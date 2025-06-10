# Span-based Joint Entity and Relation Extraction with Attention-based Span-specific and Contextual Semantic Representations

Bin Ji, Shasha Li\*, Jie Yu, Jun Ma, Qingbo Wu, Yusong TanCollege of Computer,National University of Defense Technology, Changsha, China{jibin， shashali，yj， majun， qingbowu， yusongtan}@nudt.edu.cn

# Abstract

Span-based joint extraction models have shown their efficiency on entity recognition and relation extraction. These models regard text spans as candidate entities and span tuples as candidate relation tuples. Span semantic representations are shared in both entity recognition and relation extraction, while existing models cannot well capture semantics of these candidate entities and relations.To address these problems, we introduce a span-based joint extraction framework with atention-based semantic representations. Specially,attentions are utilized to calculate semantic representations, including span-specific and contextual ones. We further investigate effects of four atention variants in generating contextual semantic representations. Experiments show that our model outperforms previous systems and achieves state-of-the-art results on ACE2005, CoNLL2004 and ADE.

# 1Introduction

This paper considers intra-sentence joint entity and relation extraction. For joint extraction mode can alleviate cascading errors and promote information utilization compared to pipelined one, this mode has drawn much attention. Typically, the joint extraction task is solved by sequence tagging based methods (Zheng et al., 2017; Chi et al., 2019).

Rather than using sequence tagging based methods,recent works attempt to solve the task with spanbased joint extraction mode (Dixit and Al-Onaizan,2019; Luan et al.,2O19). Typically, this mode first processes sentence text into text spans, which are span-based candidate entities ("spans" for short); then, calculates span semantic representations and performs span classification on them to obtain predicted entities; next,forms span-based candidate relation ("relation" for short) tuples with spans,and calculates relation semantic representations with corresponding span semantic representations; at last, performs relation classification on relation semantic representations and obtains predicted relation triples.This mode further improves joint extraction performance, whereas exists three problems.

First, different tokens in span should contribute diferently to span representation, which we calspanspecific features. But existing methods treat each span token equally important (Eberts and Ulges, 2019)or just consider span head and tail tokens (Dixit and Al-Onaizan, 2O19), ignoring these significant features. Take the span "a Palestinian youth” in sentence 1 of Figure 1 as an example, the "youth” should contribute much greater to the span representation than $" a "$ and "Palestinian”when classifying the span into "PER". Second, local contextual information of relation tuples is omitted (Luan et al., 2O18; Dixit and Al-Onaizan,2019) or just calculated by max pooling way (Eberts and Ulges,2O19） when performing relation classification,which do not suficiently capture information contained in it. Whereas local context may contain crucial information to help predict the relations that relation tuples hold. A case study is shown in sentence 2 of Figure 1,the "ownership"(in red font） can greatly help to determine the relation ("PART-WHOLE") of the relation tuple (namely

<html><body><table><tr><td>Sentence 1: The army said troops fired, and hit a boy,after [a Pales tinian youth]PER threw a stone,:</td></tr><tr><td>Sentence 2: The weak score is primarily the result of [Starbucks]oRG current strategy of increasing equity ownership of[several foreign subsidiariesloRG,*</td></tr><tr><td>Relation:<several foreign subsidiaries,Starbucks,PART-WHOLE> Sentence 3: [Palestinians]GPE claim [all of the West Bank and Gaza]Loc for a state.*</td></tr></table></body></html>

Figure 1: Sentence examples including gold entities and gold relation triples from the ACE2Oo5 dataset, where "PER","ORG” etc., denote gold entity types,"PART-WHOLE" denotes gold relation type, texts in bracket are spans of gold entities and underlined texts are local contexts of gold relation tuples,"Relation” denotes gold relation triple.

<several foreign subsidiaries, Starbucks $>$ ). Third, sentence-level contextual information is ignored in both span and relation classifications,which may be important compensation information for both ones. An example is given in sentence 3 of Figure 1,"state”(in red font) benefits the relation classification of the relation tuple (namely <allof the West Bank and Gaza, Palestinians>), while "state” is neither contained in the relation tuple nor in the local context (namely "claim"),but contained in other part of sentence 3,which is sentence-level.

To address above issues, we introduce a span-based joint extraction model with attention-based spanspecific and contextual semantic representations. Specifically,1) MLP attention is used to calculate spanspecific semantic representation; 2)atention-based sentence-level contextual semantic representation for span is calculated by taking span-specific semantic representation as query and sentence token sequence semantic representations as key,value respectively; 3)local and sentence-level contextual semantic representations for relation are obtained by attention calculation with relation tuple semantic representations and corresponding token sequence semantic representations.The advantage of this approach is that we can capture the most useful information to constitute efficient span and relation semantic representations.

We take BERT (Devlin et al.,2O19)as the default backbone network,and explore the three research questions.Moreover, we investigate effcts of Multi-Head atention (Vas wani etal.,2O17),Dot-Product attention (Luong et al.,2O15), General attention (Luong et al.,2O15) and Additive atention (Bahdanau et al.,2015) in generating contextual semantic representations.Extensive experiments on three benchmark datasets show that our model consistently outperforms previous systems. In addition,the Multi-Head attention firmly improves over other attention variants.

# 2 Related Works

Traditionally, pipelined entity and relation extraction method is divided into two subtasks, namely entity detection and relation clasification. Various neural networks have been widely investigated for the two subtasks,such as RNNs (Huang et al.,2015; Ma and Hovy,2016), CNNs (Limsopatham and Coller, 2016) for entity detection,and RNNs (Zhang and Wang, 2O15), CNNs (Zeng et al.,2O14), Transformer (Verga et al., 2018; Wang et al., 2019) for relation classification.

As discussed in $\ S 1$ , joint entity and relation extraction is typically formulated as a sequence tagging based task. Traditionally,table-flling methods have been widely explored (Miwa and Sasaki,2014; Gupta et al.,2Ol6),where token labels and relation labels fillthe diagonal and off-diagonal of the table respectively. Recently, many works concentrate on leveraging deep neural networks to tackle this task,e.g. stacked bidirectional LSTM (Miwa and Bansal, 2O16; Zheng et al.,2O17),combination of bidirectional LSTM and CNN (Zhou et al.,2017),and combination of bidirectional LSTM and attention mechanism (Chi et al., 2O19; Nguyen and Verspoor, 2O19). In addition,a novel machine reading comprehension based approach (Li et al.,2019) is proposed, which formulates the task as a Question $\&$ Answer task but still in sequence tagging based mode.

Recently,span-based joint extraction methods have been investigated to tackle problems existing in sequence tagging based methods,e.g., inability to detect overlapping entities. Specially,Dixit and AlOnaizan (2O19) realize this method by obtaining span semantic representations through a BiLSTM over concatenated ELMo, word and character embeddings,then share them in both span and relation classifications. Luan et al. (2O18) obtain span semantic representations generally the same as Lee et al. (2017), but reinforce them by introducing coreference task. Follow Luan et al. (2018),Luan et al. (2O19) propose DyGIE, which can capture span interactions through a span graph constructed dynamically. Wadden et al. (2019) deliver further performance increases on DyGIE by replacing the BiLSTM with BERT and introduce $\mathrm { { D y G I E + + } }$ ，More recently, Eberts and Ulges (2O19） propose SpERT,a simple but effective span-based model that takes BERT as backbone and use two FFNNs to classify span and relation respectively. Unlike previous works,SpERT dramatically reduces model training complexity by adopting negative sampling.

Our work follows SpERT, but differs in span-specific and contextual semantic representations. Specifically,our model obtains these semantic representations with attention mechanism.By calculating the matching degree between target sequence semantic representations and source sequence semantic representations,attention mechanism obtains atention scores on the source sequence, which are weight scores in essence. And the more important the information,the higher weight score it holds. Clasified by implementation manners of score function, attntion mechanism has multiple variants, e.g., Content-Base attention (Graves et al.,2014),Additive attention (Bahdanau et al., 2O15), General attention (Luong et al., 2015), Dot-Product attention (Luong et al., 2015),Multi-Head attention (Vaswani et al.,2017).

# 3Approach

In the rest, we abbreviate "semantic representation”as "representation".Figure 2 gives an overview of our model, which uses BERT as encoder following SpERT: we map word embeddings into BERT embeddings using pre-trained Transformer blocks (Vaswani et al.,2O17). Based on the representations, we calculate span representations and perform span classification $\&$ filtration (S3.1); Then,we organize relation tuples,calculate relation representations and perform relation classification $\&$ filtration (83.2); Third, we investigate effects of multiple attention variants in generating contextual representations (83.3); At last, we introduce model training settings (83.4).

Define a sentence and a span from the sentence to help introduce the rest, where $t$ denotes tokens and subscripts (e.g.,1,2, 3...) denote token indexes, as:

$$
\begin{array} { r l } & { \mathrm { s e n t e n c e : ~ } \boldsymbol { S } = ( t _ { 1 } , t _ { 2 } , t _ { 3 } , \dots , t _ { n } ) } \\ & { } \\ & { \mathrm { s p a n : ~ } \mathbf { s } = ( t _ { i } , t _ { i + 1 } , t _ { i + 2 } , \dots , t _ { i + j } ) } \end{array}
$$

# 3.1Span Classification and Filtration

Add NoneEntity type to the pre-defined entity types (denoted as $\eta$ ).Spans will be classified into NoneEntity as long as they do not hold any pre-defined entity types.

As Figure 2 shows,span representation for clasification composes of four parts, namely a) concatenation of span head and tail representations, $\mathbf { b }$ )span-specific representation, c) sentence-level contextual representation,and d) span width embedding. We use $X _ { i }$ to denote the BERT embedding of token $t _ { i }$ and the BERT embedding sequences of $s$ and s are defined as follows,where $X _ { 0 }$ denotes the BERT embedding of [CLS]:

$$
\begin{array} { r } { \beta _ { S } = [ X _ { 0 } , X _ { 1 } , X _ { 2 } , X _ { 3 } , . . . , X _ { n } ] } \\ { \beta _ { \mathbf { s } } = [ X _ { i } , X _ { i + 1 } , X _ { i + 2 } , . . . , X _ { i + j } ] } \end{array}
$$

Concatenation of span head and tail representations. If a span composes of more than one token, then concatenate the BERT embeddings of span head and tail tokens.Else,duplicate the BERT embedding of the single token and concatenate them. The concatenation result for span s is as:

$$
\mathcal { H } _ { \mathbf { s } } = [ X _ { i } ; X _ { i + j } ]
$$

![](images/b68a5644551038bb5246e4d100569b4ec4ffe29f7797af7de01dd762efed615e.jpg)  
Figure 2: Our joint extraction model with attention-based span-specific and contextual representations. 1) MLP atention is utilized to obtain span-specific representation; 2) Sentence-level contextual representation for span is obtained by atention calculation between span-specific representation and sentence token embedding sequence; 3)Relation local and sentence-level contextual representations are calculated by relation tuple representation attending to corresponding token embedding sequences.

Span-specific representation. Here we use MLP attention (Dixit and Al-Onaizan,2O19) to calculate span-specific representation. Take span s as an example.

$$
\begin{array} { l } { { \displaystyle \mathcal { V } _ { \mathbf { k } } = \mathbf { M } \mathbf { L } \mathbf { P } _ { k } ( X _ { \mathbf { k } } ) \qquad s . t . \quad \mathbf { k } \in [ i , i + j ] } } \\ { { \displaystyle \alpha _ { \mathbf { k } } = \frac { \exp ( { \boldsymbol { \gamma } } _ { \mathbf { k } } ) } { \underset { m = i } { \sum } \exp ( { \boldsymbol { \gamma } } _ { \mathbf { m } } ) } } } \\ { { \displaystyle \mathcal { F } _ { \mathbf { s } } = \sum _ { m = i } ^ { i + j } \alpha _ { \mathbf { m } } X _ { \mathbf { m } } } } \end{array}
$$

Where $\nu _ { \mathbf { k } }$ is a scalar; $\alpha _ { \mathbf { k } }$ is the attention weight of $\mathbf { X _ { k } }$ , computed by Softmax function; $\mathcal { F } _ { \mathbf { s } }$ is the spanspecific representation by matrix calculation on attention weights and ${ \it B } _ { \mathrm { s } }$ . By this way, we can evaluate the significance of each span token,and the more important a token, the larger atention weight it holds.

Sentence-level contextual representation. Take $\mathcal { F } _ { \mathbf { s } }$ as query, $\boldsymbol { B _ { S } }$ as key and value respectively, sentence-level contextual representation for span s is calculated as:

$$
\mathcal { T } _ { \mathbf { s } } = \mathbf { A t t e n t i o n } ( \mathcal { F } _ { \mathbf { s } } , \mathcal { B } _ { S } , \mathcal { B } _ { S } )
$$

Information beneficial for span classification will be assigned a heavy weight, and the contextual representation will be taken to constitute span representation.

Span width embedding. Span width embedding allow the model to incorporate a prior over the span width. Fixed-size embedding for each span width 1,2,..(Lee et al.,2017) is learned during model training. Thus,we can look up a width embedding $\mathscr { W } _ { j + 1 }$ from the embedding matrix for s.

Span classification. The final span representation for classification is as:

$$
\mathcal { R } _ { \mathbf { s } } = [ \mathcal { T } _ { \mathbf { s } } ; \mathcal { F } _ { \mathbf { s } } ; \mathcal { H } _ { \mathbf { s } } ; \mathcal { W } _ { j + 1 } ]
$$

$\mathcal { R } _ { \mathrm { s } }$ first passes through a multi-layers FFNN and then is fed into a Softmax classifier, which yields a posterior for s on $\eta$ (including NoneEntity), as:

$$
y _ { \mathbf { s } } = \mathbf { S o f t m a x } ( \mathbf { F F N N } ( \mathcal { R } _ { \mathbf { s } } ) )
$$

Spanfiltration.By searching the highest-scored class, the $y _ { \mathrm { s } }$ estimates which entity type does s holds. We just keep spans that are not classified into NoneEntity, and form a predicted entity set $\mathcal { E }$ . Then we perform relation classification on relation tuples derived from $\{ \mathcal { E } \otimes \mathcal { E } \}$ to reduce searching space, where $\otimes$ denotes Cartesian Product.

# 3.2 RelationClassificationandFiltration

Add NoneRelation type to the pre-defined relation types (denoted as $\gamma$ ).Let $s _ { 1 } , s _ { 2 }$ be two spans, relation tuples taken for relation classification are defined as:

$$
< s _ { 1 } , s _ { 2 } > \in \{ \mathcal { E } \otimes \mathcal { E } \} \qquad s . t . \quad s _ { 1 } \neq s _ { 2 }
$$

As Figure 2 shows,relation representation for classification composes of three parts, namely a) concatenation of relation tuple representations, $\mathbf { b }$ )local contextual representation,c) sentence-level contextual representation.

Concatenation of relation tuple representations. Before concatenating $\mathcal { R } _ { s _ { 1 } }$ and $\mathcal { R } _ { s _ { 2 } }$ , we first apply a multi-layers FFNN to them to reduce their dimensions. The concatenation result is as:

$$
\mathcal { H } _ { \mathbf { r } } = [ \mathbf { F F N N } ( \mathcal { R } _ { s _ { 1 } } ) ; \mathbf { F F N N } ( \mathcal { R } _ { s _ { 2 } } ) ]
$$

Local contextual representation. Let $\boldsymbol { B _ { \mathrm { c } } }$ denotes the BERT embedding sequence of local context between $s _ { 1 }$ and $s _ { 2 }$ ,as:

$$
\mathcal { B } _ { \mathbf { c } } = ( X _ { m } , X _ { m + 1 } , X _ { m + 2 } , \ldots , X _ { m + n } )
$$

The attention-based local contextual representation is calculate by taking $\mathcal { H } _ { \mathbf { r } }$ as query, $\boldsymbol { B _ { \mathbf { c } } }$ as key and value respectively, as:

$$
\mathcal { F } _ { \mathbf { r } } = \mathbf { A t t e n t i o n } ( \mathcal { H } _ { \mathbf { r } } , \mathcal { B } _ { \mathbf { c } } , \mathcal { B } _ { \mathbf { c } } )
$$

Sentence-level contextual representation. The sentence-level contextual representation is calculated by taking $\mathcal { H } _ { \mathbf { r } }$ as query, $\boldsymbol { B _ { S } }$ as key and value respectively, as:

$$
\mathcal { T } _ { \mathbf { r } } = \mathbf { A t t e n t i o n } ( \mathcal { H } _ { \mathbf { r } } , \mathcal { B } _ { S } , \mathcal { B } _ { S } )
$$

Relation classification. Before $\mathcal { F } _ { \mathbf { r } }$ and $\mathcal { T } _ { \mathbf { r } }$ are taken to constitute relation representation, we first apply two different multi-layers FFNNs to them to reduce their dimensions,aiming to keep them in a proper proportion in relation representation. The final relation representation for classification is as:

$$
\mathcal { R } _ { \mathbf { r } } = [ \mathcal { H } _ { \mathbf { r } } ; \mathbf { F F N N } _ { \mathcal { F } } ( \mathcal { F } _ { \mathbf { r } } ) ; \mathbf { F F N N } _ { \mathcal { T } } ( \mathcal { T } _ { \mathbf { r } } ) ]
$$

Akin to span classification, $\mathcal { R } _ { \mathbf { r } }$ first passes through a multi-layers FFNN and then is fed into a Softmax classifier, which yields a posterior for $< s _ { 1 } , s _ { 2 } >$ on $\gamma$ (including NoneRelation), as:

$$
y _ { \mathbf { r } } = \mathbf { S o f t m a x } ( \mathbf { F F N N } ( \mathcal { R } _ { \mathbf { r } } ) )
$$

Relation filtration. By searching the highest-scored class, the $y _ { \mathbf { r } }$ estimates which relation type does ${ < s _ { 1 } }$ ， $s _ { 2 } >$ holds. Only relation tuples that are not classified into NoneRelation are kept and compose predicted relation triples with predicted types.

# 3.3 Attention Variants

In this paper,we investigate effects of Multi-Head attention,Additive attention,Dot-Product attention and General atention in generating contextualrepresentations,of which score functions are shown below.

$$
M u l t i - H e a d a t t e n t i o n : { \bf s c o r e } = \frac { Q \odot \mathcal { K } } { \sqrt { d _ { \mathcal { K } } } }
$$

$$
A d d i t i v e a t t e n t i o n : \mathbf { s c o r e } = \mathcal { W } _ { 1 } \cdot Q + \mathcal { W } _ { 2 } \cdot \mathcal { K }
$$

$$
\mathbf { \nabla } - P r o d u c t ~ a t t e n t i o n : ~ \mathbf { s c o r e } = \mathcal { W } \cdot ( \mathcal { Q } \odot \mathcal { K } )
$$

$$
G e n e r a l a t t e n t i o n : \ \mathbf { s c o r e } = \boldsymbol { \mathcal { Q } } \cdot \boldsymbol { \mathcal { W } } \cdot \boldsymbol { \mathcal { K } }
$$

Where $\mathcal { Q } , \kappa$ denote query and key respectively; $\mathcal { W }$ denotes parameter matrix; $d _ { K }$ denotes dimension of $\kappa$ ；·and $\odot$ denote matrix broadcast and element-wise multiplication respectively. For Multi-Head attention and Dot-Product attention,we first apply different multi-layers FFNNs to $\mathcal { Q }$ and $\kappa$ , aiming to convert them to the same dimension.

# 3.4 Model Training

Parameter matrices of FFNNs and attentions are learned,and BERT is fine-tuned during model training The joint loss function of our model is defined as:

$$
\mathscr { L } = 0 . 4 \mathscr { L } ^ { \mathbf { s } } ~ + ~ 0 . 6 \mathscr { L } ^ { \mathbf { r } }
$$

Where $\mathcal { L } ^ { \mathbf { s } }$ denotes the cross-entropy loss of span classification and ${ \mathcal L } ^ { \mathbf r }$ denotes the binary cross-entropy loss of relation clasification. Due to the fact that performance of relation classification is generally worse than span one,we apply a larger weight score to ${ \mathcal L } ^ { \mathbf r }$ ， aiming to let the model focus more on relation classification.

Negative sampling (Eberts and Ulges,2O19) are adopted during model training to improve model performance and robustness. Unlike previous works, we adopt a dynamic sampling strategy, where the negative examples for both entity and relation are thirtyfold of the ground truth ones in each sentence. By this strategy, our model keeps a much more balanced data distribution on training data.

# 4Experiments

# 4.1 Datasets

We test our model on ACE2005, CoNLL2004 and ADE, which are refered as ACE05,CoNLL04 and ADE respectively in the rest.

· ACE05 (Doddington et al., 2004) English dataset composes of news articles in multi-domain, e.g., broadcast, newswire, weblog etc. Seven coarse-grained entity types and six coarse-grained relation types are pre-defined. We follow the training/dev/test split in (Li and Ji,2014; Li et al.,2019). It has 351 documents for training, 80 for development and 80 for test, of which 437 contain overlapping entities.   
· CoNLL04 (Roth and Yih,2OO4) composes of news articles from outlets such as WSJ and AP, We follow the training/dev/test split in (Adel and Schitze,2017; Bekoulis et al.,2018), which consists 910 articles for training, 243 for development and 288 for test.   
· ADE(Gurulingappa et al., 2Ol2) aims to extract drug-related adverse effects from medical text, including two pre-defined entity types (namely Adverse-Effect and Drug) and a single relation type i.e.,Adverse-Effect. It consists of 4272 sentences,of which 1695 contain overlapping entities. We conduct 10-fold cross validation following (Bekoulis et al.,2018; Eberts and Ulges,2019).

For ACEO5,following (Li et al.,2O19; Luan et al.,2019),an entity is considered correct if we can identify its head region and type correctly. A relation is considered correct if we can identify its argument entities and type correctly. For CoNLL04 and ADE,following (Li et al.,2019; Eberts and Ulges, 2019), we treat an entity as correct when its type and entity region match ground truth,and treat a relation as correct when its type and argument entities match ground truth.

# 4.2Experimental Settings

We build our model upon English cased version of BERTBAsE. We set the negative sampling rate to 30,batch size for model training to 8,dropout to O.2 and width embedding dimension to 50. For Multi-Head attention, the head number is set to 8. $\mathbf { F F N N } _ { \mathcal { F } }$ and $\mathbf { F F N N } _ { \mathcal { T } }$ contain three fully connected layers; and allthe other FFNNs contain two layers.We set diffrent epochs incase of different datasets. For alldatasets,the span width threshold is initialized to 10. In our model, we adopt weight losssetting, as shown in equ.(11),and follow Eberts and Ulges (2O19) for other hyperparameter settings.

# 4.3 BaselineModels

We compare our model with the following models.

· DyGIE (Luan et al.,2O19) is the current span-based state-of-the-art model on ACEO5. It reinforces span and relation representations by introducing coreference task.   
· Multi-turn QA (Li et al., 2O19) is the current sequence tagging based state-of-the-art model on ACE05 and CoNLLO4. It formulates joint entity and relation extraction as a multi-turn question and answer task, but still in sequence tagging based mode.   
· SpERT (Eberts and Ulges, 2O19) is the current span-based state-of-the-art model on ADE and CoNLLO4. Our work follows this model but adopts atention-based span-specific and contextual representations.   
· Relation-Metric (Tran and Kavuluru,2O19) is a sequence tagging based model in multi-task learning scheme. It reports performances on ADE and CoNLLO4,and achieves state-of-the-art on ADE.

Table 1: Results of different models on ACE05, CoNLL04 and ADE test sets. $\mathbf { S P A N } _ { M u l t i - H e a d }$ outperforms previous SOTA models by $+ 1 . 1 9$ $+ 1 . 2 9$ ， $+ 1 . 3 1$ in entity recognition, and $+ 2 . 0 4 , + 2 . 8 6 , + 1 . 8 9$ in relation extraction. (previous sequence tagging based SOTA $\dagger$ ; previous span-based SOTA $\ddagger$ ）   

<html><body><table><tr><td rowspan="2">Dataset</td><td rowspan="2">Method</td><td colspan="3">Entity</td><td colspan="3">Relation</td></tr><tr><td>P</td><td>R</td><td>F1</td><td>P</td><td>R</td><td>F1</td></tr><tr><td rowspan="3">ACE05</td><td>Multi-turn QA t</td><td>84.7</td><td>84.9</td><td>84.8</td><td>64.8</td><td>56.2</td><td>60.2</td></tr><tr><td>DyGIE ‡</td><td>-</td><td>1</td><td>88.4</td><td>=</td><td></td><td>63.2</td></tr><tr><td>SPANMulti-Head</td><td>89.32</td><td>89.86</td><td>89.59</td><td>71.22</td><td>60.19</td><td>65.24</td></tr><tr><td rowspan="3">CoNLL04</td><td>Multi-turn QA †</td><td>89.0</td><td>86.6</td><td>87.8</td><td>69.2</td><td>68.2</td><td>68.9</td></tr><tr><td>SpERT ‡</td><td>88.25</td><td>89.64</td><td>88.94</td><td>73.04</td><td>70.00</td><td>71.47</td></tr><tr><td>SPANMulti-Head</td><td>90.11</td><td>90.36</td><td>90.23</td><td>76.96</td><td>71.88</td><td>74.33</td></tr><tr><td rowspan="3">ADE</td><td>Relation-Metric †</td><td>86.16</td><td>88.08</td><td>87.11</td><td>77.36</td><td>77.25</td><td>77.29</td></tr><tr><td>SpERT ‡</td><td>88.99</td><td>89.59</td><td>89.28</td><td>77.77</td><td>79.96</td><td>78.84</td></tr><tr><td>SPANMulti-Head</td><td>89.88</td><td>91.32</td><td>90.59</td><td>79.56</td><td>81.93</td><td>80.73</td></tr></table></body></html>

<html><body><table><tr><td rowspan="2">Method</td><td colspan="2">ACE05</td><td colspan="2">CoNLL04</td><td colspan="2">ADE</td></tr><tr><td>Entity (F1)</td><td>Relation (F1)</td><td>Entity (F1)</td><td>Relation (F1)</td><td>Entity (F1)</td><td>Relation (F1)</td></tr><tr><td>SPANMulti-Head</td><td>89.59</td><td>65.24</td><td>90.23</td><td>74.33</td><td>90.59</td><td>80.73</td></tr><tr><td>SPAN Dot-Product</td><td>87.94</td><td>62.88</td><td>88.23</td><td>70.89</td><td>88.15</td><td>77.31</td></tr><tr><td>SPANGeneral</td><td>88.66</td><td>63.56</td><td>88.96</td><td>73.48</td><td>89.93</td><td>80.14</td></tr><tr><td> SPAN Additive</td><td>89.07</td><td>64.53</td><td>89.17</td><td>71.36</td><td>89.68</td><td>79.75</td></tr></table></body></html>

Table 2: Performance comparations of attention variants. Multi-Head attntion firmly outperforms the others,with an absolute F1 increase up to 2.44(ADE) in entity recognition and 3.44(CoNLLO4) in relation extraction.

# 4.4 Main Results

We compare our model with both sequence tagging based methods and span-based methods on the three benchmark datasets, and show the results in Table 1. We denote our method as $\mathbf { S P A N } _ { M u l t i - H e a d }$ ，which means we use Multi-Head attention to calculate contextual representations.For ACEO5 and CoNLL04, we report performance under micro-average metrics, and apply macro-average metrics to ADE performance, which follow prior Works. For ACEO5 and ADE,all the reported performances take overlapping entities into consideration.

（204 $\mathbf { S P A N } _ { M u l t i - H e a d }$ consistently outperforms both sequence tagging based and span-based SOTA methods on the three benchmark datasets. Compared to SpERT, $\mathbf { S P A N } _ { M u l t i - H e a d }$ delivers performance increases in entity recognition by 1.29(CoNLL04) and 1.31(ADE), while better ones in relation extraction, by 2.86(CoNLLO4) and 1.89(ADE). We owe these performance increases to efcient spanspecific representation and contextual representations. Moreover, $\mathbf { S P A N } _ { M u l t i - H e a d }$ delivers solid performance increases compared to DyGIE by 1.19 and 2.04 in entity recognition and relation extraction on ACE05. However, it's worth noting that DyGIE adopts a multi-task learning scheme,reinforcing span representations by introducing coreference task,which is absent in our method.

Besides Multi-Head attention, we investigate Dot-Product attention, General attention and Additive attention in our method.Table 2 shows performances of these attention variants on the three benchmark datasets. $\mathbf { S P A N } _ { M u l t i - H e a d }$ consisiently outperforms the other three methods. One possible reason is that in Multi-Head attention,the eight attention heads attnd to diffrent contextual information and learn features from diferent representation spaces. Thus Multi-Head attntion based contextual representations can better compensate span and relation representations.

<html><body><table><tr><td>Method</td><td>Entity (F1)</td><td>Relation (F1)</td><td>Method</td><td>Entity (F1)</td><td>Relation (F1)</td></tr><tr><td>SPANMulti-Head</td><td>88.10</td><td>62.13</td><td>SPAN Multi-Head</td><td>88.10</td><td>62.13</td></tr><tr><td>-SpanSpecific</td><td>86.78</td><td>60.21</td><td>-local</td><td>87.96</td><td>60.56</td></tr><tr><td>-SentenceLevel</td><td>87.57</td><td>61.12</td><td>-SentenceLevel</td><td>88.21</td><td>61.77</td></tr><tr><td>base</td><td>85.80</td><td>59.00</td><td>base</td><td>87.91</td><td>59.66</td></tr></table></body></html>

Table 3: Ablations on ACEO5 dev set with differ- Table 4: Ablations on ACE05 dev set with different span-specific and span sentence-level contex- ent relation local and sentence-level contextual utal representation settings. representation settings.

# 5 Ablation Study

Based on $\mathbf { S P A N } _ { M u l t i - H e a d } $ , we conduct ablations on the ACE20o5 dev set to analyze effects of different model components.

# 5.1Span-specific and Sentence-level Contextual Representations for Span

Table 3 shows effects of span-specific representation and sentence-level contextual representation for span in our model, where -Span Specific denotes ablating the span-specific representation by replacing $[ \mathcal { F } _ { \bf s } ; \mathcal { H } _ { \bf s } ]$ in equ.(4) with the max pooling of ${ \boldsymbol { B } } _ { \mathbf { s } }$ ; -SentenceLevel denotes ablating the sentencelevel contextual representation by replacing $\mathcal { T } _ { \mathbf { s } }$ in equ.(4) with the BERT embedding of [CLS] generated on $\boldsymbol { B _ { S } }$ ; base is the model by performing above two ablations, which is the default span representation setings in SpERT.For ACEO5,we observe that both span-specific representation and sentence-level contextual representation are helpful for both entity recognition and relation extraction.This is due to that span representations are shared in the two subtasks.

# 5.2Local and Sentence-level Contextual Representations for Relation

Table 4 shows effects of local and sentence-level contextual representations for relation in our model, where -local denotes ablating local representation by replacing $\mathcal { F } _ { \mathbf { r } }$ in equ.(9) with the max pooling of $\boldsymbol { B _ { \mathbf { c } } }$ ; -Sent enceLevel denotes ablating sentence-level contextual representation by removing $\mathbf { F F N N } _ { \mathcal { T } } ( \mathcal { T } _ { \mathbf { r } } )$ from equ.(9); base is the model by performing above two ablations, which is the default relation representation setings in SpERT.For ACEO5,we observe that both local and sentence-level contextual representations apparently benefit relation extraction, while have negligible influence on entity recognition. A convincing explanation is that these representations directly constitute relation representation, while affect span representation only by backpropagation.

It is worth noting that local contextual representation has a greater impact on relation extraction compared to sentence-level one. One reason for this is that information determining relation type mainly exists in relation tuples and the local context. Another reason is that as compensation information, sentence-level contextual representation occupies a relative smal proportion in relation representation, aiming to avoid introducing noise into relation representation.

# 6 Conclusion

We introduce atention-based semantic representation generating methods in span-based joint entity and relation extraction method. We apply MLP atention to capture span-specific features aiming to obtain semantic rich span representation,and calculate task-specific contextual representations with attention architecture to further reinforce span and relation representations. Our approach firmly outperforms both the sequence tagging based and span-based SOTA methods on three benchmark datasets,creating new state-of-the-art results.As future work, we would like to consider further improving relation clasification performance by reducing span classification errors.We also plan to explore more advanced methods for encoding effcient span and relation representations.

# Acknowledgements

The work is supported by the National Key Research and Development Program of China (2018YFB1004502) and the National Natural Science Foundation of China (61532001).

References   
Heike Adel and Hinrich Schuitze.2017. Global normalizationof convolutional neural networks for joint entity and relation classification.In Martha Palmer,Rebecca Hwa,and Sebastian Riedel,editors,Proceedings of the 2017 Conference on Empirical Methods in Natural Language Processing, EMNLP 2Ol7,Copenhagen, Denmark, September 9-11, 2017, pages 1723-1729.Association for Computational Linguistics.   
Dzmitry Bahdanau,Kyunghyun Cho,and Yoshua Bengio.2O15.Neural machine translation by jointly learning to align and translate. In Yoshua Bengio and Yann LeCun, editors,3rd International Conference on Learning Representations,ICLR 2015,San Diego, CA, USA, May 7-9,2O15,Conference Track Proceedings.   
Giannis Bekoulis,Johannes Deleu,Thomas Demeester,and Chris Develder.2018.Joint entity recognition and relation extraction as a multi-head selection problem. Expert Syst. Appl.,114:34-45.   
Renjun Chi,Bin Wu,Linmei Hu,and Yunlei Zhang.2O19.Enhancing joint entityand relation extraction with language modeling and hierarchical attention. In Jie Shao,Man Lung Yiu,Masashi Toyoda,Dongxiang Zhang, Wei Wang,and BinCui,editors, Web and Big Data-Third International Joint Conference,APWeb-WAIM 2019, Chengdu, China,August 1-3,2019,Proceedings,Part I,volume 11641 of Lecture Notes in Computer Science, pages 314-328. Springer.   
Jacob Devlin,Ming-Wei Chang,Kenton Lee,and Kristina Toutanova.2O19.BERT: pre-training of deep bidirectional transformers for language understanding. In JillBurstein,Christy Doran,and Thamar Solorio,editors, Proceedings of the 2019 Conference of the North American Chapter of the Association for Computational Linguistics: HumanLanguage Technologies,NAACL-HLT2O19,Minneapolis,MN,USA,June2-7,2019,Volume 1 (Long and Short Papers), pages 4171-4186. Association for Computational Linguistics.   
Kalpit Dixit and Yaser Al-Onaizan. 2019. Span-level model for relation extraction. In Anna Korhonen, David R. Traum,and Lluis Marquez,editors,Proceedings of the 57th Conference of the Association for Computational Linguistics,ACL 2019,Florence,Italy, July 28- August 2,2019,Volume 1: Long Papers,pages 5308-5314. Association for Computational Linguistics.   
George R. Doddington,Alexis Mitchell， Mark A. Przybocki,Lance A.Ramshaw, Stephanie M. Strassel, and Ralph M. Weischedel. 2004.The automatic content extraction (ACE) program - tasks,data, and evaluation. In Proceedings of the Fourth International Conference on Language Resources and Evaluation, LREC 2004, May 26-28,2O04, Lisbon, Portugal. European Language Resources Association.   
Markus Eberts and Adrian Ulges.2019. Span-based joint entity and relation extraction with transformer pretraining. arXiv preprint arXiv:1909.07755,abs/1909.07755.   
Alex Graves, Greg Wayne,and Ivo Danihelka.2014. Neural turing machines. arXiv preprint arXiv:1410.5401.   
Pankaj Gupta, Hinrich Schutze,and Bernt Andrassy.2016.Table filing multi-task recurrent neural network for joint entity and relation extraction. In Nicolett Calzolari,Yuji Matsumoto,and Rashmi Prasad,editors, COLING 2016, 26th International Conference on Computational Linguistics,Proceedings of the Conference: Technical Papers, December 11-16,2016, Osaka, Japan, pages 2537-2547. ACL.   
Harsha Gurulingappa, Abdul Mateen Rajput, Angus Roberts, Juliane Fluck, Martin Hofmann-Apitius,and Luca Toldo. 2012. Development of a benchmark corpus to support the automatic extraction of drug-related adverse effects from medical case reports.J.Biomed.Informatics,45(5):885-892.   
Zhiheng Huang, Wei Xu, and Kai Yu. 2015. Bidirectional LSTM-CRF models for sequence tagging.arXiv preprint arXiv:1508.01991,abs/1508.01991.   
Kenton Lee,Luheng He, Mike Lewis,and Luke Zettlemoyer. 2O17.End-to-end neural coreference resolution. In Martha Palmer, Rebecca Hwa,and Sebastian Riedel,editors,Proceedings ofthe 2O17 Conference on Empirical Methods in Natural Language Processing,EMNLP2017,Copenhagen,Denmark, September 9-11,2O17,pages 188-197. Association for Computational Linguistics.   
Qi Li and Heng Ji. 2O14. Incremental joint extraction of entity mentions and relations. In Proceedings of the 52nd Annual Meeting ofthe Associationfor Computational Linguistics,ACL2014, June 22-27,2014, Baltimore,MD, USA,Volume 1: Long Papers, pages 402-412. The Association for Computer Linguistics.

Xiaoya Li,Fan Yin,Zijun Sun, Xiayu Li,Arianna Yuan,Duo Chai,Mingxin Zhou,and Jiwei Li. 2O19.Entityrelation extraction as multi-turn question answering. In Anna Korhonen, David R. Traum,and Lluis Marquez, editors,Proceedings of the 57th Conference ofthe Association for Computational Linguistics,ACL 2019,Florence,Italy,July28-August 2,2019,Volume 1: Long Papers,pages 1340-1350.Association for Computational Linguistics.

Nut Limsopatham and Nigel Collier. 2016. Bidirectional LSTMfor named entity recognition in twiter messages. In Bo Han,Alan Riter,LeonDerczynski, Wei Xu,and Tim Baldwin, editors,Proceedings ofthe 2nd Workshop on Noisy User-generated Text, NUT@COLING 2016, Osaka, Japan, December 11,2016, pages 145-152. The COLING 2016 Organizing Committee.   
Yi Luan,Luheng He,Mari Ostendorf,and Hannaneh Hajishirzi.2018. Multi-task identification of entities, relations,ad coreference for scientific knowledge graph construction. In Ellen Rilof,David Chiang, Julia Hockenmaier,and Jun'ichi Tsujii,editors,Proceedings of the 2O18 Conferenceon Empirical Methods in Natural Language Processing,Brussls, Belgium, October 31 - November 4,2018,pages 3219-3232. Association for Computational Linguistics.   
Yi Luan,Dave Wadden,Luheng He,Amy Shah,Mari Ostendorf,and Hannaneh Hajishirzi.2O19.A general framework for information extraction using dynamic span graphs. In Jill Burstein, Christy Doran,and Thamar Solorio,editors,Proceedings of the 2Ol9 Conference of the North American Chapter of the Association for Computational Linguistics: Human Language Technologies, NAACL-HLT20l9, Minneapolis,MN, USA, June 2-7,2019, Volume 1 (Long and Short Papers),pages 3036-3046. Association for Computational Linguistics.   
Thang Luong, Hieu Pham,and Christopher D.Manning.2015.Effective approaches to attention-based neural machine translation.In Lluis Marquez, Chris Calison-Burch,Jian Su,Daniele Pighin,and Yuval Marton,editors, Proceedings of the 2015 Conference on Empirical Methods in Natural Language Processing, EMNLP 2015, Lisbon, Portugal, September 17-21,2015, pages 1412-1421.The Association for ComputationalLinguistics.   
Xuezhe Ma and Eduard H. Hovy. 2016.End-to-end sequence labeling via bi-directional lstm-cnns-crf. In Proceedings of the 54th Annual Meeting of the Association for Computational Linguistics,ACL 2O16,August 7-12, 2016, Berlin, Germany Volume 1: Long Papers.The Association for ComputerLinguistics.   
Makoto Miwa and Mohit Bansal. 2O16. End-to-end relation extraction using lstms on sequences and tree structures. In Proceedings of the 54th Annual Meeting of the Association for Computational Linguistics,ACL 2016, August 7-12,2O16, Berlin, Germany, Volume 1: Long Papers.The Association for Computer Linguistics.   
Makoto Miwa and Yutaka Sasaki. 2014. Modeling joint entity and relation extraction with table representation. In Alessandro Moschiti, Bo Pang,and Walter Daelemans, editors,Proceedings_of the 2O14 Conference on Empirical Methods in Natural Language Processing,EMNLP 2014, October 25-29, 2014, Doha, Qatar, A meeting of SIGDAT, a Special Interest Group of the ACL, pages 1858-1869. ACL.   
Dat Quoc Nguyen and Karin Verspoor. 2O19.End-to-end neural relation extraction using deep biaffine attention. In Leif Azzopardi, Benno Stein,Norbert Fuhr,Philipp Mayr, Claudia Hauff,and Djoerd Hiemstra, editors, Advances in Information Retrieval - 4lst European Conferenceon IR Research, ECIR2Ol9,Cologne,Germany, April 14-18, 2019, Proceedings, Part I, volume 11437 of Lecture Notes in Computer Science, pages 729-738. Springer.   
Dan Roth and Wen-tau Yih. 2O04.A linear programming formulation for global inference in natural language tasks.In Hwee Tou $\mathrm { N g }$ and Ellen Riloff,editors,Proceedings of the Eighth Conference on Computational Natural Language Learning, CoNLL2004, Held in cooperation with HLT-NAACL 2004, Boston, Massachusets, USA, May 6-7, 2004, pages 1-8. ACL.   
Tung Tran and Ramakanth Kavuluru. 2O19. Neural metric learning for fast end-to-end relation extraction. arXiv preprint arXiv:1905.07458.   
Ashish Vaswani, Noam Shazeer, Niki Parmar, Jakob Uszkoreit, Llion Jones,Aidan N. Gomez,Lukasz Kaiser, and llia Polosukhin._2017.Attention is allyou need.In Isabelle Guyon, Ulrike von Luxburg,Samy Bengio, Hanna M. Wallach, Rob Fergus, S. V. N. Vishwanathan,and Roman Garnett, editors,Advances in Neural Information Processing Systems 30: Annual Conference on Neural Information Processing Systems 2017, 4-9 December 2017, Long Beach, CA, USA, pages 5998-6008.   
Patrick Verga,Emma Strubell，and Andrew McCallum.2018. Simultaneously self-attending to all mentions for full-abstract biological relation extraction.In Marilyn A. Walker, Heng Ji,and Amanda Stent, editors, Proceedings of the 2Ol8 Conference of the North American Chapter of the Association for Computational Linguistics: Human Language Technologies,NAACL-HL2O18,New Orleans,Louisiana, USA, June1-6,2018, Volume 1 (Long Papers), pages 872-884. Association for Computational Linguistics.   
David Wadden, Ulme Wennberg,Yi Luan,and Hannaneh Hajishirzi.2O19.Entity,relation,and event extraction with contextualized span representations. In Kentaro Inui, Jing Jiang, Vincent Ng,and Xiaojun Wan,editors, Proceedings of the 2Ol9 Conference on Empirical Methods in Natural Language Processing and the 9th International Joint Conference on Natural Language Processing, EMNLP-IJCNLP 2O19, Hong Kong, China, November 3-7, 2019, pages 5783-5788. Association for Computational Linguistics.   
Haoyu Wang,Ming Tan, Mo Yu, Shiyu Chang,Dakuo Wang, Kun Xu, Xiaoxiao Guo,and Saloni Potdar. 2019. Extracting multiple-relations in one-pass with pre-trained transformers. In Anna Korhonen,David R.Traum, and Lluis Marquez,editors,Proceedings of the 57th Conference of the Association for Computational Linguistics,ACL20l9,Florence,ItalyJuly28-August2,2019,Volume1: LongPapers,pages 1371-1377.Association for Computational Linguistics.   
Daojian Zeng,Kang Liu, Siwei Lai,Guangyou Zhou,and Jun Zhao.2O14.Relation clasification via convolutional deep neural network．In Jan Hajic and Junichi Tsujii,editors,COLING 2O14,25th International Conference on Computational Linguistics,Proceedings of the Conference: Technical Papers,August 23-29, 2014,Dublin, Ireland, pages 2335-2344. ACL.   
Dongxu Zhang and Dong Wang.2O15.Relation classification via recurrent neural network. arXiv preprint arXiv:1508.01006,abs/1508.01006.   
Suncong Zheng,Feng Wang,Hongyun Bao, Yuexing Hao,Peng Zhou,and Bo Xu.2O17. Joint extraction of entities and relations based on a novel tagging scheme. In Regina Barzilay and Min-Yen Kan, editors,Proceedings ofthe 55th Annual Meeting of the Association for Computational Linguistics,ACL 2Ol7, Vancouver, Canada, July 30 - August 4, Volume 1: Long Papers, pages 1227-1236. Association for Computational Linguistics.   
Peng Zhou,Suncong Zheng,Jiaming Xu,Zhenyu Qi,Hongyun Bao,and Bo Xu.2O17.Joint extraction of multiple relations and entities by using a hybrid neural network. In Maosong Sun, Xiaojie Wang,Baobao Chang,and Deyi Xiong, editors, Chinese Computational Linguistics and Natural Language Processing Based on Naturally Annotated Big Data - 16th China National Conference, CCL 2Ol7,- and - 5th International Symposium, NLPNABD 2017,Nanjing, China,October 13-15,2017,Proceedings,volume 10565 of Lecture Notes in Computer Science, pages 135-146. Springer.