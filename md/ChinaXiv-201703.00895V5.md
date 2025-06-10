# Sharing deep generative representation for perceived image reconstruction from human brain activity

Changde $\mathbf { D } \mathbf { u } ^ { 1 }$ , Changying $\mathbf { D } \mathbf { u } ^ { 2 }$ , Huiguang $\mathbf { H e } ^ { 1 , 3 }$

1Research Center for Brain-Inspired Intelligence, Institute of Automation, Chinese Academy of Sciences (CAS),Beijing, China 2Laboratory of Parallel Software and Computational Science, Institute of Software,CAS, Beijing, China 3Center for Excellence in Brain Science and Intelligence Technology, CAS, Shanghai, China {duchangde2O16, huiguang.he $\} \textcircled { a }$ ia.ac.cn, changying@iscas.ac.cn

# Abstract

Decoding human brain activities via functional magnetic resonance imaging (fMRI) has gained increasing attention in recent years. While encouraging results have been reported in brain states classification tasks,reconstructing the details of human visual experience still remains difficult. Two main challenges that hinder the development of effective models are the perplexing fMRI measurement noise and the high dimensionality of limited data instances.Existing methods generally suffer from one or both of these issues and yield dissatisfactory results.In this paper, we tackle this problem by casting the reconstruction of visual stimulus as the Bayesian inference of missing view inamultiview latent variable model. Sharing a common latent representation, our joint generative model of external stimulus and brain response is not only “deep" in extracting nonlinear features from visual images, but also powerful in capturing correlations among voxel activities of fMRI recordings.The nonlinearity and deep structure endow our model with strong representation ability,while the correlations of voxel activities are critical for suppressing noise and improving prediction.We devise an efficient variational Bayesian method to infer the latent variables and the model parameters.To further improve the reconstruction accuracy, the latent representations of testing instances are enforced to be close to that of their neighbours from the training set via posterior regularization.Experiments on three fMRI recording datasets demonstrate that our approach can more accurately reconstruct visual stimuli.

# 1Introduction

Brain decoding，which aims to predict the information about external stimuli using brain activities,plays an importantrole in brain-machine interfaces(BMIs).Recent developments in this area have shown promising results [Schoenmakers et al.,2015; Lee and Kuhl, 2016l． However,most previous researches only focus their attention on the prediction of the category of presented stimulus [Van Gerven et al., 2010a; Ng and Abugharbieh,2O11; Damarla and Just, 2013;

Elahe'Yargholi,2O16].Accurate reconstruction of the visual stimuli from brain activities stilllacks adequate examination and requires plenty of efforts to improve. Two main challenges that hinder the development of effective models are the perplexing measurement noise of functional magnetic resonance imaging (fMRI) and the high dimensionality of limited data instances.Existing methods generally suffer from one or both of these issues and yield dissatisfactoryresults.

Fujiwara et al. has proposed to use Bayesian canonical correlation analysis(BCCA)for building the reconstruction model,where image bases are automatically extracted from the measured data[Fujiwara et al.,2O13].As a latent variable model interpretation of non-probabilistic CCA,BCCA assumes linear observation model for visual images and spherical covariance for the Gaussian distribution of voxel activities.In practice,however, linear observation model for visual images has limited representation power,and spherical covariance can not capture the correlations among voxel activities. Since the measurement noises are ubiquitous in voxel activities,utilizing the correlations among voxel activities would be critical for suppressing noise and improving prediction performance.

On the other hand,introducing deep structure into multiview representation learning is attracting more and more attentions recently [Wang et al.,2O15; Chandar et al.,2016]. Deep canonically correlated autoencoders (DCCAE),which consists of two deep autoencoders and optimizes the combinationof canonical correlation between the learned bottleneck representations and the reconstruction errors of the autoencoders,can extract nonlinear features from both views and reconstruct each view by the correlational bottleneck representations[Wang et al.,2O15].Nevertheless,DCCAE did not consider the cross-reconstruction between two views, which limits its effectiveness in applications where a missing view needs to be reconstructed from the existing one.To our knowledge,no deep multiview learning model with shared generative latent representation has been designed specifically for missing view reconstruction.

Focusing on these problems,we present a deep generative multiview model (DGMM),where we cast the reconstruction of perceived image as the Bayesian inference of the missing view. Sharing a common latent representation,DGMM allows us to generate visual images and fMRI activity patterns simultaneously.For visual images,unlike BCCA,we explore nonlinear observation models parameterized by deep neural networks (DNNs),which can be multi-layered perceptrons(MLPs) or convolutional neural networks(CNNs).This nonlinearity and deep structure endow our model with strong representation ability.For fMRI activity patterns,we adopt a full covariance matrix for the Gaussian distribution of voxel activities.While the full covariance matrix has the advantage of capturing the correlations among voxels,it results in severe computational issues.To reduce the complexity,we impose a low-rank assumption on the covariance matrix.This is beneficial to suppressing noise and improving prediction performance.Furthermore,we devise an efficient mean-field variational inference method to infer the latent variables and the model parameters.To further improve the reconstruction accuracy,the latent representations of testing instances are enforcedto be close to that of theirneighbours from the training set via posterior regularization[Zhu et al.,2O14]. Compared with the non-probabilistic deep multiview representation learning models mentioned above [Wang et al., 2015; Chandar et al.,2O16],our Bayesian model has the inherent advantage of avoiding overfitting to small training set by model averaging. Finally,extensive experimental comparisons on three fMRI recording datasets demonstrate that our approach can reconstruct visual images from fMRI measurements more accurately.

# 2 Related work

In the literature of brain decoding,there are a relatively limited number of studies reporting perceived image reconstructions to date. Miyawaki et al. reconstructed the lower-order information such as binary contrast patterns using a combination of multi-scale local image bases whose shapes are predefined [Miyawaki et al.,2OO8]. Van Gerven et al. reconstructed handwritten digits using deep be lief networks [Van Gerven et al.，2O1Ob]. Schoenmakers et al.reconstructed handwritten characters using a straightforward linear Gaussian approach [Schoenmakers et al.,2O13l. Fujiwara et al. proposed to build the reconstruction model in which image bases can be automatically estimated by Bayesian canonical correlation analysis(BCCA)[Fujiwara et al.,2O13]. In addition,there are works trying to reconstruct movie clips [Nishimoto et al.,2011; Haiguang Wen and Liu,2016].

Though a similar strategy to our work has been used by Fujiwara et al. [Fujiwara et al.,2O13] for visual image reconstruction,its linear observation model for visual images has limited representation power in practice. Several recently proposed deep multiview representation learning models can provide a service to visual image reconstruction [Wang et al., 2015;Chandar et al.,2O16l. For example,deep canonically correlated autoencoders(DCCAE）with nonlinear observation models for both views has good ability to learn deep correlational representations and reconstruct each view using the learned representations respectively [Wang et al.,2015]. Compared with DCCAE,correlational neural networks (CorrNet) further considered the cross-reconstruction between two views [Chandar et al.,2016]. However, directly applying the nonlinear maps of DCCAE and CorrNet to limited noisy brain activities is prone to overfitting

Inspired by recent developments in deep generative models such as variational autoencoders(VAE）[Kingma and Welling,2O14], we present a deep generative multiview model(DGMM),which can be viewed as a nonlinear extension of the linear method BCCA. To the best of our knowledge, this paper is the first to study visual image reconstruction via Bayesian deep learning.

# 3Perceived image reconstruction with DGMM

In this section,we cast the reconstruction of perceived images from human brain activity as the Bayesian inference of missing viewina multiviewlatent variable model.

Assume the training set consists of paired observations from two distinct views $( \mathbf { X } , \mathbf { Y } )$ ，denoted by $( \mathbf { x } _ { 1 } , \mathbf { y } _ { 1 } ) , \ldots ,$ $( { \bf x } _ { N } , { \bf y } _ { N } ) _ { ; }$ where $N$ is the training set size, $\mathbf { x } _ { i } \in \mathbb { R } ^ { D _ { 1 } }$ and $\mathbf { y } _ { i } ~ \in ~ \mathbb { R } ^ { D _ { 2 } }$ for $i ~ = ~ 1 , \dots , N$ .Here $\textbf { X } \in \ \mathbb { R } ^ { D _ { 1 } \times N }$ and $\textbf { Y } \in \ \mathbb { R } ^ { D _ { 2 } \times N }$ denote the visual images and fMRI activity patterns,respectively. The presence of paired two-view data presents an opportunity to learn better representations by analyzing both views simultaneously. Therefore,we introduce the shared latent variables $\mathbf { Z } \in \dot { \mathbb { R } } ^ { K \times N }$ to relate the visual images $\mathbf { X }$ to the fMRI activity patterns $\mathbf { Y }$ . The shared latent variables are treated as the following Gaussian prior distribution,

$$
\begin{array} { r } { p ( \mathbf { Z } ) = \prod _ { i = 1 } ^ { N } \mathcal { N } \left( \mathbf { z } _ { i } | \mathbf { 0 } , \mathbf { I } \right) . } \end{array}
$$

Since the visual image and associated fMRI activity pattern are assumed to be generated from the same latent variables, we have two likelihood functions. One is for visual images, and the other is for fMRI activity patterns.

# 3.1Deep generative model for perceived images

When observation noises for image pixels are assumed to follow a Gaussian distribution with zero mean and diagonal covariance, the likelihood function of visual images is

$$
\begin{array} { r } { p _ { \theta } ( \mathbf { X } \vert \mathbf { Z } ) = \prod _ { i = 1 } ^ { N } \mathcal { N } \left( \mathbf { x } _ { i } \vert \pmb { \mu _ { \mathbf { x } } } ( \mathbf { z } _ { i } ) , \ \mathrm { d i a g } ( \pmb { \sigma _ { \mathbf { x } } ^ { 2 } } ( \mathbf { z } _ { i } ) ) \right) , } \end{array}
$$

where the mean $\pmb { \mu _ { \mathbf { x } } ( \mathbf { z } _ { i } ) }$ and covariance $\pmb { \sigma } _ { \mathbf { x } } ^ { 2 } ( \mathbf { z } _ { i } )$ are nonlinear functions of the latent variables $\mathbf { z } _ { i }$ ．To allow for second moment of the data to be captured by the density model, we choose these nonlinear functions to be deep neural networks(DNNs),which is refer to as the generative network, $g ( \mathbf { z } )$ parameterized by $\pmb \theta$ .Here the DNNs can be multilayered perceptrons (MLPs) or convolutional neural networks (CNNs).Compared with linear observation model, DNNs can extract nonlinear features from visual images and capture the stages of human visual processing from early visual areas towards the ventral streams [Güclui and van Gerven,2015; Cichy et al., 2O16]. This nonlinearity and deep structure endow our model with strong representation ability.

# 3.2 Generative model for fMRI activity patterns

fMRI voxels are generally highly correlated,and the correlation can carry relevant information about stimuli or tasks, evenin the absence of information in individual voxels[Yamashita et al.,20O8;Hossein-Zadeh andothers,2016].However,most existing methods [Fujiwara et al.,2O13;Schoenmakers et al.,2O13] simply assume a spherical or diagonal covariance for the Gaussian distribution of voxel activities thus ignoring any correlations among voxels. Unlike them, we assume the observation noises of voxel activities follow a Gaussian distribution with zero mean and full covariance matrix.While this difference might seem minor, it is critical for the model to be able to suppress noise and improve prediction performance.In addition,although nonlinear transformations for fMRI activity patterns are more powerful than linear transformations (in terms of the types of features they can learn), extant multi-voxel pattern analysis (MVPA) studies have not found aclearperformance benefit fornonlinear versus linear transformations.Therefore,weassume thelikelihoodfunction of fMRI activity patterns is

![](images/e5665c618287378687ae3731518fb5a4c14c40b5e7f0873898e84d919cfef1ef.jpg)  
Figure1:Graphical models forDGMM.(a) Directly uses the full covariance matrix $\Psi$ . (b) Imposing a low-rank assump tion on $\Psi$ 0 $\mathbf { \Delta } \Psi = \mathbf { H } ^ { \top } \mathbf { H } + \gamma ^ { - 1 } \mathbf { I } )$ ：

$$
\begin{array} { r } { p ( \mathbf { Y } | \mathbf { Z } ) = \prod _ { i = 1 } ^ { N } \mathcal { N } \left( \mathbf { y } _ { i } | \mathbf { B } ^ { \top } \mathbf { z } _ { i } , \boldsymbol { \Psi } \right) . } \end{array}
$$

The model should be further complemented with priors for the _projection matrix $\mathbf { B }$ and the covariance matrix $\Psi \in$ $\mathbb { R } ^ { D _ { 2 } \times D _ { 2 } ^ { * } }$ . Popular choices would be automatic relevance determination (ARD) prior and Wishart distribution for $\mathbf { B }$ and $\Psi ^ { - 1 }$ , respectively,

$$
\begin{array} { r l } & { p ( \pmb { \tau } ) = \prod _ { j = 1 } ^ { D _ { 2 } } \mathcal { G } \left( \tau _ { j } | \alpha _ { \tau } , \beta _ { \tau } \right) } \\ & { p ( \mathbf { B } | \pmb { \tau } ) = \prod _ { j = 1 } ^ { D _ { 2 } } \mathcal { N } \left( \mathbf { b } _ { j } | \mathbf { 0 } , \tau _ { j } ^ { - 1 } \mathbf { I } \right) } \\ & { p ( \pmb { \Psi } ^ { - 1 } ) = \mathcal { W } \left( \pmb { \Psi } ^ { - 1 } | \mathbf { V } , n _ { 0 } \right) , } \end{array}
$$

where $\mathcal { G } \left( \cdot | \alpha , \beta \right)$ denotes gamma distribution with shape parameter $\alpha$ and rate parameter ${ \boldsymbol { \beta } } , \mathbf { V }$ and $n _ { 0 }$ denote the scale matrix and degrees of freedom for Wishart distribution,respectively.

While the above model has the advantage of capturing the correlations among voxels,it resultsin severe computational issues(the cost is cubic asafunction of $D _ { 2 }$ ).Fortunately,the problem of inferring high-dimensional covariance matrix $\Psi$ can be solved by introducing auxiliary latent variables $\bar { \mathbf { Z } } \in$ $\mathbb { R } ^ { \bar { K } \times N }$ [Archambeau and Bach, 2009],

$$
\begin{array} { r } { p ( \bar { \bf Z } ) = \prod _ { i = 1 } ^ { N } \mathcal { N } \left( \bar { \bf z } _ { i } |                \mathbf { 0 } , \mathbf { I } \right) , } \end{array}
$$

and rewriting the likelihood function in Eq.(3) as

$$
\begin{array} { r } { p ( \mathbf { Y } | \mathbf { Z } , \bar { \mathbf { Z } } ) = \prod _ { i = 1 } ^ { N } \mathcal { N } \left( \mathbf { y } _ { i } | \mathbf { B } ^ { \top } \mathbf { z } _ { i } + \mathbf { H } ^ { \top } \bar { \mathbf { z } } _ { i } , \gamma ^ { - 1 } \mathbf { I } \right) , } \end{array}
$$

where ARD prior and simple gamma prior can be set for the extra projection matrix $\bar { \mathbf { H } } \bar { \in } \bar { \mathbb { R } } ^ { \bar { K } \times D _ { 2 } }$ and variance parameter $\gamma$ ,respectively,

$$
\begin{array} { r l } & { p ( \pmb { \eta } ) = \prod _ { j = 1 } ^ { D _ { 2 } } \mathcal { G } \left( \eta _ { j } | \alpha _ { \eta } , \beta _ { \eta } \right) } \\ & { p ( \mathbf { H } | \pmb { \eta } ) = \prod _ { j = 1 } ^ { D _ { 2 } } \mathcal { N } \left( \mathbf { h } _ { j } | \mathbf { 0 } , \eta _ { j } ^ { - 1 } \mathbf { I } \right) } \\ & { p ( \gamma ) = \mathcal { G } \left( \gamma | \alpha _ { \gamma } , \beta _ { \gamma } \right) . } \end{array}
$$

The graphical models of DGMM are shown in Fig.1.Note thatsparsity of the projectionmatrices $\mathbf { B }$ and $\mathbf { H }$ can be tuned by assigning suitable values to the hyper-parameters $( \alpha _ { \tau } , \beta _ { \tau } )$ and $( \alpha _ { \eta } , \beta _ { \eta } )$ ,respectively.

By integrating out auxiliary latent variables $\bar { \mathbf Z }$ ,Eq.(6) can be shown to be equivalent to imposing a low-rank assumption on the covariance matrix $\Psi$ in Eq.(3) $( \boldsymbol { \Psi } = \mathbf { H } ^ { \top } \mathbf { H } + \gamma ^ { - 1 } \mathbf { I } )$ which allows decreasing the computational complexity. From another perspective, this low-rank assumption produces a full factorization of the variation in fMRI data into shared components $\mathbf { Z }$ and private components $\bar { \mathbf Z }$ ，The ability to identify whatis shared and what is non-shared makes our model be good at suppressing noise and improving prediction performance.

As short-hand notations,all hyper-parameters in the model will be denoted by $\Omega = \{ \alpha _ { \tau } , \beta _ { \tau } , \alpha _ { \eta } , \beta _ { \eta } , \alpha _ { \gamma } , \beta _ { \gamma } \}$ ，while the priors by $\Xi = \{ \tau , \eta , \gamma \}$ and the remaining variables by $\boldsymbol \Theta \doteq \{ { \bf B } , { \bf { \bar { H } } } , { \bf { Z } } , { \bf { \bar { Z } } } \}$ .Dependence on $\Omega$ is omitted for clarity throughout the paper. Then we can get the following posterior distribution using Bayes’ rule

$$
p ( \Theta , \Xi | \mathbf { X } , \mathbf { Y } ) = \frac { p _ { \theta } ( \mathbf { X } | \mathbf { Z } ) p ( \mathbf { Y } | \mathbf { Z } , \bar { \mathbf { Z } } ) p ( \Theta | \Xi ) p ( \Xi ) } { p _ { \theta } ( \mathbf { X } , \mathbf { Y } ) } ,
$$

where $p _ { \theta } ( \mathbf { X } , \mathbf { Y } )$ is the normalization constant.

# 4Variational posterior inference

Given above generative model,exact inference is intractable.Here we formulate a mean-field variational approximate inference method to infer the latent variables and model parameters.Specifically,we assume there are a family of factorable and free-form (except for $q ( \mathbf { Z } ) .$ ）variational distributions

$$
q ( \Theta , \Xi ) = q ( { \bf B } ) q ( { \bf H } ) q ( { \bf Z } ) q ( \bar { \bf Z } ) q ( \tau ) q ( \eta ) q ( \gamma ) ,
$$

and define $q ( \mathbf { Z } )$ as a product of multivariate Gaussian distributions with diagonal covariance',i.e.,

$$
q ( \mathbf { Z } ) = \prod _ { i = 1 } ^ { N } q _ { \varphi } ( \mathbf { z } _ { i } | \mathbf { x } _ { i } ) = \prod _ { i = 1 } ^ { N } \mathcal { N } \left( \mathbf { z } _ { i } | \mu _ { \mathbf { z } } ( \mathbf { x } _ { i } ) , \mathrm { d i a g } ( \pmb { \sigma } _ { \mathbf { z } } ^ { 2 } ( \mathbf { x } _ { i } ) ) \right) ,
$$

where the mean $\pmb { \mu _ { \mathbf { z } } } ( \mathbf { x } _ { i } ) \ = \ [ \mu _ { \mathbf { z } i 1 } , \dots , \mu _ { \mathbf { z } i K } ] ^ { \top }$ and covariance diag(σ²(xi)） = diag(²i1, are outputs of the recognition network specified by another DNN with parameters $\varphi$ . Then the objective is to get the optimal one which minimizes the Kullback-Leibler (KL) divergence between the approximating distribution and the target posterior, i.e.,

$$
\operatorname* { m i n } _ { \boldsymbol { q } ( \Theta , \Xi ) \in \mathcal { P } } \mathrm { K L } \left( \boldsymbol { q } ( \Theta , \Xi ) \big | \big | p _ { \theta } \big ( \Theta , \Xi \big | \mathbf { X } , \mathbf { Y } \big ) \right) ,
$$

where $\mathcal { P }$ is the space of probability distributions.Equivalently,we can also bound the marginal likelihood:

$$
\begin{array} { r l } & { \log p _ { \theta } ( \mathbf { X } , \mathbf { Y } ) } \\ & { = \mathbb { E } _ { q ( \Theta , \Xi ) } [ \log p _ { \theta } ( \mathbf { X } , \mathbf { Y } , \Theta , \Xi ) - \log q ( \Theta , \Xi ) ] } \\ & { \phantom { = } + \mathrm { K L } \left( q ( \Theta , \Xi ) \lVert p _ { \theta } ( \Theta , \Xi | \mathbf { X } , \mathbf { Y } ) \right) } \\ & { \geq \mathbb { E } _ { q ( \Theta , \Xi ) } [ \log p _ { \theta } ( \mathbf { X } , \mathbf { Y } , \Theta , \Xi ) - \log q ( \Theta , \Xi ) ] } \\ & { = \int q ( \Theta , \Xi ) [ \log \frac { p ( \Theta , \Xi ) } { q ( \Theta , \Xi ) } + \log p _ { \theta } ( \mathbf { X } | \Theta , \Xi ) } \\ & { \phantom { = } + \log p ( \mathbf { Y } | \Theta , \Xi ) ] d \Theta d \Xi } \\ & { = \mathcal { L } _ { P } ( \Theta , \Xi , \mathbf { X } , \mathbf { Y } ) + \mathcal { L } _ { \mathcal { X } } ( \Theta , \Xi , \mathbf { X } , \mathbf { Y } ) + \mathcal { L } _ { \mathcal { Y } } ( \Theta , \Xi , \mathbf { X } , \mathbf { Y } ) } \\ & { = \mathcal { L } ( \Theta , \Xi , \mathbf { X } , \mathbf { Y } ) } \end{array}
$$

where we used the fact that KL divergence is guaranteed to be non-negative,and

$$
\begin{array} { r l } & { \mathcal { L } _ { \mathcal { P } } ( \boldsymbol { \Theta } , \boldsymbol { \Xi } , \mathbf { X } , \mathbf { Y } ) = - D _ { K L } \big ( q ( \boldsymbol { \Theta } , \boldsymbol { \Xi } ) \big | | p ( \boldsymbol { \Theta } , \boldsymbol { \Xi } ) \big ) } \\ & { \mathcal { L } _ { \mathcal { X } } ( \boldsymbol { \Theta } , \boldsymbol { \Xi } , \mathbf { X } , \mathbf { Y } ) = \mathbb { E } _ { q ( \boldsymbol { \Theta } , \boldsymbol { \Xi } ) } \big [ \log p _ { \boldsymbol { \theta } } ( \mathbf { X } | \boldsymbol { \Theta } , \boldsymbol { \Xi } ) \big ] } \\ & { \mathcal { L } _ { \mathcal { Y } } ( \boldsymbol { \Theta } , \boldsymbol { \Xi } , \mathbf { X } , \mathbf { Y } ) = \mathbb { E } _ { q ( \boldsymbol { \Theta } , \boldsymbol { \Xi } ) } \big [ \log p ( \mathbf { Y } | \boldsymbol { \Theta } , \boldsymbol { \Xi } ) \big ] . } \end{array}
$$

Intuitively, $\mathcal { L } _ { \mathcal { X } }$ and $\mathcal { L } _ { \mathcal { Y } }$ can be interpreted as the (negative) expected reconstruction errors of visual images and fMRI activity patterns,respectively. Maximizing this lower bound strikes a balance between minimizing reconstruction errors of two views and minimizing the $\mathrm { K L }$ divergence between the approximate posterior and the prior.

# 4.1Learning $\theta , \varphi$ and Z

Given the fixed-form approximate posterior distribution for factor $\mathbf { Z }$ ， $\mathcal { L } _ { \mathcal { P } } ( \mathbf { Z } , \mathbf { X } , \mathbf { Y } )$ can be computed exactly as:

$$
\begin{array} { l } { \displaystyle \mathcal { L } _ { \mathcal { P } } ( \mathbf { Z } , \mathbf { X } , \mathbf { Y } ) = \sum _ { i = 1 } ^ { N } { - D _ { K L } \big [ q _ { \varphi } ( \mathbf { z } _ { i } | \mathbf { x } _ { i } ) | | p ( \mathbf { z } _ { i } ) \big ] } } \\ { \displaystyle = \frac { 1 } { 2 } \sum _ { i = 1 } ^ { N } { \sum _ { k = 1 } ^ { K } \big ( 1 + \log ( \sigma _ { \mathbf { z } _ { i k } } ^ { 2 } ) - { \mu _ { \mathbf { z } _ { i k } } } ^ { 2 } - \sigma _ { \mathbf { z } _ { i k } } ^ { 2 } \big ) } . } \end{array}
$$

On the other hand, $\mathcal { L } _ { \mathcal { X } } ( \mathbf { Z } , \mathbf { X } , \mathbf { Y } )$ and $\mathcal { L } _ { \mathcal { Y } } ( \mathbf { Z } , \mathbf { X } , \mathbf { Y } )$ can be approximated by Monte-Carlo sampling[Kingma and Welling，2014;Kingma et al.,2014]. Instead of sampling directly from $q _ { \varphi } ( \mathbf { z } _ { i } | \mathbf { x } _ { i } )$ ， $\mathbf { z } _ { i }$ is computed as a deterministic function of $\mathbf { x } _ { i }$ and some noise term such that $\mathbf { z } _ { i }$ has the desired distribution. Assuming we draw $L$ samples, $\mathbf { z } _ { i } ^ { ( l ) }$ $( l = 1 , \ldots , L )$ can be expressed as

$$
\begin{array} { r } { \mathbf { z } _ { i } ^ { ( l ) } = \pmb { \mu } _ { \mathbf { z } } ( \mathbf { x } _ { i } ) + \pmb { \sigma } _ { \mathbf { z } } ( \mathbf { x } _ { i } ) \odot \pmb { \epsilon } ^ { ( l ) } , } \end{array}
$$

where $\epsilon ^ { ( l ) } \sim \mathcal { N } \left( \mathbf { 0 } , \mathbf { I } \right)$ and $\odot$ denotes element-wise multiplication.Then the resulting Monte-Carlo approximations are

$$
\begin{array} { r } { \mathcal { L } _ { \mathcal { X } } ( \mathbf { Z } , \mathbf { X } , \mathbf { Y } ) = \sum _ { i = 1 } ^ { N } \{ \mathbb { E } _ { q ( \mathbf { z } _ { i } ) } \left[ \log p _ { \theta } ( \mathbf { x } _ { i } | \mathbf { z } _ { i } ) \right] \} } \\ { = \frac { 1 } { L } \sum _ { i = 1 } ^ { N } \sum _ { l = 1 } ^ { L } \log p _ { \theta } ( \mathbf { x } _ { i } | \mathbf { z } _ { i } ^ { ( l ) } ) , } \end{array}
$$

$$
\begin{array} { r } { \mathcal { L } _ { \mathcal { V } } ( \mathbf { Z } , \mathbf { X } , \mathbf { Y } ) = \sum _ { i = 1 } ^ { N } \{ \mathbb { E } _ { q ( \mathbf { z } _ { i } ) } \left[ \log p ( \mathbf { y } _ { i } | \mathbf { z } _ { i } ) \right] \} } \\ { = \frac { 1 } { L } \sum _ { i = 1 } ^ { N } \sum _ { l = 1 } ^ { L } \log p ( \mathbf { y } _ { i } | \mathbf { z } _ { i } ^ { ( l ) } ) . } \end{array}
$$

Finally, the parameters of DNNs ( $\pmb \theta$ and $\varphi$ )can be obtained by optimizing the objective function $\begin{array} { r } { \mathcal { L } ( \mathbf { Z } , \mathbf { X } , \mathbf { Y } ) } \end{array}$ (based on minibatches） using the standard stochastic gradient based optimization methods such as SGD,RMSprop or AdaGrad [Duchi et al., 2011].

# 4.2Learning

For a specific factor $\pi$ (except for $\mathbf { Z }$ ), it can be shown that when keeping all other factors fixed the optimal distribution $q ^ { * } ( \pi )$ satisfies

$$
\begin{array} { r } { q ^ { * } ( \pi ) \propto \exp \left\{ \mathbb { E } _ { q ( \{ \Theta , \Xi \} \backslash \pi ) } [ \log p _ { \theta } ( \mathbf { X } , \mathbf { Y } , \Theta , \Xi ) ] \right\} . } \end{array}
$$

For our model, thanks to the conjugacy, the resulting optimal distribution of each factor follows the same distribution as the corresponding factor.

The optimal distributions of the projection parameters can be found as a product of multivariate Gaussian distributions:

$$
\begin{array} { r l } & { q ^ { * } ( \mathbf { B } ) = \prod _ { j = 1 } ^ { D _ { 2 } } \mathcal { N } \left( \mathbf { b } _ { j } | \pmb { \mu _ { \mathbf { b } _ { j } } } , \left[ \langle \tau _ { j } \rangle \mathbf { I } + \langle \gamma \rangle \langle \mathbf { Z } \mathbf { Z } ^ { \top } \rangle \right] ^ { - 1 } \right) } \\ & { q ^ { * } ( \mathbf { H } ) = \prod _ { j = 1 } ^ { D _ { 2 } } \mathcal { N } \left( \mathbf { h } _ { j } | \pmb { \mu _ { \mathbf { h } _ { j } } } , \left[ \langle \eta _ { j } \rangle \mathbf { I } + \langle \gamma \rangle \langle \bar { \mathbf { Z } } \bar { \mathbf { Z } } ^ { \top } \rangle \right] ^ { - 1 } \right) } \end{array}
$$

where notation $\langle \cdot \rangle$ denotes the expectation operator, i.e., $\langle \pi \rangle$ means the expectation of $\pi$ over its current optimal distribution,and

$$
\begin{array} { r l } & { \pmb { \mu _ { \mathbf { b } _ { j } } } = \pmb { \Sigma _ { \mathbf { b } _ { j } } } \sum _ { i = 1 } ^ { N } \langle \gamma \rangle \big ( y _ { i j } - \langle \mathbf { h } _ { j } ^ { \top } \rangle \langle \bar { \mathbf { z } } _ { i } \rangle \big ) \langle \mathbf { z } _ { i } \rangle } \\ & { \pmb { \mu _ { \mathbf { h } _ { j } } } = \pmb { \Sigma _ { \mathbf { h } _ { j } } } \sum _ { i = 1 } ^ { N } \langle \gamma \rangle \big ( y _ { i j } - \langle \mathbf { b } _ { j } ^ { \top } \rangle \langle \mathbf { z } _ { i } \rangle \big ) \langle \bar { \mathbf { z } } _ { i } \rangle . } \end{array}
$$

The optimal distribution of the auxiliary latent variables can also be found as a product of multivariate Gaussian distributions:

$$
\begin{array} { r } { q ^ { * } ( \bar { \mathbf { Z } } ) = \prod _ { i = 1 } ^ { N } \mathcal { N } \left( \bar { \mathbf { z } } _ { i } | \pmb { \mu } _ { \bar { \mathbf { z } } _ { i } } , \left[ \mathbf { I } + \langle \gamma \rangle \langle \mathbf { H } \mathbf { H } ^ { \top } \rangle \right] ^ { - 1 } \right) } \end{array}
$$

where

$$
\begin{array} { r } { \pmb { \mu _ { \bar { \mathbf { z } } _ { i } } } = \pmb { \Sigma _ { \bar { \mathbf { z } } _ { i } } } \sum _ { j = 1 } ^ { D _ { 2 } } \langle \gamma \rangle \big ( y _ { i j } - \langle \mathbf { b } _ { j } ^ { \top } \rangle \langle \mathbf { z } _ { i } \rangle \big ) \langle \mathbf { h } _ { j } \rangle . } \end{array}
$$

The optimal distributions of the precision variables can be formulated as:

$$
\begin{array} { r l } { q ^ { * } ( \pmb { \tau } ) } & { = \prod _ { j = 1 } ^ { D _ { 2 } } \mathcal { G } \left( \tau _ { j } | \alpha _ { \tau } + \frac { K } { 2 } , \beta _ { \tau } + \frac { 1 } { 2 } \langle \mathbf { b } _ { j } ^ { \top } \mathbf { b } _ { j } \rangle \right) } \\ { q ^ { * } ( \pmb { \eta } ) } & { = \prod _ { j = 1 } ^ { D _ { 2 } } \mathcal { G } \left( \eta _ { j } | \alpha _ { \eta } + \frac { \bar { K } } { 2 } , \beta _ { \eta } + \frac { 1 } { 2 } \langle \mathbf { h } _ { j } ^ { \top } \mathbf { h } _ { j } \rangle \right) } \\ { q ^ { * } ( \gamma ) } & { = \mathcal { G } \left( \gamma | \alpha _ { \gamma } + \frac { N D _ { 2 } } { 2 } , \beta _ { \gamma } + \frac { 1 } { 2 } \sum _ { i = 1 } ^ { N } \sum _ { j = 1 } ^ { D _ { 2 } } \delta _ { i j } ^ { 2 } \right) } \end{array}
$$

where $\delta _ { i j } = y _ { i j } - \langle \mathbf { b } _ { j } ^ { \top } \rangle \langle \mathbf { z } _ { i } \rangle - \langle \mathbf { h } _ { j } ^ { \top } \rangle \langle \bar { \mathbf { z } } _ { i } \rangle$

# 4.3 Convergence

The inference mechanism sequentially updates the optimal distributions of the latent variables and the model parameters until convergence,which is guaranteed because the KL divergence is convex with respect to each of the factors.

# 4.4 Prediction

Using the estimated parameters,we can derive the predictive distribution for a visual image $\mathbf { x } _ { \mathrm { p r e d } }$ given a new brain activity $\mathbf { y } _ { \star }$ .The predictive distribution $p ( \mathbf { x } _ { \mathrm { p r e d } } | \mathbf { y } _ { \star } )$ can be formulated as follows,

$$
p ( \mathbf { x } _ { \mathrm { p r e d } } | \mathbf { y } _ { \star } ) = \int p _ { \theta } ( \mathbf { x } _ { \mathrm { p r e d } } | \mathbf { z } _ { \star } ) p ( \mathbf { z } _ { \star } | \mathbf { y } _ { \star } ) d \mathbf { z } _ { \star }
$$

where the posterior distribution of latent variables $p ( \mathbf { z } _ { \star } | \mathbf { y } _ { \star } )$ can be derived by

$$
\begin{array} { r } { p ( \mathbf { z } _ { \star } | \mathbf { y } _ { \star } ) = \displaystyle \int p ( \mathbf { y } _ { \star } | \mathbf { z } _ { \star } , \bar { \mathbf { z } } _ { \star } , \mathbf { B } , \mathbf { H } , \gamma ) p ( \mathbf { z } _ { \star } ) p ( \bar { \mathbf { z } } _ { \star } ) } \\ { q ^ { * } ( \mathbf { B } ) q ^ { * } ( \mathbf { H } ) q ^ { * } ( \gamma ) d \bar { \mathbf { z } } _ { \star } d \mathbf { B } d \mathbf { H } d \gamma } \end{array}
$$

The posterior distribution $p ( \mathbf { z } _ { \star } | \mathbf { y } _ { \star } ) = p ( \mathbf { z } _ { \star } ) p ( \mathbf { y } _ { \star } | \mathbf { z } _ { \star } ) / p ( \mathbf { y } _ { \star } )$ can be equivalently obtained by solving the following information theoretical optimization problem:

$$
\operatorname* { m i n } _ { \ b { q } ( \mathbf { z } _ { \star } ) \in \mathcal { P } } \mathrm { K L } \left( \ b { q } ( \mathbf { z } _ { \star } ) \| \ b { p } ( \mathbf { z } _ { \star } | \mathbf { y } _ { \star } ) \right)
$$

Expanding Eq.(15) and ignoring the term unrelated to $q ( \mathbf { z } _ { \star } )$ we further get

$$
\operatorname* { m i n } _ { q ( \mathbf { z } _ { \star } ) \in \mathcal { P } } \mathrm { K L } \left( q ( \mathbf { z } _ { \star } ) \| p ( \mathbf { z } _ { \star } ) \right) - \mathbb { E } _ { q ( \mathbf { z } _ { \star } ) } [ \log p ( \mathbf { y } _ { \star } | \mathbf { z } _ { \star } ) ] .
$$

To ensure the latent representations of testing instances are close to that of their neighbours from the training set,we adopt the posterior regularization[Zhu et al., 2O14] strategy to incorporate the manifold regularization into the above posterior predictive distribution $p ( \mathbf { z } _ { \star } | \mathbf { y } _ { \star } )$ . Specifically,we define the following expected manifold regularization:

$$
\begin{array} { r l } { \mathcal { R } ( q ( \mathbf { z } _ { \star } ) ) } & { = \mathbb { E } _ { q ( \mathbf { z } _ { \star } ) } \left[ \sum _ { i = 1 } ^ { N } s _ { i } \| \mathbf { z } _ { \star } - \mathbf { z } _ { i } \| ^ { 2 } \right] } \end{array}
$$

where $s _ { i }$ is some similarity measure of instances $\mathbf { y } _ { i }$ and $\mathbf { y } _ { \star }$ Here we use a $\mathbf { k }$ -nearest neighbor graph to effectively model local geometry structure in the input space and the affinity graph is defined as:

$$
s _ { i } = \left\{ \begin{array} { l l } { \exp \left( - \frac { \| \mathbf { y } _ { \star } - \mathbf { y } _ { i } \| ^ { 2 } } { 2 t ^ { 2 } } \right) , \mathbf { y } _ { i } \in \mathcal { N } ( \mathbf { y } _ { \star } ) , } \\ { 0 , \mathrm { o t h e r w i s e } , } \end{array} \right.
$$

where $\mathcal { N } ( \mathbf { y } _ { \star } )$ denotes the $\mathbf { k }$ -nearest neighbors of $\mathbf { y } _ { \star }$

Then our posterior regularization strategy can be formulated as

$$
\begin{array} { r l } & { \underset { q ( \mathbf { z } _ { \star } ) \in \mathcal { P } } { \operatorname* { m i n } } \mathrm { K L } \left( q ( \mathbf { z } _ { \star } ) \lVert p ( \mathbf { z } _ { \star } ) \right) - \mathbb { E } _ { q ( \mathbf { z } _ { \star } ) } [ \log p ( \mathbf { y } _ { \star } | \mathbf { z } _ { \star } ) ] } \\ & { \qquad + \rho \mathcal { R } ( q ( \mathbf { z } _ { \star } ) ) , } \end{array}
$$

where the parameter $\rho > 0$ controls the expected scale.As a direct way to impose constraints and incorporate knowledge inBayesian models,posterior regularization is more natural and general than specially designed priors.However, directly solving Eq.(16) with $\mathcal { R }$ is difficult and inefficient.Let

$$
\begin{array} { r } { h ( \mathbf { z } _ { \star } | \boldsymbol { \rho } , \mathbf { s } ) = \exp \left\{ - \boldsymbol { \rho } \sum _ { i = 1 } ^ { N } s _ { i } \| \mathbf { z } _ { \star } - \mathbf { z } _ { i } \| ^ { 2 } \right\} } \end{array}
$$

then Eq.(16) can be rewritten as

$$
\begin{array} { r l } & { \underset { q ( \mathbf { z } _ { \star } ) \in \mathcal { P } } { \mathrm { m i n } } \mathrm { K L } \left( q ( \mathbf { z } _ { \star } ) \lVert p ( \mathbf { z } _ { \star } ) \right) - \mathbb { E } _ { q ( \mathbf { z } _ { \star } ) } [ \log p ( \mathbf { y } _ { \star } | \mathbf { z } _ { \star } ) ] } \\ & { \qquad - \mathbb { E } _ { q ( \mathbf { z } _ { \star } ) } [ \log h ( \mathbf { z } _ { \star } | \boldsymbol { \rho } , \mathbf { s } ) ] . } \end{array}
$$

Solving problem Eq.(17),we can get the posterior distribution

$$
\begin{array} { l } { { \displaystyle p ( { \bf z } _ { \star } | { \bf y } _ { \star } ) = \frac { p ( { \bf z } _ { \star } ) p ( { \bf y } _ { \star } | { \bf z } _ { \star } ) h ( { \bf z } _ { \star } | \rho , { \bf s } ) } { p ( { \bf y } _ { \star } ) } } \ ~ } \\ { { \displaystyle ~ = \int p ( { \bf y } _ { \star } | { \bf z } _ { \star } , \bar { \bf z } _ { \star } , { \bf B } , { \bf H } , \gamma ) p ( { \bf z } _ { \star } ) h ( { \bf z } _ { \star } | \rho , { \bf s } ) p ( \bar { \bf z } _ { \star } ) } \ ~ } \\ { { \displaystyle q ^ { * } ( { \bf B } ) q ^ { * } ( { \bf H } ) q ^ { * } ( \gamma ) d \bar { \bf z } _ { \star } d { \bf B } d { \bf H } d \gamma ~ \ ~ ( 1 8 } } \end{array}
$$

Because the multiple integral over the random variables $\bar { \mathbf { z } } _ { \star }$ $\mathbf { B } , \mathbf { H }$ and $\gamma$ is intractable,we replace the random variables B, H and $\gamma$ with the mean of estimated optimal distributions $q ^ { * } ( \mathbf { B } ) , q ^ { * } ( \mathbf { H } )$ and $q ^ { * } ( \gamma )$ ,respectively,to vanish the integral over B, $\mathbf { H }$ and $\gamma$ Then $p ( \mathbf { z } _ { \star } | \mathbf { y } _ { \star } )$ becomes

$$
p ( \mathbf { z } _ { \star } | \mathbf { y } _ { \star } ) = \int p ( \mathbf { y } _ { \star } | \mathbf { z } _ { \star } , \bar { \mathbf { z } } _ { \star } ) p ( \mathbf { z } _ { \star } ) h ( \mathbf { z } _ { \star } | \rho , \mathbf { s } ) p ( \bar { \mathbf { z } } _ { \star } ) d \bar { \mathbf { z } } _ { \star } .
$$

Now the posterior distribution $p ( \mathbf { z } _ { \star } | \mathbf { y } _ { \star } )$ can be found as:

$$
p ( \mathbf { z } _ { \star } | \mathbf { y } _ { \star } ) = \mathcal { N } \left( \mathbf { z } _ { \star } | \pmb { \mu } _ { \mathbf { z } _ { \star } } , \pmb { \Sigma } _ { \mathbf { z } _ { \star } } \right) ,
$$

where

$$
\begin{array} { r l } & { \Sigma _ { \mathbf { z } _ { \star } } = [ \langle \mathbf { B T B } ^ { \top } \rangle + ( 1 + \rho \sum _ { i = 1 } ^ { N } s _ { i } ) \mathbf { I } ] ^ { - 1 } } \\ & { \mu _ { \mathbf { z } _ { \star } } = \Sigma _ { \mathbf { z } _ { \star } } [ \langle \mathbf { B } \rangle \mathbf { T y } _ { \star } + \rho \sum _ { i = 1 } ^ { N } s _ { i } \langle \mathbf { z } _ { i } \rangle ] } \\ & { \mathbf { T } = \gamma \mathbf { I } - \gamma ^ { 2 } \langle \mathbf { H } ^ { \top } ( \mathbf { I } + \gamma \langle \mathbf { H } \mathbf { H } ^ { \top } \rangle ) ^ { - 1 } \mathbf { H } \rangle . } \end{array}
$$

However, with the likelihood of the visual image $p _ { \pmb { \theta } } ( \mathbf { x } _ { \mathrm { p r e d } } | \mathbf { z } _ { \star } )$ formulated by a DNN,the integral over the latent variables $\mathbf { z } _ { \star }$ (Eq.(13)) can not be computed analytically. Similar as in the training phase,we can approximate this integral by Monte-Carlo sampling.Finally, the reconstructed vims.e. $\begin{array} { r } { \mathbf { \dot { x } } _ { \mathrm { p r e d } } = \frac { 1 } { L } \sum _ { l = 1 } ^ { L } \mathbf { \dot { x } } _ { \mathrm { p r e d } } ^ { ( l ) } } \end{array}$ g here $\mathbf { x } _ { \mathrm { p r e d } } ^ { ( l ) }$ $L$ purpt-s of the generative network,ie, $\mathbf { x } _ { \mathrm { p r e d } } ^ { ( l ) } = g ( \mathbf { z } _ { \star } ^ { ( l ) } )$ .

# 5Experiments

In this section, we present extensive experimental results on fMRI recording datasets to demonstrate the effectiveness of the proposed framework for perceived image reconstruction from human brain activity. Specifically, we compare our DGMM with the following algorithms,which use either a shallow or a deep architecture:

· Fixed Bases (Miyawaki et al.): a specially designed method to reconstruct visual images by combining local image bases of multiple scales $( 1 \times 1 , 1 \times 2 , 2 \times 1$ ，and $2 \times 2$ pixels covering an entire image) [Miyawaki et al., 2008l.The shapes of these predefined images bases are fixed,thus it may not be optimal for image reconstruction.

·Bayesian CCA(BCCA):a probabilistic extension of CCA model that relates the fMRI activity space to the visual image space viaa set of latent variables [Fujiwara et al.,2O13].BCCA assumes a linear observation model for visual images and a spherical covariance for the Gaussian distribution of fMRI voxels.

·Deep Canonically Correlated Autoencoders (DCCAE): a latest deep multi-view representation learning model that consists of two autoencoders and optimizes the combination of canonical correlation between the learned bottleneck representations and the reconstruction errors of the autoencoders [Wang et al., 2015].DCCAE do not consider the cross-reconstruction errors between two views.

· Deconvolutional Neural Network (De-CNN): a latest neural decoding method based on multivariate linear regression and deconvolutional neural network [Haiguang Wen and Liu, 2016; Zeiler et al., 2011]. It is atwo-stage cascademodel,i.e.,itfirstpredictsfeaturemaps by multivariate linear regression, then reconstruct images by feeding the estimated feature-maps in a pretrained deconvolutional neural network.

# 5.1Experimental testbed and setup

Datadescription. We conducted experiments on three public fMRI datasets obtained from Miyawaki et al. [Miyawaki et al.,2OO8] and van Gerven[Van Gerven et al.,2010b; Schoenmakers et al.,2O13l.Dataset1,consisting of contrastdefined $1 0 \times 1 0$ patches,contains two independent sessions [Miyawaki et al.,2Oo8]. One is a‘random image session', in which spatially random patterns were sequentially presented. The other is a‘figure image session',in which alphabetical letters and simple geometric shapes were sequentially presented. We used fMRI data from primary visual area V1 of subject 1 (S1) for the analysis. Note that all comparing algorithms were trained on the data from ‘random image session’and evaluated on the data from‘figure image session'. Dataset 2 contains a hundred handwritten gray-scale digits (equal number of 6s and 9s) at a $2 8 \times 2 8$ pixel resolution taken from the training set of the MNIST database and the fMRI data from V1,V2 and V3[Van Gerven et al.,201Ob]. Dataset 3 contains 36O gray-scale handwritten characters (equal number of Bs,Rs,As,Is,Ns,and Ss) at a $5 6 \times 5 6$ pixel resolution takenfrom[VanderMaaten,2OO9landthefMRIdataofV1, V2 taken from three subjects [Schoenmakers et al.,2013]. The visual images were downsampled from $5 6 \times 5 6$ pixels to $2 8 \times 2 8$ pixels in our experiments. The details of the 3 data sets used in our experiments had been summarized in Table 1．See [Miyawaki et al.，2OO8;Van Gerven et al.,2010b; Schoenmakers et al.,2O13] for more information, including fMRI data acquisition and preprocessing.

Voxel selection.Voxel selection is an important component to fMRI brain decoding because many voxels may not respond to the visual stimulus. A common approach is to choose those voxels that are maximally correlated with the visual images during training.We chose voxels for which the model provided better predictability (encoding performance).

Table 1: The details of the 3 data sets used in our experiments.   

<html><body><table><tr><td>Datasets</td><td>#Instances</td><td></td><td>#Pixels #Voxels</td><td>#ROIs</td><td>#Training</td></tr><tr><td>Dataset 1</td><td>1400</td><td>100</td><td>797</td><td>V1</td><td>1320</td></tr><tr><td>Dataset 2</td><td>100</td><td>784</td><td>3092</td><td>V1, V2, V3</td><td>90</td></tr><tr><td>Dataset 3</td><td>360</td><td>784</td><td>2420</td><td>V1, V2</td><td>330</td></tr></table></body></html>

This codifies our intuition that the voxels better predicted with the visual images are those to be included in the decoding model. The goodness-of-fit between model predictions and measured voxel activities was quantified using the coefficient of determination $( \mathrm { R } ^ { 2 } )$ which indicates the percentage of variance that is explained by the model. In experiments, we first computed the $\mathrm { R ^ { 2 } }$ of each voxel using 1O-fold crossvalidation on training data, then voxels with positive $\mathrm { R ^ { 2 } }$ were selected for further analysis.

Parameter setting. The hyper-parameters of the proposed DGMM were set to $( \alpha _ { \tau } , \beta _ { \tau } ) \bar { = } ( \bar { \alpha } _ { \eta } , \beta _ { \eta } ) = ( \alpha _ { \gamma } , \beta _ { \gamma } ) \bar { = } ( 1 , 1 )$ for all data sets,while 5-fold cross validation was conducted on training sets to choose better regularization parameters $\rho$ from $2 ^ { [ - \bar { 8 } : 0 ] }$ . For fair comparison, model parameters of other methods had also been tuned carefully. In our experiments,we considered multiple layer perceptrons (MLPs） as the type of recognition models.Inspired by the selectivity of visual areas to feature maps of varying complexity [Güglu and van Gerven,2O15; Haiguang Wen and Liu, 2O16],we set the structures of the recognition network for visual images as ‘100-200'，‘784-256-128-10' and‘784-256-128-5' for three data sets,respectively. Specially，we considered two types of the structures for DCCAE. One has an asymmetric shape (same setup as our model for image view and a single layer setup for fMRI view,DCCAE-A),which can mimic our model in structure and function.The other one has a symmetric shape(same setup for both views,DCCAE-S),which can explore the deep nonlinear maps for fMRI data.

# 5.2 Performance evaluation

The reconstructed geometric shapes and alphabet letters,handwritten digits and handwritten characters by the pro posed DGMM and other algorithms were shown in Fig.2, Fig.3 and Fig.4, respectively, where the first row denote presented images,and below rows are the reconstructed images obtained from all comparing algorithms.

Overall, the images reconstructed byDGMM captured the essential features of the presented images.In particular, they showed finereconstructions forhandwrittendigitsand characters.Although the reconstructed geometric shapes and alphabet letters had some noise in the peripheral regions,the main shapes can be clearly distinguished. With the obtained reconstructions of handwritten digits and characters shared certain characteristics of their corresponding original images, there are subtle differences in the strokes.We attribute this phenomenon to the fact that manifold regularization imposed on the latent representations may change the details of reconstructed images.On the contrast,images reconstructed by Miyawaki's method and BCCA were coarse for all image types with noise scattered over the entire reconstructed image.Also,both DCCAE-S and DCCAE-A produced disappointing reconstructions which often lacked shapes of the presented images,especially for geometric shapes and alphabet letters.This might be due to the fact that nonlinear maps will easily over-fit the voxel activities.

![](images/bae9df05fe62c3b221110534dfaff4475e871180704f69c3b688cc762e8581b5.jpg)  
Figure 4: Examples of reconstructed 18 distinct handwriten characters taken from subject 3 of Dataset 3.

![](images/c87e5fe62ca6c88e492a00826cc2c4744abcbd6def7c0f9bfe4f83fed31be8d6.jpg)  
Figure 2: Image reconstructions of geometric shapes and alphabetletterstakenfromDataset1.

![](images/f78c6c1ac7f6776bcc84374d877fdfba4da16848358f1099d97c4f0bf697bce1.jpg)  
Figure 3:Image reconstructions of 1O distinct handwritten digits taken from Dataset 2.

To evaluate the reconstruction performance quantitatively, we used several standard image similarity metrics,including Pearson's correlation coefficient (PCC),mean squared error (MSE) and structural similarity index (SSIM) [Wang et al., 2004].Note that MSE is not highly indicative of perceived similarity,while SSIM can address this shortcoming by taking texture into account.In addition,we also performed image classification analysis to quantify the reconstruction accuracy from another perspective. Specifically, linear support vector machine (SVM) and convolutional neural network(CNN) which had been trained on the presented visual images were used as the classifiers to label the reconstructed images. The classification accuracy of SVM(ACC-SVM) and CNN (ACC-CNN) on reconstructed images were reported. Performance comparisons were listed in Table 2.Note that we also listed the time consumed in training phase for all comparing algorithmsinthelastcolumnforreference.Severalobservations can be drawn as follows.

First,by comparing DGMM against the other algorithms, we can find that DGMM performs considerably better on all three data sets.In particular, the SSIM values of DGMM significantly surpass the baseline algorithms in all cases.

Second,by examiningDGMMagainstBCCA which has a linear observation model for visual images,we can find that DGMM always outperform BCCA. This encouraging result shows that the DGMM with a DNN model for visual images is able to extract nonlinear features from visual images.

Third，DGMM shows obvious better performance than DCCAE-A and DCCAE-S. Except for ignoring crossreconstructions,it is also caused by the fact that a linear map between voxel activities and bottleneck representation is enough to achieve good performance,while the nonlinear maps are easily overfitting under the high dimensionality of limited fMRI data instances.

Fourth,the performance of De-CNN is moderate for all data sets. We attribute this to the fact that it is a two-stage method which can't obtain the global optimal result of model parameters.

Finally,nearly $1 0 0 \%$ correct classification is possible for eachalgorithm onDataset2.We believe thatitiscaused bythe fact that digit 6 and 9 are easily to distinguish from each other.On Dataset 3,the remarkably higher classification performance on the images reconstructed by our model demonstrates the superiority of the proposed DGMM again.

Table 2:Performance of several image reconstruction methods onthe test sets.Results were averaged over 2Orandom sed and all subjects (mean±std).The best performance on each dataset was highlighted.   

<html><body><table><tr><td>Datasets</td><td>Algorithms</td><td>PCC</td><td>MSE</td><td>SSIM</td><td>ACC-SVM</td><td>ACC-CNN</td><td>Time(s)</td></tr><tr><td rowspan="6">Dataset 1</td><td>Miyawaki et al.</td><td>.609±.151</td><td>.162±.025</td><td>.237±.105</td><td></td><td>1</td><td>19.4±1.1</td></tr><tr><td>BCCA</td><td>.438±.215</td><td>.253±.051</td><td>.181±.066</td><td></td><td></td><td>74.9±3.0</td></tr><tr><td>DCCAE-A</td><td>.455±.113</td><td>.234±.029</td><td>.166±.025</td><td></td><td>1</td><td>211.8±7.5</td></tr><tr><td>DCCAE-S</td><td>.401±.100</td><td>.240±.027</td><td>.175±.011</td><td></td><td></td><td>254.9±9.8</td></tr><tr><td>De-CNN</td><td>.469±.149</td><td>.263±.067</td><td>.224±.129</td><td></td><td>1</td><td>108.2±2.2</td></tr><tr><td>DGMM</td><td>.611±.183</td><td>.159±.112</td><td>.268±.106</td><td></td><td></td><td>118.4±2.5</td></tr><tr><td rowspan="6">Dataset 2</td><td>Miyawaki et al.</td><td>.767±.033</td><td>.042±.007</td><td>.466±.030</td><td>1.00</td><td>1.00</td><td>39.9±1.2</td></tr><tr><td>BCCA</td><td>.411±.157</td><td>.119±.017</td><td>.192±.035</td><td>1.00</td><td>1.00</td><td>20.7±1.0</td></tr><tr><td>DCCAE-A</td><td>.548±.044</td><td>.074±.010</td><td>.358±.097</td><td>.900</td><td>.967±.047</td><td>12.7±0.3</td></tr><tr><td>DCCAE-S</td><td>.511±.057</td><td>.080±.016</td><td>.552±.088</td><td>1.00</td><td>1.00</td><td>19.4±0.8</td></tr><tr><td>De-CNN</td><td>.799±.062</td><td>.038±.010</td><td>.613±.043</td><td>1.00</td><td>1.00</td><td>35.8±1.2</td></tr><tr><td>DGMM</td><td>.803±.063</td><td>.037±.014</td><td>.645±.054</td><td>1.00</td><td>1.00</td><td>18.6±1.2</td></tr><tr><td rowspan="6">Dataset 3</td><td>Miyawaki et al.</td><td>.481±.096</td><td>.067±.026</td><td>.191±.043</td><td>.655±.193</td><td>.655±.113</td><td>128.1±4.6</td></tr><tr><td>BCCA</td><td>.348±.138</td><td>.128±.049</td><td>.058±.042</td><td>.633±.034</td><td>.600±.098</td><td>32.9±1.0</td></tr><tr><td>DCCAE-A</td><td>.354±.167</td><td>.073±.036</td><td>.186±.234</td><td>.478±.126</td><td>.533±.072</td><td>38.1±1.1</td></tr><tr><td>DCCAE-S</td><td>.351±.153</td><td>.086±.031</td><td>.179±.117</td><td>.478±.051</td><td>.478±.155</td><td>59.5±1.8</td></tr><tr><td>De-CNN</td><td>.470±.149</td><td>.084±.035</td><td>.322±.118</td><td>.589±.135</td><td>.611±.128</td><td>96.8±2.0</td></tr><tr><td>DGMM</td><td>.498±.193</td><td>.058±.031</td><td>.340±.051</td><td>.767±.115</td><td>.778±.083</td><td>42.4±4.2</td></tr></table></body></html>

# 6 Conclusion and future works

We have proposed a deep generative multiview framework to tackle the perceived image reconstruction problem. In our framework,multiple correspondences between visual image pixels and fMRI voxels can be found viaa set of latent variables.We also derived a predictive distribution that succeeded in reconstructing visual images from brain activity patterns.Although we focused on visual image reconstruction problem in this paper,our framework can also deal with brain encoding tasks.Extensive experimental studies have confirmed the superiority of the proposed framework.

Two challenging and promising directions can be considered in the future.First, considering the recurrent neural networks(RNNs)[Chung et al.,2015] in our framework,we can explore the reconstruction of dynamic vision. Second, considering each subject's fMRI measurements as one view, we can explore multi-subject decoding.

# Acknowledgment

This work was supported by National Natural Science Foundation of China (No.91520202,61602449) and Youth Innovation Promotion Association CAS.

# References

[Archambeau and Bach,2Oo9] CédricArchambeauand FrancisRBach.Sparse probabilistic projections.In NIPS, pages 73-80,2009.   
[Chandar et al.,2O16] Sarath Chandar,Mitesh M Khapra, HugoLarochelle,andBalaramanRavindran.Correlational neural networks. Neural computation,2016.

[Chung et al.,2O15] Junyoung Chung，Kyle Kastner,LaurentDinh,Kratarth Goel, Aaron C Courville,and Yoshua Bengio.A recurrent latent variable model for sequential data. In NIPS, pages 2980-2988,2015.

[Cichyetal.,2O16]RadoslawMartin Cichy,AdityaKhosla, Dimitrios Pantazis,Antonio Torralba,and Aude Oliva. Comparison of deep neural networks to spatio-temporal cortical dynamics of human visual object recognition reveals hierarchical correspondence.Scientific reports,6, 2016.   
[Damarla and Just, 2O13] Saudamini Roy Damarla and Marcel Adam Just. Decoding the representation of numerical values from brain activation patterns. Human brain mapping,34(10):2624-2634,2013.   
[Duchi et al.,2O11] John Duchi,Elad Hazan，and Yoram Singer. Adaptive subgradient methods for online learning and stochastic optimization. Journal of Machine Learning Research,12(Jul):2121-2159,2011.   
[Elahe'Yargholi,2O16] Gholam-AliHossein-Zadeh Elahe'Yargholi.Brain decoding-classification of hand written digits from fmri data employing bayesian networks. Frontiers inHuman Neuroscience,1O,2016.   
[Fujiwara et al.,2O13] Yusuke Fujiwara,Yoichi Miyawaki, and Yukiyasu Kamitani. Modular encoding and decoding models derived from bayesian canonical correlation analysis.Neural computation,25(4):979-1005,2013.   
[Guclui and van Gerven,2O15] Umut Güclu and Marcel A. J. van Gerven.Deep neural networks reveal a gradient in the complexity of neural representations across the ventral stream. Journal ofNeuroscience,35(27):10005-10014, 2015.

[Haiguang Wen and Liu,2O16] Yizhen Zhang Kun-Han Lu Haiguang Wen,Junxing Shi and Zhongming Liu. Neu

ral encoding and decoding with deep learning for dynamic natural vision. arXiv:1608.03425v1,2016.   
[Hossein-Zadeh and others,2016] Gholam-Ali HosseinZadeh et al. Reconstruction of digit images from human brain fmri activity through connectivity informed bayesian networks. Journal of neuroscience methods,257:159-167, 2016.   
[Kingma and Welling,2014] Diederik P Kingma and Max Welling. Auto-encoding variational bayes. In ICLR,2014.   
[Kingma et al., 2014] Diederik P Kingma, Shakir Mohamed, Danilo Jimenez Rezende，and Max Welling. Semisupervised learning with deep generative models. In NIPS, pages 3581-3589, 2014.   
[Lee and Kuhl, 2O16] Hongmi Lee and Brice A Kuhl. Reconstructing perceived and retrieved faces from activity patterns in lateral parietal cortex．The Journal of Neuroscience,36(22):6069-6082,2016.   
[Miyawaki et al.,2Oo8] Yoichi Miyawaki, Hajime Uchida, Okito Yamashita, Masa-aki Sato, Yusuke Morito,Hiroki C Tanabe,Norihiro Sadato,and Yukiyasu Kamitani. Visual image reconstruction from human brain activity using a combination of multiscale local image decoders. Neuron, 60(5):915-929,2008.   
[Ng and Abugharbieh,2O11] Bernard $\mathrm { N g }$ and Rafeef Abugharbieh. Generalized group sparse classifiers with application in fmri brain decoding.In CVPR,pages 1065-1071,2011.   
[Nishimoto et al.,2011] Shinji Nishimoto， AnTVu, Thomas Naselaris,Yuval Benjamini,Bin Yu,and Jack L Gallant.Reconstructing visual experiences from brain activity evoked by natural movies.Current Biology, 21(19):1641-1646, 2011.   
[Schoenmakers et al.,2013] Sanne Schoenmakers,Markus Barth,Tom Heskes,and Marcel van Gerven. Linear reconstruction of perceived images from human brain activity. Neurolmage,83:951-961,2013.   
[Schoenmakers et al.,2015] SanneSchoenmakers，Umut Güclu,Marcel Van Gerven,and Tom Heskes.Gaussian mixture models and semantic gating improve reconstructions from human brain activity. Frontiers in computational neuroscience, 8, 2015.   
[Van der Maaten,2OO9] Laurens Van der Maaten.A new benchmark dataset for handwritten character recognition. Tilburg University, pages 2-5,2009.   
[Van Gerven et al.,2O10al Marcel AJ Van Gerven,Botond Cseke,Floris P De Lange,and Tom Heskes.Efficient bayesian multivariate fmri analysis using a sparsifying spatio-temporal prior. Neurolmage, 50(1):150-161,2010.   
[Van Gerven et al.,201Ob] Marcel AJ Van Gerven,Floris P De Lange，and Tom Heskes.Neural decoding with hierarchical generative models.Neural computation, 22(12):3127-3142,2010.   
[Wang et al.,2004] Zhou Wang，Alan C Bovik, Hamid R Sheikh,and Eero P Simoncelli. Image quality assessment: from error visibilityto structural similarity.IEEE transactions on image processing,13(4):600-612,2004.   
[Wang et al.,2O15] Weiran Wang，Raman Arora，Karen Livescu,and Jeff Bilmes. On deep multi-view representation learning.In ICML,pages1083-1092,2015.   
[Yamashita et al.,2Oo8] Okito Yamashita,Masa-aki Sato, Taku Yoshioka,Frank Tong,and Yukiyasu Kamitani. Sparse estimation automatically selects voxels relevant for the decoding of fmri activity patterns.Neurolmage, 42(4):1414-1429,2008.   
[Zeiler et al.,2O11] Matthew D Zeiler, Graham W Taylor, and Rob Fergus. Adaptive deconvolutional networks for mid and high level feature learning. In ICCV, pages 2018- 2025,2011.   
[Zhu et al.,2014] Jun Zhu,Ning Chen,and Eric P Xing. Bayesian inference with posterior regularization and applicationsto infinite latentsvms.Journal ofMachineLearningResearch,15(1):1799-1847,2014.