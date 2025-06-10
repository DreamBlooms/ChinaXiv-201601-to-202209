# A Creativity Survey of Unsupervised Graph Neural Network: Interactive Clustering and Embedding

# XIA LIU

School of Computer and Information Engineering,Henan Normal University; Ix15518903750@ 163.com

WEI LI

Institute of Computing Technology, Chinese Academy of Sciences; liwei@ict.ac.cn

Abstract:The rise and application of neural network has successfully promoted theresearch of pattrn recognition and data mining.In recent years,graph neural network has atracted more and more attntion.It has some applications in text classification,sequenceannotation,neural machine translation,relationextraction,image clasificationandotherfields. Thisreview mainlyintegrates theexistingresearchonsemi-supervisedorunsupervised graphneuralnetwork.Theresearch workof this paperis mainlyclasified in three aspects,oneisbasedontheclassficationofresearchquestions,theother is basedon the classificationofresearch methods,and the third is basedontheclassificationofmeasures.The mainresearch problems are thelow-dimensional representationof nodes in graphs andthe over-smooth probleminthe process of message transfer.The research methods mainly focus on the graph embedding algorithm,such as the graph embedding algorithm based on probability graph andthe method basedondeep learning.The measurement methods mainly focus on the accuracy and ffciencyof thealgorithmand model.Finally, tis paper alsoputs forwardthe feasible futureresearch direction,which provides reference for readers.

Keywords: Graph neural network, unsupervised learning, network embedding, node clustering

# 1 INTRODUCTION

Graph,alsocalled network,asacommondata structure, widelyappears in People's Dailylife,suchas social network, World Wide Web and soon.The rise and application of neural network has successfully promoted the research of pattern recognition and data mining.Many machine learning tasks that once relied heavily on manual feature extraction,such as objectdetection machine translationand speechrecognition,have beenrevolutionized byvarious end-to-enddeep learning paradigms,such asconvolutional Neural networks (CNN)long and short trm memory (LSTM)and auto-encoders.Graph neural networks isakindof ink model,which relies on theinformation transferbetween nodes inthe Graph tocapture the dependency relations in the Graph.Most graph neural networks (GNNS）are specifically designed forsemi-supervised learningtasks (transductionand induction),inwhich supervised information (labeled nodes)playsan importantrole in enhancing the resolution. Unfortunately,supervised informationcannot fundamentallysolve this problem for tworeasons: first,embedding in the network,unsupervised information cannot beobtained from unsupervised tasks such as node clustering and link prediction.Most existing unsupervised GNNS either reconstruct the original information (adjacency matrix and atribute matrix)or maximize mutual information to retain as much information as posible.Therefore,the super-smooth problem of unsupervised GNNS tends to be worse than that of semi-supervised GNNS.Second,while learning messageaggregation from labeled nodes can alleviate smoothing problems,itcanalso cause serious over-fiting problems that can severely impact performance.

This paperon the existing research literature about the diagram of the neural network are classified,based on the literaturereadingand study,firstof allweanalyzedthe various literatureresearch,found that partofthe literature is to morecomplex diagram of the neural network low dimensionalrepresentationof the nodes,partofthis documentis to map neural network insmooth problem was analyzed in the process of information transfer.Then we analyzed the research methods and found that most of the literatures are about graph embedding algorithms.Some literatures study graph embedding algorithms basedon probability graphs,and the other literatures study graph embedding algorithms based on deep learning In adition,the analysis of literatures shows that most literatures studysemi-supervised and unsupervised graph neural networks,and some are fullysupervised neural networks.Finally,we also analyze the measurement methods of various literatures,and find that some literatures study the accuracyof the proposed algorithm or model in node classification,and the other literatures analyze the efficiency of the proposed algorithm or model.

Through the analysis ofthe research methods and measurement methods of various literatures,the characteristics and innovation points of each article are found.Combined with the previous analysis,this paper also puts forward the future research direction of graph neural network and points that can be optimized.

Therestofthepaperisorganized as follows.Section I gives theclasificationof researchobjects of Unsupervised Graph Neural Network.Section Ilintroduces the clasification of research methods.Section IV introduces the comparisonof experimental analysis in related literature.Section Vdiscuses the research opportunities in future work and Section VI concludes the paper.

# 2CLASSIFICATIONOFRESEARCHOBJECTS

Table 1:Different Research Objects   

<html><body><table><tr><td rowspan="2">Topics</td><td colspan="3">Networkclassification</td></tr><tr><td>GCN</td><td>GNN</td><td>GAN</td></tr><tr><td>Low dimensional represent</td><td>I.[9][15][19][17]</td><td>II. [1][3]</td><td>ⅢI</td></tr><tr><td>Over-smoothing problem</td><td>IV.[8][13][7]</td><td>V.</td><td>VI.[16]</td></tr></table></body></html>

# 2.1 Criteria

Figure inrecent years because neural network has atracted the atentionof manyscholars,te studyof map neural network is also ivolved inmanydiferent neighborhood.Inorder tofindoutthe differences,this paper willclasify map neural network Inaddition,forneuralnetworkstudythereare two main problems,oneisabout thelowdimensionalrepresentation ofthe nodes,theotherisasmooth problemintheprocessofinformation transferInthissection,twoseparateanddistinct criteria will be used to classify existing strategies into different types.

1)Network clasification.There are threetypes:figureconvolution networkand the neural networkand generate against network most of the existing map neural network is designed asasemi-supervised task,because the supervision information can reduce the messging process of smoothing problem,and figure convolution network and the neural network can learn by graph embedding low-dimensional representation of the nodes.

2)Topics.Thereare two kinds ofproblems:Low-dimensionalrepresentation orover-smoothingof nodes.The purposeof graph embedding is to represent every node in the graph as alow-dimensional vector and to usethat vector to perform a series of downstream tasks in semi-supervised learning tasks,using supervised information (labeled nodes）to mitigate over-smoothing of message delivery.Unfortunately,due to the lack of supervised information,thesuper-smooth problem tends to be more serious in unsupervised tasks.Therefore,the over-smooth problem of information transmission exists in graph convolutional networks and generative adversativenetworks,while the low-dimensionalrepresentation problemof nodes only exists in graph convolutional networks and graph neural networks.

# 2.2 The Classification

Basedontheappeal classification standard, we givetheclassficationinTable1.The meaningofeach class isas follows: Type I:This type is to studythe low-dimensional representation of nodes in graph convolutional neural networks by learning the low-dimensional representation of nodes in complex networks through graph embedding algorithm. Type II: This type is to study the low-dimensional representation of nodes in graph neural networks. Type II: This type deals with low-dimensional representation of nodes in generative adversarial networks. Type IV: This type studies the problem of over smooth information transfer in graph convolutional networks. Type V: This type studies the over-smooth problem of information transfer in graph neural networks. Type VI: This type deals with the over-smooth problemof information transfer in Graph generation network.

# 2.3 Explanation of Different Types

References ([9][15][19])belong to TypeI.Reference [9]studies how to effctivelycaptureand measure theaffinity relationship between nodes,and learn thelow-dimensional representation of atributes and nodes inthe same semantic space.Meanwhile,in order to obtain high-quality embedding,this paper proposes a variational auto-encoder,which emplaces the Gaussian distributionof the mean and Gaussianvariance of each nodeand atribute.Reference15] proposed a general methodof learning node representation in graph structured data in an unsupervised way-- depth graph informationanalysis (DGI) DGI relies on the mutual information between the maximized patch representation and the corresponding high-level graph abstract Both are derived using the established graph convolutional network architecture. Reference [19] explores an architecture-jumping knowledge (JK) network that flexibly utilizes diferent neighborhood ranges for each node to achieve better structure-aware representation.

References ([1][3])belong to Type I1. Reference [1] studies learming low-dimensional vectors to represent vertices in graphs,and proposes a new GraRep model forlearning weighted graph vertex representation.Diferent from existing work, this modelintegrates the global tructure informationof graphs intothe learning process Current feature learning methods are notcapable of capturing the diversityof connectionpatterns observed in the network.Reference[3] Node2vec,an algorithmframework forlearning continuous featurerepresentationofnodes inthenetwork,is proposed.InNode2vec,the mapping of nodes tolow-dimensional feature Spaces is learned to maximize the possibilityof preserving nodes'network neighborhoods.

References ([8][13][7])belong to TypeIV.Reference [8]provedthat graph convolutionof GCNmodel is actuallyaspecial formof Laplaciansmoothing form,which is the keyreason whyGCNs comes intoplay,but it also brings many potential problems of over-smoothingof convolution layerIn order to overcome the limitations of GCN model with shalow architecture,this paper proposes colaborative trainingand self-training methods to train GCNs Reference[13]proposes a novel and flexible DropEdge technologytoalleviate the over-smoothingandover-fiting problems DropEdge removes a random number of edges from the input graph at each training stage,likeadata intensifier and a messaging decelerator. The paper alsotheoretically proves that DropEdgecan either slowdown over-smooth convergence or mitigate the esulting information loss.More importantly,DropEdge is a general skillthatcan beequipped with manyother backbone models to improve performance.Inreference[7],an improved propagationscheme based on personalized PageRank is derived using the relationship between graph convolutional network (GCN)and PageRank.This propagation process is used to construct a simple model, neural predictive personalized propagation (PPNP)and its fast approximation APPNP.

References ([16])belong toType VI.Reference[16] proposeda framework to solve the weakness ofattentionalrestriction in graph atentional network andthe problem ofover-smoothing on decision boundaries.This paper first provedthe oversmoothing behaviorof GATtheoretically,and then developed a methodusing constrained atentional weights according toclass boundariesandfeature aggegationpaterns Inaddition,inorder toalleviate theproblemofover-fting,this paper proposes additional constraints on the graph structure.

# 3CLASSIFICATIONOFRESEARCHMETHODS

Table2.DifferentResearchMethods   

<html><body><table><tr><td rowspan="2">Graph embedding algorithm</td><td colspan="3">Machine learning</td></tr><tr><td>Semi-supervised learning</td><td>Unsupervised learning</td><td>Supervised learning</td></tr><tr><td>Based on probability model</td><td>I. [15][10][11][17]</td><td>II. [3][20]</td><td>II.[1][14]</td></tr><tr><td>Based on deep learning</td><td>IV. [2]</td><td>V. [9][4][8][7][6]</td><td>VI</td></tr></table></body></html>

# 3.1 Criteria

Most existing graph neural networks (GNNS)are designed based on deep learningforsemi-supervised learning tasks,in which supervised information (labeled nodes)is used to aleviate the over-smooth problem of message delivery.In this section,three independent and different criteria would be used to divide research objects into different types:

1）Machine learning.There are threetypes here: Semi-supervised learning,unsupervised learning orsupervised learning. There are many methods of artificial inteligence,but the methodused for gaph neural network is machine learning,and mostof theresearches on graph neural network are semi-supervised learing,because supervisedinformationcan aleviate the over-smooth problemof informationtransmisson.Therefore,three different machine learning methods willbe studied in this paper.

2）Graph embedding algorithm.There are two kinds of Graph embedding algorithm here: Based on probability model or Based on deep learning.Invarious references,this paper uses two different graph embedding algorithms based on probability model and deep learning respectively to study graph clustering,so this is alsoan important distinguishing standard of this paper

# 3.2 The Classification

Basedonthe appeal classificationstandard,we givetheclasification in Table 2.The meaning ofeachclass is as follows: TypeI: This type is toovercome theover-smooth problemofinformationtransferinsemi-supervised graph neuralnetwork byadopting the embedded method based on probability graph model.

Type I: This type is to overcome the flatness of information transfer in unsupervised graph neural network by adopting the embedding method based on probability graph model.

Type III:This type overcomes the information transfer in fullysupervised graph neural network byadopting the embedding method based on probability graph model.

Type IV:This type is to overcome the over-smooth problem of information transfer in semi-supervised graph neural network by adopting the embedding method based on deep learning model.

Type V:This type is toovercome the over-smooth problem ofinformation transfer in unsupervised graph neural network byadopting the embedding method based on deep learning model.

TypeVI: This typeof embedding method based onprobability graph modelisusedtoovercome the over-smooth problem of information transfer in fully supervised graph neural network.

# 3.3Explanation of Different Types

References ([15][10][1])belong to TypeI.Reference[15]proposed depth graph information (DGI),which isageneral method to learn node representationin graph structuredata inan unsupervised way.DGI relies on the mutual information between the maximized patch representationand the corresponding high-level graph summary,and these graphs are derived fromthe established graph convolutional network architecture The patch representation after learning summarizes the subgraph centered on the nodes of interest,so Referencecan be reused in the downstream node intelligent learning task.In reference[1O],DeepWalk is proposed to summarize recent advances in language modeling andunsupervised feature learning,or deep learning.From word sequences to graphics,DeepWalk uses local information from truncated random walks to learn potential representations by treating walks as equivalent sentences.Reference[11] uses graph Mutual information (GMI) to measure the corelation between input graph and high-level hidden representation. GMI extends thetraditional calculation idea of mutual information fromvector space to graph domain.Itis essential to measure mutual information from two aspects of node characteristics and topological structure.The isomorphic transformation of the input graph is invariant，which isan unavoidable constraint in many existing graph representation learning algorithms.Inadition,existing mutualinformation estimationmethods,suchas MNE,canbeusedtoefectivelyestimate and maximize it.

References ([3][20]) belong to Type II.In Node2VEC,Reference [3] learns the method of mapping nodes to lowdimensional space of features,which can keep the network neighborhood of nodes to the maximum extent.The paper defines aflexible node network neighborhood concept and designs a biased random walk process,which can effectively explore diferent neighborhoods Reference[20] proposed a semi-supervised learning framework based on graph embedding.The paper developed two variants of the method,transductionand induction,bytraining theembeding of eachinstance to jointlypredicttheclass tagsand neighborhood context in the graph In the transformation variantof the method,classlabels aredeterminedby learned embeddings and input feature vectors,while in the inductive variant, embeddings are defined as parameter functions offeature vectors,so instances not seen in training can be predicted. References ([1]) belong to Type II.Reference [1] proposed a new GraRep model for learning weighted graph vertex representation.This modelrepresents the vertices in the graphbylearninglow-dimensional vectors.Diferent fromexisting studies, it integrates the global structure information of the graph into the learning process. References ([12])belong toTypeIV.Reference[12]proposedanoveladversarial graph data embedding framework,which encodes the topological structure andnode contentof the graph intoacompactrepresentation,andon thisbasis trains the decoder toreconstruct the structure of thecomposition.In adition,the potential representation is matched withtheprior distribution through theadversarial training scheme Inorderto lear arobust embedding,twoadversarial methods are developed,adversarialregularized graphauto-encoder (ARGA)andadversarial variational graphauto-encoder (ARVGA). References ([9][4][7]) belong to Type V.Reference [9] proposedan atribute network model(CAN)basedoncollaborative embedding,which CANlearn low-imensional representations of atributes and nodes in te same semantic space,so as to efectivelycapture and measure the similarity betweenthem In order to obtain high-quality embedding,we propose a variationalauto-encoderReference thatuses the meanand varianceof Gausian distribution to embedeach node.Reference [4]Introduced in many network is another feature,namelythe characteristics of communitystructure inthis feature,the network node to close together,and only aloose connection between these groups We proposed a methodto detect such community,based onusingthe centricity index to find the ideaof thecommunity boundaries Reference[7]Using the relationship between graph convolutionnetwork (GCN)andPageRank,wederiveanimproved propagation scheme based on personalized PageRank.We use this propagation process to construct a simple model, personalized neural predictive propagation (PPNP),and its fast approximation,APPNP.

# 4REVIEWOFEXPERIMENTALANALYSIS

In this section,we willclassifythe metric of evaluation and system parameters,as shown in Table 3.InTable 3,all experimental analysis isalso classified according tothe metricand parameters.Itcanbeseen from Table 3that mostof the references compare superiority, effectiveness index of algorithm.

Table 3.Experiments with Different Metric and Parameters   

<html><body><table><tr><td rowspan="2">Metric</td><td colspan="2">Parameters</td></tr><tr><td>algorithm</td><td>model</td></tr><tr><td>Accuracy</td><td>I.[15][8][6][13][11][16]</td><td>II.[18][7][20][17]</td></tr><tr><td>Efficiency</td><td>III. [2]</td><td>IV.[1][14]</td></tr><tr><td>Others</td><td>V.[3]</td><td>VI.</td></tr></table></body></html>

# 4.1MetricofEvaluation

Accuracy means the proportion ofcorrect node classification to actual node clasification of social network.The formula is as follows:

Eficiency means that thetimecomplexityrequiredtouse thealgorithmor modelislessthanthatof theexistingalgorithm or model. The formula is as follows:

$$
\mathrm { T } ( { \mathrm { n } } ) = \mathrm { O } ( \mathrm { f } ( { \mathrm { n } } ) )
$$

Other metric includes Macro-F1 Score,Micro-F1 Score and Normalized mutual information (NMI).

# 4.2 System Parameters

Thealgorithmrepresents thealgorithmusedfornodeclasificationinsocialnetwork.Thetimecomplexityofthealgorithm is small,andthedivisionofnodes insocialnetworkismoreaccuratethantheexistingalgorithm.However,theinformation in the semi-supervised graph neural network can alleviate this problem.   
Model represents the model used for node classification.When dealing with diffrent problems,diferent models can achieve different efects.Therearealso some other parameters,such asdiferent experiments of graph neural network and comparison experiments of existing models.

# 4.3Experimental Comparison

In reference[15],the authors tested the proposed method ona synthetic network.Forthe transformation task,the average clasification accuracy(with standard deviation)at the test nodes of the proposed method was reported after 5O training sessions (followed by logistic regression), indicating the high accuracy of the DGI method.

Inreference[8],theauthor conductedalarge numberof experiments onreal benchmark toverifythe proposed theoryand method,including joint training self-trainingcombination andcrossexperiment results show thatthe proposed joint training and self-training methods have high accuracy in node classification of GCNs.   
Inreference [6],the authors evaluate the performanceof the proposed method BTLSC detection community in nine real world networks and real communities on the ground.Experimental results show that the proposed method has high accuracy in node classification   
In reference[13],theauthors tested the layer2,8,32ofthe proposed modelondiferent data sets,andtheresults show that the proposed model DropEdge improves the accuracy of the test.   
In reference[11], theauthor compares the proposed method with otherunsupervised methods.Experimental results show that the proposed GMI-Mean and GMI-Adaptive methods achieve the best clasification accuracy on allthree data sets. This powerful performance benefits from the encoded representation that preserves the node features and topology information in the graph to the maximum extent,which is conducive to classfication。   
In reference [1],experiments arecaried out on three different types of tasks,including clustering classificationand visualization experiments. The results show that the proposed GraRep model can integrate different $\mathbf { k }$ -step local relation informationintotheglobal graph representationof differenttypes of graphs,so itcanbeefectivelyapplied todifferent tasks.   
In reference[14], theauthor compares the proposedLINE model with several existing graph embedding methods thatcan be extended to very large networks.The results show that in the reconstructed network,LINE (second) is superior to DeepWalk'scombinationoffirst and second order proximityon the original network in mostcases and hascaptured most of the information,LINE.The method isaveryefectiveand eficientnetwork embedding method,whichissuitable for dense and sparse networks.   
In reference [7],the authorconducted experiments on GCN,N-GCN,GAT,BootStrapped feature Propagationand JK modelsrespectively.According to the experimental results,the proposed model personalized Propagationof Neural Predictions (PPNP) has high accuracy in node classification.   
In reference [2O],compared with the existing methods,the author shows that the proposed semi-supervised learning framework based on graph embedding has high accuracy in text classfication   
Inreference[17],the author evaluated thenodeclassificationperformanceofthe proposed MODELSGCon Cora,Citeseer and Pubmed datasets respectively.Experimental results show that the SGC has beter performance on Citeseer, which is due to fewer parameters of SGC and therefore less over-fiting.   
In eference2],the performanceof dual-Sinkhorn is testedonMNSTdataset,andthe experimentalresultsshow thatthe proposed algorithm is eficient and has low time complexity.

# 5DISCUSSIONANDSUGGESTION

This paper discusses the research methodandresearch object found figure ofthe neural network study mostlyaredesigned forasemi-supervised task,because supervision informationcan slow the smoothing problem of messaging Butsmooth information transmission problem in unsupervised way more serious,because there is no degree information is available Therefore,unsupervised neural network research is an importantisue Deep learning undoubtedly become the preferred method However,to date, most research on and the figure of the neural network are based on the graph embedding algorithm without supervision and supervision,andsupervision of all research methods basedon depth of learning algorithm wererare .Therefore,this article puts forward the folowing several direction,can offr the direction for the future study of the figure of neural network.

1)The low-dimensionalrepresentationof nodes in graph attention network can be studied,and then the graph embeding algorithmbasedondeep learning is used foranalysis.Finally,the measurement is carriedout by the accuracyof node classification.

2)Many practical methods are selected in this paper and compared with other methods Therefore,future research can conduct in-depth researchon theaccuracyandeficiencyofthe method and find the best method for differentobjects

# 6 CONCLUSIONS

Throughthe previousanalysis,we findthat mostof theresearches on graph neural networks are basedonsemi-supervised learning tasks,but the over-smoth problem of messge delivery is more serious in unsupervised learning Therefore,the graph neural network based on unsupervised modecan be further studied in the future,especially the graph embeding algorithm based on deep learning to learn the low-dimensional representation of nodes in graph atention network.There are fewanalyses and researches in this area.Therefore,this kindofresearch method can befurther studied in the future.

# References

[1]S.Cao,W.Lud.Xu,“Grae:Linggraepeseatioithlobaltructuralifoatio”i,,0.   
[2] M.Cuturi,“Sinkhorn distances: Lightspeed computationofoptimal transport,”in NIPS,2013,pp.2292-2300.   
[3]A.GroverandJ.Leskovec,“node2vec: Scalable feature learning for networks,”in SIGKDD,2016,pp.855-864.   
[4]M.Girvannd.EJewan“Couirctureinoaldgicaletwoks”ol.99,o12pp82,. [5]D.Jin,KgaeFeldg“Deioipei background, general and specialized topics,”2019,pp.1-1.   
[6]T.N.Kipfand M.Weling,“Semi-supervised clasifification with graph convolutional ntworks,”inICLR,2017.   
[7J.Klicpera,d“dictge:aalkspoaldgk”9. [8]Q.Li,Z.Hadu“Dephsauotosfdlg”8,4. [9]Z.Meng,S.Liang,H.Bao,and X.Zhang,“Co-embedding atributed networks,”in WSDM,2019,pp.393-401.   
[10]B.Perozi,R.Al-foundS.iea,“Deepwalk:olineleaingofsocialrepresetatios,”inKD,2014,pp70-71.   
[1Z.Peng,Wuang,o.ZgoXudang“Graeprseatilangiaaltaloatitio” in WWW,2020, pp.259-270.   
[12]S.Pan,RHg"e 2615.   
[13]Y.Rong,WHngTXudHang“Dogedsaooluileoksoeifaii [14J.Tang,M.Qu.Wang,.ZangJYann.ei“E:ge-saleifoatioetwokebeing”iWW,5,7. [15]P.Velickovic,W.Fedus,W.L.Hamilton,P.Lio,Y.Bengio,andR.D.Hjelm,“Deep graph infomax,”inICLR,2019.   
[16]G.WangingHangLsoc“roatooieargdostrats” abs/1910.11945,2019.   
[17]F.Wu,A.HCftydbifouoatks” [18]K.Xu,W.Hu,J.Leskovec,and S.Jegelka,“How powerful are graph neural networks?”in ICLR,2019.   
[19]K.XuC.obKbrtgij 2018, pp. 5449–5458.   
[20]Z.Yang,W..CoenndRautdiovRevisitigs-spesedleagihgabengs”26p48.