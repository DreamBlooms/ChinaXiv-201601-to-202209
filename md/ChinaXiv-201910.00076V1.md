# Masked Sentence Model based on BERT for Move Recognition in Medical Scientific Abstracts

Gaihong Yu12,，Zhixiong Zhang\*1,2,3, HuanLiu12,LiangpingDing1,2

(1.National Science Library, Chinese Academy of Sciences,Beijing 100190 2.University of Chinese academy of sciences,Beijing1ooo49,China 3.Wuhan Library,Chinese Academy of Sciences,Wuhan 430071,China）

# Abstract:

Purpose: Move recognition in scientific abstracts is an NLP task of classifying sentences of the abstracts into different types of language unit. To improve the performance of move recognition in scientific abstracts,a novel model of move recognition is proposed that outperforms BERT-Base method.

Design: Prevalent models based on BERT for sentence classification often classify sentences without considering the context of the sentences. In this paper, inspired by the BERT's Masked Language Model (MLM), we propose a novel model called Masked Sentence Model that integrates the content and contextual information of the sentences in move recognition. Experiments are conducted on the benchmark dataset PubMed 2OK RCT in three steps. And then compare our model with HSLN-RNN, BERT-Base and SciBERT using the same dataset.

Findings: Compared with BERT-Base and SciBERT model, the F1 score of our model outperforms them by $4 . 9 6 \%$ and $4 . 3 4 \%$ respectively,which shows the feasibility and effectiveness of the novel model and the result of our model comes closest to the state-of-the-art results of HSLN-RNN at present.

Research Limitations: The sequential features of move labels are not considered, which might be one of the reasons why HSLN-RNN has better performance. And our model is restricted to dealing with bio-medical English literature because we use dataset from PubMed which is a typical biomedical database to fine-tune our model.

Practical implications: The proposed model is better and simpler in identifying move structure in scientific abstracts, and is worthy for text classfication experiments to capture contextual features of sentences.

Originality: The study proposes a Masked Sentence Model based on BERT which takes account of the contextual features of the sentences in abstracts in a new way. And the performance of this classification model is significantly improved by rebuilding the input layer without changing the structure of neural networks.

Keywords: Move Recognition, BERT, Masked Sentence Model, Scientific Abstracts

# 1.Introduction

The concept of move, or rhetorical move, was originally developed by Swales to functionally describe a part or section in research articles for communicative purpose (Swales et al., 2004). Authors of research papers generally need to explain the purpose, methods, results,and conclusions of their researches in abstracts. Those language units are called as the moves of the abstracts.

Many journals currently require authors to provide structured abstracts with explicitly annotated move labels.For example,authors usually use “Purpose” to indicate the move label and the sentences following the label to represent the aim of the study. But currently，many important journals such as Nature and Science still use unstructured abstracts when they publish the research articles.

Automatically recognizing moves of unstructured abstracts in research papers(move recognition in brief), which is typically a classification task, enables readers to quickly grasp the main points of research papers,and it is useful for various text-mining tasks such as information extraction, information retrieval and automatic summarization.

Many researchers have done lots of work on it. Early researches on move recognition adopted traditional machine learning methods such as Native Bayes (NB) (Teufel,1999)，Conditional Random Fields (CRF) (Hirohata et al.,2008)， Support Vector Machine (SVM) (Yamamoto and Takagi，2005; Ding et al.,2019), Logic Regression (LR) (Fisas et al.,2016) etc. These methods achieve good recognition performance, but they are very complicated to apply because they rely heavily on numerous carefully hand-engineered features such as lexical， semantic， structural, statistical and sequential features.

In recent years,neural networks have been widely used in NLP research including move recognition tasks (Dasigi et al., 2017; Kim, 2014; Lai et al., 2015; Ma et al., 2015; Zhang et al., 2019). Neural networks have strong nonlinear fiting ability and can automatically learn a better and deeper presentation for the input without complicated feature engineering. Methods using neural networks usually get beter performance than traditional machine learning methods,which is one of the reasons why deep learning methods are widely used in many NLP researches.

Especially, Di Jin et al. (Jin and Szolovits, 2O18) from MIT proposed a hierarchical sequential labeling network named HSLN-RNN which used the contextual information within surrounding sentences to help classify the current sentence. Concretely, HSLN-RNN used a Bi-LSTM layer after encoding sentence-level features to capture contextual features within sentences and a CRF layer to capture sequential features within surrounding move labels. And HSLN-RNN achieved the state-ofthe-art results with a F1 score $9 2 . 6 \%$ on the dataset of PubMed 20K RCT.

BERT (Bidirectional Encoder Representations from Transformers） (Devlin et al.， 2018), released by Google in Oct.2O18, received widespread atention because it broke the records of 11 NLP tasks when released. After the release of BERT, some researchers have done move recognition researches based on BERT and try to get beter performance. Iz Beltagy et al. (Beltagy et al.,2018) fine-tuned BERT-Base model on PubMed 20K RCT and got an average F1 score of $8 6 . 1 9 \%$ . They also released the SciBERT model which re-pre-trained the original BERT model with corpus from biomedical domain. Based on the SciBERT, the F1 score on PubMed 2OK RCT reached to $8 6 . 8 1 \%$ （204号 which was better than BERT-base model but still didn't reach to the highest F1 score of $9 2 . 6 \%$ based on HSLN-RNN model (Jin and Szolovits, 2018).

By comparing the models based on BERT and HSLN-RNN, we find that the main problem of the current BERT-based models is that they only use the content information of the sentence without considering the context information of the sentence. Here,“content information” means the sentence itself and the “context information” means the surrounding information (or the surrounding sentences) of the sentence in an abstract.

We assume that the move type of a sentence depends on not only the sentence itself but also its surrounding sentences and the context information of the sentences can help to improve the performance of move recognition. For instance, when we draft an abstract, the sentence of "Results" is more likely to be followed by a sentence of"Conclusions” than a sentence of"Purpose".

In our study, we intend to integrate the content and context information of sentences in move recognition based on BERT. Inspired by BERT's “masked language model” (MLM), we propose a “masked sentence model” (MSM) based on BERT to solve this problem. We mainly improve the move recognition task during the BERT fine-tuning procedure without changing its neutral networks. The model makes full use of the content and context of the sentences.

Our key contributions are summarized as follows:

(1） We propose a Masked Sentence Model based on BERT that can capture not only the content features but also contextual features of the sentences. And our model is easy to apply because it just rebuilds the input layer without any change on the structure of neural networks. (2) We evaluate on the public dataset for move recognition (PubMed 2OK RCT) and see an improvement of approximately $+ 4 . 3 4 \%$ F1 score compared to SciBERT, $+ 4 . 9 6 \%$ F1 score compared to BERT-Base model, which shows the effectiveness of our masked model.

# 2. Methodology

# 2.1 Main Idea

Firth (Firth,1957) proposed a distributional hypothesis in natural language processing research that words can be identified by their context. This hypothesis has been widely used in information retrieval， topic recognition (Basili and Pennacchioti,20l6) and other NLP researches.BERT's Masked Language Model (MLM) is also based on this distributional hypothesis.MLM simply masks some percentage of the input tokens at random,and then predicts those masked tokens based on their context.

Similarly, we propose that sentences in an abstract also follow the distributional hypothesis and we believe that a sentence in an abstract can be identified by the contextual sentences surrounding them.

Based on this hypothesis, a novel model called Masked Sentence Model (MSM) is proposed. In this model, it integrates two ideas of sentence representations for the move recognition task. Same as traditional deep learning classifiers,it preserves using the content of the target sentence as the input of the classfier to learn the internal features of this sentence. Moreover, for the purpose of capturing the contextual information, it innovatively uses the whole abstract but with the target sentence masked as the input of the classifier to learn the contextual features of the target sentence.

For example, there is an abstract document from PubMed’ shown in figure 1 which contains seven sentences (from $\mathbf { S } _ { 1 }$ to s7). For the second sentence(s2), we have two representations for the input of a deep learning classifier: 2-a (representation based on the content of the sentence)，2-b (representation based on the context of the sentence by using the whole abstract masking the target sentence with a fixed meaningless string denoted as ‘[MASK]'). And in the Masked Sentence Model, we combine the two representations above to learn both the content features and contextual features of the sentence(2-c).

[s1]This survey aims atreviewing the literature related to Clinical Information Systems (CIS), Hospital Information Systems (HIS),Electronic Health Record (EHR)systems,and how collected data canbeanalyzedbyArtificial Intelligence (A) techniques. [s]We selected the majorjournals (lljournals)colecting papers (more than 70o0)over thelast fiveyearsfromthetopmembersoftheresearchcommunityandreadandanalyzedthepapers(morethan200) covering the topics. $\left[ \mathbf { s } _ { 3 } \right]$ Then, we completed the analysis using search engines to also include papers from major conferences over the same five years. $[ \mathsf { s } _ { 4 } ] \mathsf { W } \mathsf { e }$ defined a taxonomy of major features and research areasof CIS,HIS,EHR systems. $[ { \sf s } _ { 5 } ] { \sf W } { \sf e }$ also defined a taxonomy for the use of Artificial Intelligence (AI) techniques on healthcare data. $\mathsf { \Gamma } [ \mathsf { s } _ { 6 } ] \mathsf { I n }$ the light of these taxonomies, we report on the most relevant papers from the literature. $\displaystyle \mathbf { \ [ s _ { 7 } ] } \mathbf { W } \mathbf { e }$ highlighted some major research directionsand issues which seem to be promising andto need further investigations overa medium- or longterm period.

2-a: representation based on content of the sentence(e.g. ${ \bf s } _ { 2 }$ of D1) [s]Weselectedthemajorjournals(lljournals)colectingpapers(morethan7ooo)overthelastfiveyearsfromthetop membersoftheresearch community,andreadandanalyzed thepapers(more than200)covering thetopics. 2-b: representation based on the context of the sentence (e.g. $\mathbf { s } _ { 2 }$ of D1) [s]Thissurveyaimsatreviewingthe literaturerelatedtoClinical Information Systems (CIS),Hospital Information Systems (HIS),Electronic Health Record (EHR) systems,andhow collecteddatacanbeanalyzed byArtificial Intellgence(AI) techniques.[MASK].Then,wecompleted theanalysis usingsearch enginestolso includepapers from major conferences over thesame fiveyears.Wedefinedataxonomyofmajor features and researchareasofCIS,HIS,EHRsystems.WealsodefinedataxonomyfortheuseofArtificial Inteligence (Al) techniques on healthcaredata.Inthe lightofthesetaxonomies,wereportonthemostrelevantpapers fromthe literature.Wehighlighted some major research directionsand issues which seem to bepromisingandto need furtherinvestigationsoveramedium-orlong-termperiod. 2-c: representation based on Masked Sentence Model (e.g. ${ \bf s } _ { 2 }$ of D1) [sz] We selected the major journals(ll journals)collectingpapers (more than ,ooo) over the last five years from thetop members oftheresearch community,and readand analyzedthe papers (more than 200) Integrate Information Systems(HIS),Electronic Health Record(EHR)systems,and how collcteddatacanbe analyzedbyArtificial Intelligence(AI) techniques.[MASK].Then,wecompleted theanalysisusing search engines to also includepapers frommajor conferences overthesame fiveyears.Wedefineda taxonomy ofmajor featuresandresearchareasofCIS,HIS,EHRsystems.Wealsodefinedaaxonomy fortheuseofArtificial Intelligence(Al) techniquesonhealthcaredata.Inthe lightof thesetaxonomies, wereportonthemost relevant papersfrom the literature.We highlighted somemajor research directions and issues which seem to be promising and to need further investigations over amedium-or long-termperiod.

We use this integrated MSM representation of the sentence as input in the BERT fine-tuning procedure and conduct several experiments to verify its effectiveness.

# 2.2 MSM Construction

Based on the main idea mentioned above, we construct the Masked Sentence Model (as shown in figure3) in three processing steps before BERT fine-tuning.

![](images/0966952d81dfd3021bcf56b08dd71c146f10f9eb8607f20a2ced21476c52cde7.jpg)  
Figure 3 The architecture ofMasked Sentence Model based onBERT

# Step1: Sentence Information Processing

In this step，for an abstract, each target sentence in the abstract of scientific papers is represented by the content of sentence.

For example, the second sentence (sz） of the abstract shown in figure 1 is annotated with “Methods”,the data format after this process step is shown in table 1. We use this representation to learn the internal features of the sentence.

Table1 data format of sentence's content   

<html><body><table><tr><td>Label</td><td>the content of the sentence</td></tr><tr><td>Methods</td><td>We selected the major journals (11 journals) collecting papers (more than 7,000) over the last five years from the top members of the research community, and read and analyzed the papers (more than 20O) covering the topics.</td></tr></table></body></html>

# Step2: Sentence Contextual Information Processing

In step2, we will get the contextual information of each sentence in the abstract. Here we adopt a new method that simply uses the whole abstract except the target sentence replacing by a [MASK] string to obtain the contextual information. And in this paper, we replace each word of the target sentence with ‘aaa’ characters to build the meaningless string of [MASK].

For the sentence(s2), the length of this sentence is 37, so the data format after this step is shown in table 2 where the second sentence is replaced with 37 ‘aaa’ characters.We input this contextual information into the BERT fine-tuning procedure and to learn the contextual features of the sentence.

Table 2 data format of sentence's context   

<html><body><table><tr><td>Label</td><td>the context of the sentence</td></tr></table></body></html>

<html><body><table><tr><td>Methods</td><td>This survey aims at reviewing the literature related to Clinical Information Systems (CIS), Hospital Information Systems (HIS), Electronic Health Record (EHR) systems, and how collected data can be analyzed by Artificial Intelligence (AI) techniques. aaa aaa aaa aaa aaa aaa aaa aaa aaa aaa aaa aaa aaa aaa aaa aaa aaa aaa aaa aaa aaa aaa aaa aaa aaa aaa aaa aaa aaa aaa aaa aaa aaa aaa aaa aaa aaa. Then, we completed the analysis using search engines to also include papers from major conferences over the same five years. We defined a taxonomy of major features and research areas of CIS, HIS, EHR systems. We also defined a taxonomy for the use of Artificial Intelligence (AI) techniques on healthcare data. In the light of these taxonomies, we report on the most relevant papers from the literature. We highlighted some major research directions and issues which seem to be promising and to need further investigations over a medium- or long-term period.</td></tr></table></body></html>

# Step3: MSM Integrate Processing

Thirdly,in this step, it integrates the content and contextual information of the sentence to construct the Masked Sentence Model. And it implements the integration by inputting the above two training samples together to the BERT fine-tuning procedure to train the Masked Sentence Model based on BERT-Base for move recognition task. For example, the final input representation for the second sentence $\left( \mathbf { s } _ { 2 } \right)$ in this step is shown in table 3.

Table 3 data format of integrate sentence's content and context   

<html><body><table><tr><td>Label</td><td>the content & context of the sentence</td></tr><tr><td>Methods</td><td>We selected the major journals (11 journals) collecting papers (more than 7,000) over the last five years from the top members of the research community, and read and analyzed the papers (more than 2oO) covering the topics.</td></tr><tr><td>Methods</td><td>This survey aims at reviewing the literature related to Clinical Information Systems (CIS), Hospital Information Systems (HIS), Electronic Health Record (EHR) systems, and how collected data can be analyzed by Artificial Intelligence (AI) techniques. aaa aaa aaa aaa aaa aaa aaa aaa aaa aaa aaa aaa aaa aaa aaa aaa aaa aaa aaa aaa aaa aaa aaa aaa aaa aaa aaa aaa aaa aaa aaa aaa aaa aaa aaa aaa aaa. Then, we completed the analysis using search engines to also include papers from major conferences over the same five years. We defined a taxonomy of major features and research areas of CIS, HIS, EHR systems. We also defined a taxonomy for the use of Artificial Intelligence (AI) techniques on healthcare data. In the light of these taxonomies, we report on the most relevant papers from the literature. We highlighted some major research directions and issues which seem to be promising and to need further investigations over a medium- or long-term period.</td></tr></table></body></html>

# 3Experiments & Results

# 3.1 Experiments design

In this paper, for diferent verification purposes, we design and conduct three different move recognition experiments based on BERT with the same neural network architecture and the same dataset. They only vary in the input data during the fine-tuning procedure.

Experiment 1 (or Expl): An experiment based on the content of sentences. We fine-tune the BERT-Base model for downstream move recognition task by using the data format as shown in table 1, which only contains the content of sentences in fine-tuning input layer.

Experiment 2 (or Exp2): An experiment based on the context of sentences.The purpose of this experiment is exploring the rationality of our assumption based on distributional hypothesis and verifying the feasibility of the method of sentence context processing. This experiment was carried out based on the context of sentences by using the data format as shown in table 2 as BERT finetuning inputs.

Experiment 3(or Exp3): The most important experiment based on the MSM integrated information. In order to verify the effectiveness of the novel MSM model which is proposed in this paper. This experiment uses the data format as shown in table 3 which integrates the content and context of sentences as BERT fine-tuning inputs.

# 3.2 Data Sets

Our study evaluates the MSM model on the benchmark dataset PubMed 20K RCT (Dernoncourt and Lee,2017) which contains approximately 20,000 medical scientific abstracts for sequential sentence classification. The dataset is based on the PubMed database of biomedical literature and each sentence of an abstract is labeled with its rhetorical role in the abstract using one of the following classes: Background, Objectives,Methods,Results, and Conclusions.

# 3.3 Hyper-parameters Setting

Our study uses the BERT-base model (Devlin et al., 2018) with a hidden size of 768,12 Transformer blocks (Vaswani et al.， 20l7) and 12 self-atention heads. And fine-tunes with the following setings: a batch size of 5,a max sequence length of 512, the learning rate of 3e-5, the init_checkpoint of bert_base, the train steps of 100,000 and the warm-up steps of 10,000.

# 3.4Evaluation Metrics

For each designed experiment, our study reports the performance with the evaluation metrics of precision (P),recall (R) and F1 score on the same test set provided by PubMed 20K RCT dataset (29,578 sentences from 2,50 abstract). The experimental results of each experiment are detailed in section 3.5.

# 3.5 Results

# The Results of Exp1: based on the content of sentences

Table 4 shows the results of experiment based on the content of sentences. It can be found that just using the content of sentences can achieve effective results for move recognition at the average precision, recall, and F1 score of $8 6 . 7 5 \%$ ， $8 6 . 6 1 \%$ ，and $8 6 . 5 3 \%$ , respectively. In this experiment, it can get promising results on the categories of Methods and Results where both the precision and recall score are above $91 \%$ . On the category of Conclusions，particularly， the F1 score reaches to a relatively good score at $8 3 . 1 3 \%$ . However, for the categories of Background and Objectives, the F1 scores are $6 9 . 6 4 \%$ and $6 4 . 2 0 \%$ respectively，which can't satisfy our expectations very well and indicates a huge room for improvement.

Table 4 The results of Exp1: based on the content of sentences   

<html><body><table><tr><td>Label</td><td>P</td><td>R</td><td>F1</td><td>Support</td></tr><tr><td>Background</td><td>64.37</td><td>75.85</td><td>69.64</td><td>3077</td></tr><tr><td>Objectives</td><td>73.55</td><td>56.97</td><td>64.20</td><td>2333</td></tr><tr><td>Methods</td><td>92.42</td><td>94.97</td><td>93.68</td><td>9884</td></tr><tr><td>Results</td><td>92.08</td><td>91.09</td><td>91.58</td><td>9713</td></tr><tr><td>Conclusions</td><td>84.95</td><td>81.38</td><td>83.13</td><td>4571</td></tr><tr><td>Avg / Total</td><td>86.75</td><td>86.61</td><td>86.53</td><td>29578</td></tr></table></body></html>

# The Results of Exp2: based on the context of sentences

Table 5 presents the results of experiment based on the context of sentences, in which it only uses the context of sentences. The performance can reach the F1 score on average of $8 6 . 0 9 \%$ ,and it indicates the validity of this method.These results prove that our basic assumption “sentences can be identified by their context in an abstract.” is reasonable. And it shows that the method of using the context of sentences greatly improves the performance on the Background and Conclusions categories, whose average F1 performance improves $6 . 1 8 \%$ and $6 . 6 1 \%$ respectively, in comparison with the corresponding ones based on the content of sentences. However, the performance on the Methods and Results categories decreases slightly compared to the corresponding ones based on the content of sentences. These two experiments indicate that using the content of sentences performs beter in Methods and Results categories and using the context of sentences performs better in Background, Conclusions and Objective categories.

Table 5 The results of Exp2: based on the context of sentences   

<html><body><table><tr><td>Label</td><td>P</td><td>R</td><td>F1</td><td>Support</td></tr><tr><td>Backgroun</td><td>72.27</td><td>79.72</td><td>75.82</td><td>3077</td></tr><tr><td>Objectives</td><td>70.51</td><td>60.27</td><td>64.99</td><td>2333</td></tr><tr><td>Methods</td><td>90.70</td><td>89.80</td><td>90.25</td><td>9884</td></tr><tr><td>Results</td><td>87.71</td><td>89.20</td><td>88.45</td><td>9713</td></tr><tr><td>Conclusions</td><td>90.19</td><td>89.30</td><td>89.74</td><td>4571</td></tr><tr><td>Avg / Total</td><td>86.13</td><td>86.15</td><td>86.09</td><td>29578</td></tr></table></body></html>

# The Results of Exp3: based on MSM integrated information

Table 6 shows the BERT's fine-tuning experimental results based on MSM model with integrated information of content and context of sentences. It shows that the novel model achieves the best results in the overall experiments,and the average precision, recall and F1 score can reach $91 . 2 2 \%$ 0 $91 . 3 0 \%$ ，and $9 1 . 1 5 \%$ respectively. Compared to the first two experiments, the results of this experiment increase by $4 . 6 2 \%$ and $5 . 0 6 \%$ respectively in terms of F1 score. The results show that the novel Masked Sentence Model performs beter performance on the task of move recognition. Furthermore，the study verifies that the model can effectively improve the performance by incorporating the content and context information of sentences.

Table 6 The results of Exp3: based on MSM integrated information   

<html><body><table><tr><td>Label</td><td>P</td><td>R</td><td>F1</td><td>Support</td></tr><tr><td>Background</td><td>75.26</td><td>81.18</td><td>78.11</td><td>3077</td></tr><tr><td>Objectives</td><td>78.08</td><td>61.98</td><td>69.10</td><td>2333</td></tr><tr><td>Methods</td><td>92.98</td><td>97.48</td><td>95.17</td><td>9884</td></tr><tr><td>Results</td><td>96.02</td><td>93.74</td><td>94.87</td><td>9713</td></tr><tr><td>Conclusions</td><td>94.70</td><td>94.51</td><td>94.60</td><td>4571</td></tr><tr><td>Avg / Total</td><td>91.22</td><td>91.30</td><td>91.15</td><td>29578</td></tr></table></body></html>

# 3.6 Result Analysis

Table7 shows the comparing results of the above-mentioned three experiments, which better explain the advantage of our integrated MSM model.

<html><body><table><tr><td colspan="6">Table Comparedresultsoftheexperiments</td></tr><tr><td rowspan="2">Label</td><td>Exp1</td><td>Exp2</td><td>Exp3</td><td>Exp3-Exp1</td><td>Exp3-Exp2</td></tr><tr><td>F1</td><td>F1</td><td>F1</td><td>+F1</td><td>+F1</td></tr><tr><td>Background</td><td>69.64</td><td>75.82</td><td>78.11</td><td>8.47</td><td>2.29</td></tr><tr><td>Objectives</td><td>64.20</td><td>64.99</td><td>69.10</td><td>4.9</td><td>4.11</td></tr><tr><td>Methods</td><td>93.68</td><td>90.25</td><td>95.17</td><td>1.49</td><td>4.92</td></tr><tr><td>Results</td><td>91.58</td><td>88.45</td><td>94.87</td><td>3.29</td><td>6.42</td></tr><tr><td>Conclusions</td><td>83.13</td><td>89.74</td><td>94.60</td><td>11.47</td><td>4.86</td></tr><tr><td>Avg /Total</td><td>86.53</td><td>86.09</td><td>91.15</td><td>4.62</td><td>5.06</td></tr></table></body></html>

From the “Exp3-Expl", it can be found that the MSM model greatly improves the performance on the ‘Conclusions’ and ‘Background' categories, whose average F1 performance improve $1 1 . 4 7 \%$ and $8 . 4 7 \%$ respectively, in comparison with the corresponding ones based only on the content of the sentence. Then followed by the $4 . 9 \%$ improvement on‘Objectives’ category. The impact on the ‘Methods’and‘Results’ categories is relatively small Based on these comparisons, it indicates that the‘Conclusions’ and‘Background’ categories are more context-sensitive and can achieve huge improvements by incorporating contextual information. This makes sense because the‘Background' move always appears at the beginning of the abstracts and the ‘Conclusions’ move appears at the end of the abstract. So by adding contextual information to the input, the model will learn the positional information to a certain extent.

Correspondingly， from the“Exp3-Exp2”, in comparison with the corresponding ones based only on the context of the sentence,the MSM model got the highest F1 value growth on the‘Results' category $( 6 . 4 2 \% )$ ， the lowest F1 value growth on the Background category $( 2 . 2 9 \% )$ and a relative balanced growth in the other three categories. This indicates that the content of the sentence also plays an important role to identify the rhetorical role of the sentence,which used to express the author's writing intention.-

# 4. Comparisons & Discussion

In this section, we compare the model proposed in this paper with other models, and discuss the compared results. Table 8 lists our model and the other experimental models evaluated on the PubMed $2 0 \mathrm { k }$ corpus. MaskedSentenceModel based on BERT presented in this paper is denoted by “Our Model".“Others”contains HSLN model, BERT-Base model, and two models of SciBERT.

It shows that HSLN's average F1 score still ranks the first based on Bi-LSTM $\cdot +$ CRF methods. Our model achieves better performance than the current models based on BERT,which outperforms 4.34 points than SciBERT (BaseVocab),and 4.96 points than BERT-Base. However, our current model is still 1.45 points lower than HSLN.This makes sense because the sequence tag information considered in the HSLN model is not considered in our model, so there is room for improvement based on BERT.

Table8PubMed20kRCTresults   

<html><body><table><tr><td></td><td>Models</td><td>F1(PubMed 20k RCT)</td></tr><tr><td>Our Model</td><td>MaskedSentenceModel_BERT</td><td>91.15</td></tr><tr><td rowspan="4">Others</td><td>HSLN-RNN(Jin and Szolovits. 2018)(SOTA)</td><td>92.6</td></tr><tr><td>BERT-Base(Beltagy et al..2018)</td><td>86.19</td></tr><tr><td>SciBERT(SciVocab)(Beltagv etal..2018)</td><td>86.80</td></tr><tr><td>Sci BERT (BaseVocab) (Beltagy et al..2018)</td><td>86.81</td></tr></table></body></html>

# 5.Conclusions&Future Work

This paper presents a novel approach to recognizing moves in scientific abstracts using Masked Sentence Model based on BERT. It demonstrates that integrating content and context information of sentences by using MSM model to learn the internal and contextual features of sentences can improve overal performance of recognitions. The proposed method achieves more successful results than other previous BERT based methods.It outperforms the BERT-Base and SciBERT results by （24 $4 . 9 6 \%$ and $4 . 3 4 \%$ respectively on the public dataset PubMed 20k RCT. Because the model doesn't take sequential features of move labels into account, HSLN-RNN stillhas bettr performance than it.

Our MSM approach is general and easy to apply. It can achieve a better performance improvement on the move recognition task just by making some optimizations in the input layer without any change on the BERT's internal structure of neural networks. And we believe that our model is effective for many other context-sensitive NLP tasks including text classfication, sentiment analysis.

Although our model are proved to have great performance, there is also some limitations. Our current method is stillrelatively simple because we simply replace each word of the sentences with a meaningless string ‘aaa’ to generate the contextual representation of the sentences. In the future, we will improve the performance of the MSM method from the following aspects:

1. We will try to modify the method of generating the contextual information of the sentences such as using a fixed length string of 3O‘aaa’ to mask the target sentences and analyze its effect. 2. We plan to extend our MSM to cover many other important features for move recognition such as sequential features which are not incorporated in our MSM approach.

3. Also we would like to try modifying the structure of neural networks to fit the special input layer proposed in this study. In that way, this context-sensitive approach could be more efficient.

# Acknowledgments

This work is supported by the project “The demonstration system of rich semantic search application in scientific literature”(Grant No.1734) from the Chinese Academy of Sciences.

# Author Contributions

Zhixiong Zhang (zhangzhx $@$ mail.las.ac.cn) and Gaihong Yu(yugh@mail.las.ac.cn) designed and produced the research. Huan Liu(liuhuan@mail.las.ac.cn) conducted the experiments. Gaihong Yu wrote the main body of the paper. Zhixiong Zhang done a lot of modifications and improvements and finally completed the paper. Huan Liu and Liangping Ding(dingliangping $@$ mail.las.a.cn) done a lot of paper revision and improvement work especially in the Introduction and Methodology Section.

# References

Amini I, Martinez D, Molla D. Overview of the ALTA 2012 shared task[J]. 2012.   
Badie K, Asadi N,Tayefeh Mahmoudi M. Zone identification based on features with high semantic richness and combining results of separate classifiers[J]. Journal of Information and Telecommunication, 2018: 1-17.   
Basili R， Pennacchiotti M. Distributional lexical semantics: Toward uniform representation paradigms for advanced acquisition and processing tasks[J]. Natural Language Engineering, 2010, 16(4): 347-358.   
Beltagy I, Cohan A,Lo K .SciBERT: Pretrained Contextualized Embeddings for Scientific Text[J]. 2019.   
Dasigi P,Burns G A P C, Hovy E, et al. Experiment segmentation in scientific discourse as clauselevel structured prediction using recurrent neural networks[J]. arXiv preprint arXiv:1702.05398, 2017.   
Devlin J, Chang M W,Lee K, et al. Bert: Pre-training of deep bidirectional transformers for language understanding [J]. arXiv preprint arXiv:1810.04805, 2018.   
Ding Liangping, Zhang Zhixiong,Liu Huan.Research on Factors Affecting the SVM Model. Performance on Move Recognition[J].Data Analysis and Konwledge Discovery,2019   
Firth JR. A synopsis of linguistic theory,1930-1955[J]. Studies in linguistic analysis,1957.   
FisasB， Ronzano F， Saggion H. A multi-layered annotated corpusofscientific papers[C]//Proceedings of the Tenth International Conference on Language Resources and Evaluation (LREC 2016). 2016: 3081-3088.   
Franck Dernoncourt and Ji Young Lee. 2O17. Pubmed 2O0k rct: a dataset for sequential sentence classification in medical abstracts. In IJCNLP.   
Gerlach M, Peixoto T P,Altmann E G.A network approach to topic models[J]. Science advances, 2018, 4(7): eaaq1360.   
Hirohata K, Okazaki N,Ananiadou S,et al. Identifying sections in scientific abstracts using conditional random fields[C]//Proceedings of the Third International Joint Conference on Natural Language Processing: Volume-I. 2008.   
Mingbo Ma, Liang Huang, Bing Xiang, and Bowen Zhou. 2015. Dependency-based convolutional neu- ral networks for sentence embedding. arXiv preprint arXiv:1507.01839.   
Peters M E, Neumann M, Iyyer M, et al. Deep contextualized word representations[J]. arXiv preprint arXiv:1802.05365, 2018.   
Radford A, Narasimhan K, Salimans T, et al. Improving language understanding by generative pretraining[J].URL:https://s3-us-west-2.amazonaws.com/openaiassets/researchcovers/languageunsupervised/language understanding paper. pdf, 2018.   
Siwei Lai, Liheng Xu, Kang Liu, and Jun Zhao. 2O15. Recurrent convolutional neural networks for. text classification. In AAAI, volume 333, pages 2267- 2273.   
Swales,J.M. Research Genres: explorations and applications [M].Cambridge:Cambridge University. Press,2004:228-229.   
Taylor W L."Cloze procedure": A new tool for measuring readability[J]. Journalism Buletin, 1953, 30(4): 415-433.   
TEUFELS.Argumentativezoning:information extraction fromscientific text[D]. Edinburgh:University of Edinburgh,1999.   
Vaswani A， Shazeer N, Parmar N,et al. Atention is all you need[C]//Advances in neural information. processing systems. 2017: 5998-6008.   
Yamamoto Y,Takagi T. A sentence classification system for multi-document summarization in the. biomedical domain [C]//Proceedingsof International Workshop on Biomedical Data Engineering. 2005: 90-95.   
Yoon Kim. 2O14. Convolutional neural net- works for sentence clasification. arXiv preprint. arXiv:1408.5882.   
Zhang Z, Liu H, Ding L, et al. Moves Recognition in Abstract of Research Paper Based on Deep Learning[C]//2019 ACM/IEEE Joint Conference on Digital Libraries (JCDL). IEEE, 2019: 390- 391.