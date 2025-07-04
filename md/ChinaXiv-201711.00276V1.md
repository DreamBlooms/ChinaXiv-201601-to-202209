# DPABl: Data Processing & Analysis for (Resting-State) Brain Imaging

Chao-Gan Yan1.2, Xin-Di Wang², Xi-Nian Zuo1, Yu-Feng Zang4.5

1Key Laboratory of Behavioral Science and Magnetic Resonance Imaging Research Center， Institute of Psychology，Chinese Academy of Sciences，Beijing，China; 2Department of Child and Adolescent Psychiatry， NYU Langone Medical Center School of Medicine, New York, NY, USA; ³State Key Laboratory of Cognitive Neuroscience and Learning & IDG/McGovern Institute for Brain Research, Beijing Normal University, Beijing, China;4Center for Cognition and Brain Disorders， Hangzhou Normal University, Hangzhou, China; 5Zhejiang Key Laboratory for Research in Assessment of Cognitive Impairments,Hangzhou, Zhejiang, China

# Corresponding author:

Chao-Gan Yan, Ph.D.

Key Laboratory of Behavioral Science and Magnetic Resonance Imaging Research   
Center, Institute of Psychology, Chinese Academy of Sciences,Beijing, China   
16 Lincui Road, Chaoyang District, Beijing 100101, China   
Tel: +86-10-64101582   
Fax: +86-10-64101582   
E-mail: ycg.yan@gmail.com

# ABSTRACT

Brain imaging efforts are being increasingly devoted to decode the functioning of the human brain. Among neuroimaging techniques,resting-state fMRl (R-fMRl) is currently expanding exponentially. Beyond the general neuroimaging analysis packages (e.g., SPM, AFNl and FSL), REST and DPARSF were developed to meet the increasing need of user-friendly toolboxes for R-fMRl data processing. To address recently identified methodological challenges of R-fMRl, we introduce the newly developed toolbox, DPABl, which was evolved from REST and DPARSF. DPABl incorporates recent research advances on head motion control and measurement standardization, thus allowing users to evaluate results using stringent control strategies. DPABl also emphasizes test-retest reliability and quality control of data processing.Furthermore，DPABl providesa user-friendly pipeline analysis toolkit for rat/monkey R-fMRl data analysis to reflect the rapid advances in animal imaging. In addition， DPABl includes preprocessing modules for task-based fMRl, voxel-based morphometry analysis,statistical analysis and results viewing. DPABl is designed to make data analysis require fewer manual operations,be less time-consuming，have a lower skill requirement，a smaller risk of inadvertent mistakes，and be more comparable across studies.We anticipate this open-source toolbox will assist novices and expert users alike and continue to support advancing R-fMRl methodology and its application to clinical translational studies.

Keywords: data processing; quality control; resting-state fMRl; standardization; statistical analysis

# 1.Introduction

Human brain function，as implemented by one of the most complex systems in the universe，is fascinating to decode. Brain imaging has advanced our progress in such efforts during recent decades. Among neuroimaging techniques，magnetic resonance imaging(MRl)， especially functional MRl (fMRl)， dominatesbecause ofits non-invasiveness，whole-brain coverage and wide availability (Bandetini， 2012). By detecting local concentrations of deoxygenated and oxygenated hemoglobin， fMRl blood-oxygen level dependent (BOLD） signals alow inferring blood flow changes associated with differential neural activity during distinct tasks (Huettel et al.，2004). Unlike task-based fMRl requiring specific tasks tailored to each cognitive experiment design， resting-state fMRl (R-fMRl） focuses on spontaneous brain activity without requiring subjects to perform explicit cognitive tasks,other than remaining extremely stil or 'resting' in the scanner (Biswal et al.， 1995). R-fMRl has become increasingly popular (Buckner et al., 2013; Fox and Raichle,2007; Kelly et al.,2012) because of its substantial reliability (Shehzad et al., 2009; Zuo and Xing,2014), sensitivity (Castellanos et al., 2013; Foxand Greicius， 2010； Greicius， 2008) andcomparabilityacross labs (ADHD-200-Consortium, 2012; Biswal et al., 2010; Di Martino et al., 2014; Mennes et al., 2013).The R-fMRl field has been expanding exponentially, with more than 1,000 studies now being published per year (Birn, 2012; Yan et al., 2014; Zuo and Xing,2014).

As the R-fMRl field has grown, there is an increasing need for user-friendly toolboxes for

R-fMRl data processing that go beyond manually integrating functions in general analysis packages such as Statistical Parametric Mapping (SPM) (Ashburner， 2012)，FMRIB Software Library (FSL) (Jenkinson et al., 2012),or Analysis of Functional Neurolmages (AFNI)(Cox，2012). Song and colleagues developed a toolbox named Resting-State fMRI Data Analysis Toolkit (REST) (Song et al.， 2011） to calculate common R-fMRl derivatives. Based on SPM and REST functions,a MATLAB toolbox for“pipeline" data analysis of R-fMRl data，DPARSF was also developed (Yan and Zang，2010). The DPARSF analysis pipeline automated and overcame time-consuming manual procedures in preprocessing R-fMRl data and generating R-fMRl derivatives，e.g.， functional connectivity (Biswal et al.， 1995)，regional homogeneity (ReHo) (Zang et al.，2004), amplitude of low frequency fluctuations (ALFF) (Zang et al.， 2O07)， fractional ALFF (fALFF) (Zou et al.， 2008)，voxel-mirrored homotopic connectivity (VMHC) (Zuo et al, 2010b）and degree centrality (Buckner et al.， 2Oo9). This user-friendly toolbox made R-fMRl analysis easily accessible to a broader community,as attested by its having been cited more than 600 times per Google Scholar. Although DPARSF has been widely used (including more recent R-fMRl pipelines CONN (Whitfield-Gabrieli and Nieto-Castanon, 2012)and FATCAT (Taylor and Saad， 2013)， the original DPARSF has fallen behind with some recent developments of R-fMRl methodologies，particularly in relation to R-fMRl methodological challenges.

For example，head motion is a formidable challenge for R-fMRl，as recent work conclusively demonstrated that even head micro-movements could introduce artifactual inter-individual differences in R-fMRl metrics (Power et al.,2012a,b; Satterthwaite et al, 2012;Van Dijk et al.， 2012). Several studies (Fair et al.， 2012； Power et al., 2014; Satterthwaite et al., 2013; Yan et al.， 2013a) provided comprehensive assessments of motion-related artifacts and suggested procedures for controlling them， including higher-order regression models (e.g., Friston 24-parameter model(Friston et al.,1996)) and motion scrubbing approaches at the individual-subject level (Power et al., 2012a),as well as accounting for head motion at the group-level (i.e.， covariate analysis). Such strategies need to be seamlessly integrated into an easy-to-use R-fMRl pipeline toolbox. See a comprehensive review on recent advances regarding this topic in Power et al. (2015).

Measurement standardization represents another key chalenge for R-fMRl. Concerns about the many sources of nuisance variation impacting on R-fMRl measures continue to grow (Cole et al.，2010; Kelly et al.，2012). A recent study compared an array of standardization approaches and found group-level post-hoc standardizations for mean-regression and variance-standardization were advantageous for avoiding the introduction of artifactual relationships with standardization parameters (Yan et al, 2013b). To better generalize such standardization to minimize the influence of nuisance variables in future studies,a user-friendly module for standardizing R-fMRl indices is warranted.Furthermore, to yield valid results，R-fMRl measures must have adequate test-retest (TRT) reliability (Shehzad et al.,2009; Zuo et al., 2010a; Zuo and Xing, 2014). A module for assessing TRT reliability is also needed to facilitate investigating effects of inter-individual differences on R-fMRl measures.

With all the methodological improvements being incorporated into R-fMRl, adequate quality control (QC) is essential for establishing reliable results. For most advanced MRl centers,regular quality assurance protocols ensuring scanner performance stability are performed daily (Friedman and Glover, 20o6; Ihalainen et al.,2004; Simmons et al., 1999).Even when the quality of fMRl acquisition is monitored, quality control of data processing needs to be considered. The quality of raw structural and functional images, as well as the effects of registration to standard templates must be checked. Furthermore,spatial coverage of functional images and head motion during scanning should be considered in the quality control steps. Manual data checking is extremely time consuming,which sometimes prevents investigators from checking each subject's data. Thus,an integrated and efficient quality control module for data processing would be essential for ensuring the reliability of R-fMRl study findings.

Most R-fMRl studies are performed on humans. However,as the physiology underlying fMRl effects remains largely unknown, R-fMRl studies with animal models are critical (Hutchison and Everling,2012). Animal work,including rodents and non-human primates, allows neurophysiological recordings and pharmacological/behavior manipulations, which may not be ethical or practical in humans.There exist structural image analysis pipelines for animals; for example, SPMMouse facilitates voxel-based morphometry analysis for mouse data (Sawiak et al., 2Oo9). However, there is no user-friendly R-fMRl analysis pipeline designed for animal data to date.

To meet these demands,we developed a toolbox named DPABl (for Data Processing & Analysis of Brain Imaging (Figure 1),which evolved from DPARSF and REST. DPABl includes an advanced edition of DPARSF，which integrates the latest algorithms to control for head motion，as well as standardization，TRT reliability，quality control modules and rat/monkey data analysis pipelines.DPABl works with other imaging modalities，including preprocessing modules for task-based fMRl and for voxel-based morphometry analysis,as well as modules for statistical analysis. DPABl also includes a MRI viewer.

# 2. Implementation

DPABl was developed in MATLAB (The MathWorks Inc.， Natick，MA，US). It is an open-source package (source code available at htp://rfmri.org/DPABl) evolved from DPARSF and REST. It supports Windows, MacOS and Linux operating systems. Here, we introduce the implementation of its key features.

# 2.1. Advanced DPARSF

The implementation of DPARSF V1.0 (basic edition) was previously described (Yan and Zang,2010). The updated edition of DPARSF has been integrated into DPABl as a key module.Here we present the updated functions in the most recent edition (V3.2）as follows.

In addressing head motion concerns in R-fMRl analyses (Power et al.， 2012a，b; Satterthwaite et al.， 2012； Van Dijk et al.， 2012)，DPARSF V3.2 provides Friston 24-parameter motion correction (Satterthwaite et al.， 2013; Yan et al.， 2013a)， i.e., regression with autoregressive models of motion incorporating 6 head motion parameters, 6 head motion parameters one time point before，and the 12 corresponding squared items (Friston et al.，1996). DPARSF V3.2 also provides voxel-specific head motion calculation and correction at the individual level (Satterthwaite et al.， 2013; Yan et al, 2013a). Data scrubbing was implemented in multiple ways: 1) model each bad time point as a separate regressor in nuisance covariates regression, 2) delete bad time points,and 3）interpolate bad time pointswith nearest neighbor， linear or cubic spline interpolation.The voxel-specific mean framewise displacement (FD） and volume-level mean FD are calculated for accounting for head motion in group-level analyses.

In addition to head motion correction， DPARSF V3.2 also provides regression of other nuisance variables,including white matter (WM) and cerebrospinal fluid (CSF） signal regression. Other than mean signal regression, the CompCor method (Behzadi et al, 2007)，which was reported to be advantageous (Chai et al.， 2012),is integrated.This extracts the first 5 principal components from a combined WM/CSF mask.

Additionally，DPARSF V3.2 can distribute the processing of multi-subject datasets to different CPU cores with the MATLAB parallel computing toolbox. It supports defining regions of interests interactively based on a participant's T1 image in native space. It resamples the mask files automaticaly if the dimensions mismatch those of the functional images.Before co-registration of structural images and functional images,skull strip can be performed on each modality to improve the accuracy of registration.

# 2.2. Standardization module

To reduce the impact of many sources of nuisance variation impacting on R-fMRI measures，we have provided several post-hoc standardization approaches in the standardization module.

1）Mean Regression: calculate the mean across all brain voxels for a given R-fMRI measure of each participant and then regress out the mean at the group-level.   
2) Mean Regression $^ +$ SD Division: calculate the mean and standard deviation across brain voxels for each participant,and then regress out the mean at the group-level. The residual value at each voxel is divided by the standard deviation.

3） Mean Regression $^ +$ log SD Regression: a mean regression $^ +$ log SD regression model was employed to accurately address both additive and multiplicative noise in a two-step regression model. Please see Yan et al. (2013b) for more details.

4) Z-standardization: calculate the mean and standard deviation across brain voxels for a given R-fMRl measure, then subtract the mean from the value at each voxel and divide the value at each voxel by the standard deviation.

5)Mean Division: calculate the mean across brain voxels for a given R-fMRl measure and divide the value at each voxel by the mean.

6)Mean Subtraction: calculate the mean across brain voxels for a given R-fMRI measure and then subtract the mean from the value at each voxel.

7） Median - inter-quartile range standardization: calculate the median and the range between $2 5 \% - 7 5 \%$ percentile (interquartile range), then subtract the median from the value at each voxel and divide the value at each voxel by the interquartile range.

8)Rank standardization: each voxel is ranked according to its value within the brain, and the rank value is assigned to each voxel.

9） Quantile standardization: each voxel is ranked according to value for each participant, and then the average value across participants of each rank is computed.The voxel with the same rank for each participant is assigned that average value.

10)Gaussian function fit normalization. First fit a Gaussian function with parameters of mean,standard deviation,and area to the distribution of values (restricted to full width at half maximum), then subtract the estimated mean from the value at each voxel and divide the value at each voxel by the estimated standard deviation (Lowe et al, 1998).

# 2.3.Test-retest Reliability

Before using R-fMRl measures to test inter-individual differences,TRT reliability should be assessed (Shehzad et al., 2009; Zuo et al., 2010a; Zuo and Xing, 2014). The TRT reliability module supports voxel-wise intra-class correlation (ICC) calculation with either ANOVA or linear mixed models.

# 1) ANOVA model:

$$
I C C = \frac { M S _ { b } - M S _ { w } } { M S _ { b } + M S _ { w } }
$$

Where ${ \mathsf { M S } } _ { \mathrm { b } }$ is the between-subject mean square and ${ \mathsf { M S } } _ { \mathsf { w } }$ is the within-subject mean square for each index (Shrout and Fleiss, 1979).

2) Linear mixed model

As described in Zuo et al., (2011; 2013), the two-level linear mixed model was applied to the decomposition of $\mathsf { Y } _ { i j }$ (the value of the $j .$ -th participant's $j .$ -th measurement occasion):

$$
Y _ { i j } = \mu _ { 0 j } + e _ { i j } , \mu _ { 0 j } = \mu _ { 0 0 } ^ { \prime } + e _ { 0 j } ^ { \prime }
$$

where $\mu _ { 0 0 } ^ { \prime }$ is a fixed parameter and $e _ { j } ^ { \prime }$ and $e _ { i j }$ are independent random effects normally distributed with mean O and variances $\sigma _ { e \prime } ^ { 2 }$ and $\sigma _ { e } ^ { 2 }$ .The term $e _ { j } ^ { \prime }$ is the participant effect and $e _ { i j }$ is the measurement error. The ICC was defined as

$$
I C C = \frac { \sigma _ { e \prime } ^ { 2 } } { \sigma _ { e ^ { \prime } } ^ { 2 } + \sigma _ { e } ^ { 2 } }
$$

The variance terms were estimated with the restricted maximum likelihood (ReML) approach.

# 2.4. Quality control

To facilitate quality control, DPABl includes the following QC steps (Figure 2).

1) QC for raw functional and structural images.   
During preprocessing, there is a step for reorienting functional images and T1 images interactively. This step can help improve the accuracy of coregistration， segmentation andnormalization，especially when the image's initial orientation is substantially inconsistent with a standard template.At the same time,it's an important QC step.DPABl pops up the related images for each subject automatically，allowing users to rate the quality of the structural and functional images and comment. For example,images with large distortions，head motion，drop out， ghosting，or structural abnormality can be screened. The scores and comments are used for thresholding the quality of the raw functional and structural images.

2) QC forspatial normalization.

To make comparisons between subjects feasible，the individual brain is spatially coregistered (normalized） to standardized space. Ensuring adequate effects of normalization of each individual is important for drawing reliable conclusions.The DPABl

QC module provides a convenient and eficient way to visually inspect coregistration. As demonstrated in Figure 3， four yoked windows with normalized structural image, functional image, gray matter (GM) segmentation and a MNl template pop up. On top of each image,the GM/WM boundary is overlaid to better check the spatial normalization effect.The QC scores and comments can be stored through the rating window for later thresholding.

3) QC for spatial coverage and group mask generation.   
Due to the limitation of how many slices can be included in functional scans and the variability in head size and shape (e.g., echo-planar imaging (EPl)), the spatial coverage of EPl raw images varies. The regions not covered in some subjects may produce spurious findings due to coverage differences. DPABl generates a coverage mask with a program equivalent to AFNl's 3dAutomask. Group masks could be generated including voxels,which are present in a minimum percentage (e.g., $9 5 \%$ ) of participants. Subjects who overlap with the group mask less than a certain amount (e.g., $2 ^ { \star } \mathsf { S D }$ under the group mean overlap) can be excluded.

# 4) QC for head motion.

Beyond the head motion correction strategies discussed in section 2.1，excluding subjects with excessive head motion from statistical analysis is also essential. DPABl generates an Excel file including the following head motion metrics for each subject: max (or mean) absolute translations and rotations, mean RMS,mean FD Van Dijk (Van Dijk et al., 2012),mean FD Jenkinson (Jenkinson et al., 2O02),mean FD Power (Power et al, 2012a)，number of time points with mean FD Power $> 0 . 5$ (or 0.2)， percentage of time points with mean FD Power $> 0 . 5$ (or O.2). DPABl can pop up the head motion time course for each subject, and could threshold subjects according to their motion metrics. These quality control steps allow users to select those subjects with good quality and generate a subject list for statistical analysis.

# 2.5.Animal modules

To facilitate R-fMRl research on animal models, DPABl includes a module for macaque monkeys and a module for rats.

For monkey data processing, most of the steps are similar as for humans,except for spatial normalization. The individual monkey structural image is coregistered to the functional image.Then, using the monkey prior tissue probability maps generated by McLaren et al. (20o9), the transformed structural image is segmented into GM, WM and CSF through unified segmentation (Ashburner and Friston, 20o5). The functional volumes are normalized to the 112RM-SL space using the normalization parameters estimated during unified segmentation (McLaren et al., 2010; McLaren et al. 2009). The remaining steps follow the human processing pipeline.

For rat data processing, the voxel size of the rat structural and functional images is usually too small for the standard neuroimaging software packages, which were designed for human imaging. Thus, DPABl offers a function (Voxel Size Augmentor) to augment (usually 10 times) the voxel size. A rat T2 template (Schwarz et al., 20o6) is used for spatial normalization.

# 2.6. Other Utilities

DPABI provides a preprocessing pipeline for task-based fMRl, including DlCOM to NIfTl, slice timing,realignment, nuisance regression， spatial normalization,and smoothing. In addition, it also supports VBM analysis including segment structural images into GM, WM and CSF (Ashburner and Friston，20o5) and then uses the Diffeomorphic Anatomical Registration Through Exponentiated Lie algebra (DARTEL） tool (Ashburner， 2007） to compute transformations from individual native space to MNl space.

DPABl also offers a statistical analysis module supporting common statistical models. Furthermore, it estimates smoothness based on 4D residuals and writes to the NifTl headers.The smoothness is used for Gaussian random field (GRF) theory correction for multiple comparisons or Monte Carlo simulation (AlphaSim),as only using smooth kernels in preprocessing is not sufficient. Beyond multiple comparison corrections over voxels,DPABl offers a module to perform post-hoc comparison correction over group pairs after ANOVA analysis. Most neuroimaging studies perform pairwise two-sample t tests after ANOVA analysis,which provides no protection against multiple comparisons over group pairs.In DPABl, we introduced post-hoc procedures including Tukey-Kramer (honestly significant diference), Bonferroni, Dunn-Sidak and Scheffe control procedures. The corrected p values under a given control procedure for comparing group means of any pairs were calculated (e.g., through Studentized Range statistic for Tukey-Kramer correction) with the same route as MATLAB command multcompare (http://www.mathworks.com/help/stats/multcompare.html). The p maps were then converted to Z maps according to the Normal inverse cumulative distribution function (norminv), with the sign of group mean diferences applied. Using the Z maps,users can correct the significant voxels from ANOVA for multiple comparisons.To the best of our knowledge, this is the first neuroimaging package that offers post-hoc control procedures over multiple group pairs.

Finally, the results can be viewed in the DPABl viewer (based on spm's function spm_orthviews). DPABl Viewer allows displaying multiple images in different layers,as well as creating region of interest masks based on atlases or statistical maps.DPABl viewer reports the structure names of clusters and generates reports based on XjView (by Xu Cui, http://www.alivelearn.net/xjview8/). The viewer also provides an interface to the surface displaying tool, BrainNet Viewer (Xia et al.,2013), thus producing a volume map and a corresponding surface map with the same color and range settings.

In addition， DPABl provides utilities including a T1 Image defacer and multiple image averager. DPABl has also adapted the utilities of DICOM sorter, image calculator and image reslicer from REST.

# 3. Illlustration

# 3.1. Data

Here we used the publicly available imaging data from the 10oo Functional Connectomes Project (all data are available at http:/fcon_10oo.projects.nitrc.org) to demonstrate the functions of DPABl. The primary results were reported in Yan et al. (2013b); here we illustrate DPABl usage with re-generated figures. Datasets of 944 subjects from 18 sites, including an R-fMRl run and a T1-weighted anatomical image, were used for analyses.

# 3.2. Preprocessing

All preprocessing was performed using the advanced DPARSF module V3.2.Al volume slices were corrected for different signal acquisition times.Then，the time series of images for each subject were realigned. Individual structural images (T1-weighted MPRAGE）were co-registered to the mean functional image after realignment. The transformed structural images were then segmented into GM,WM and CSF (Ashburner and Friston，2005). The DARTEL tool (Ashburner，2007）was used to compute transformations from individual native space to MNl space. To remove the nuisance signals,the Friston 24-parameter model (Friston et al., 1996) was utilized to regress out head motion effects from the realigned data. The signals from WM and CSF were regressed out to reduce respiratory and cardiac efects.In addition, linear and quadratic trends were also included as regressors since the BOLD signal exhibits low-frequency drifts.Temporal filtering $( 0 . 0 1 - 0 . 1 \ \mathsf { H z } )$ was then performed on the time series except for the frequency-based R-fMRl indices: ALFF and fALFF.

The following R-fMRl-based indices of intrinsic brain function were examined: 1)ALFF (Zang et al., 2007) / fALFF (Zou et al.，2008); 2) ReHo (Zang et al.，2004); 3) VMHC (Anderson et al.，2011； Zuo et al., 2010b); 4) seed-based correlation analysis of the posterior cingulate cortex (PCC: 0,-53,26; 10mm diameter sphere) (Satterthwaite et al., 2012; Van Dijk et al., 2012; Yan et al., 2013a); and 5) network degree centrality (Buckner et al.,2009; Zuo et al., 2012). A comprehensive review of these rfMRl metrics is provided elsewhere (Zuo and Xing, 2014).

# 3.3. Quality Control

The quality control module was used to score datasets and exclude those that did not meet quality criteria. By rating the raw functional and structural images,as well as their normalization effects，using the rating function in DPABl, 49 subjects were excluded, leaving 895 subjects to be analyzed. Using the head motion thresholding function，33 subjects with motion (Mean FD Jenkinson (Jenkinson et al., 2012)) greater than $2 ^ { \star } \mathsf { S D }$ above the group mean motion (threshold: 0.192mm) were excluded，resulting in 862 subjects. A group mask was generated by including voxels present in at least $90 \%$ of participants (Figure 4). Finally，34 subjects with overlap with the group mask less than $2 ^ { \star } \mathsf { S D }$ under the group mean overlap (threshold: $9 2 . 2 \%$ ）were excluded,resulting in 828 subjects for group analyses. Those 828 subjects passing quality control were forwarded to further analysis.

# 3.4. Standardization

The standardization module was utilized to standardize the R-fMRl measures to reduce the impact of many sources of nuisance variation. Here, two standardization approaches were taken as examples.1) Mean Regression: calculate the global mean for each subject and then regress out the mean at the group-level. 2) Mean Regression $^ +$ SD Division: The residual value after mean regression is divided by the standard deviation for each subject.

# 3.5.Test-retest reliability

The TRT reliability module was used to evaluate the reliability of R-fMRl measures after standardization. The NYU TRT dataset, which contains three scans for each subject, was used to evaluate the ICC; the first scan (scan 1) was collected 5- 16 months (mean ± SD $= 1 1 \pm 4$ months) before two subsequent scans (scans 2 and 3), which were collected in a single session ${ \sim } 4 5$ minutes apart. We evaluated inter-session reliability as the ICC between scan 1 and the average of scans 2 and 3. ICC values were derived by linear mixed models (LMMs) as per Zuo et al. (2013). As demonstrated in Figure 5,ALFF without standardization showed very low TRT reliability,which would prevent its usage. With standardization,whether with mean regression or mean regression & SD division, ALFF showed moderate TRT reliability. All the other measures showed moderate TRT reliability，slightly reduced by standardization.The surface maps were produced by BrainNet Viewer (Xia et al., 2013), through an interface in the DPABl Viewer.

# 3.6. Statistical Analysis

The Statistical Analysis module was used to examine inter-individual differences in R-fMRl measures related to age while taking the confounding effects of sex， site and mean FD into account. Age effects were estimated by the t-value of the corresponding regressor in the general linear model. Gaussian random field theory correction for multiple comparisons was applied (voxel $Z { > } 2 . 3$ ，cluster-level $\mathsf { p } { < } 0 . 0 5$ ，corrected） for the voxel-wise maps of R-fMRl derivatives. As demonstrated in Figure 6, there were negative age associations with unstandardized R-fMRl measures across brain regions except for ALFF.After standardization, the distributed negative-relationships were removed; regions with remaining positive age effects are shown.

# 4.Discussion

Here we described the newly developed toolbox，DPABl，which includes an advanced edition of DPARSF (V3.2)，modules for head motion control， standardization，TRT reliability，quality control and rat/monkey data analysis pipelines. Processing of other imagingmodalities， including preprocessing modules for task-based fMRl and voxel-based morphometry analysis are included. DPABl also provides modules for statistical analysis,an MRl viewer and a series of image utilities.

We illustrated DPABl usage by applying it to a standardization project based on public datasets. With the integrated head motion control functions， DPABl makes it straightforward to evaluate results using strict motion correction strategies,to minimize spurious findings from motion effects. The standardization module minimizes the influence of nuisance variables on R-fMRl results.With the TRT reliability module, investigators can first test the reliability of their measures before investigating inter-individual differences.The quality control module helps users closely inspect their data,as adequate quality control is essential for establishing reliable and valid results. The statistical analysis module allws users to perform statistical analysis and multiple comparison corrections conveniently. Results can be viewed and high quality images exported easily using the viewer. Furthermore，the animal processing modules allow researchers to conveniently examine pharmacological/behavior manipulation effects and explore the underlying physiological mechanism and pathology related changes in R-fMRl data through animal studies.

DPABl is designed so that data analysis will require fewer manual operations,be less time-consuming，have a lower skill requirement， smaller possibility of inadvertent mistakes,and greater comparability across studies. Given these potential advantages, DPABl could set a standard data processing stream for R-fMRl data. If that were to occur, having data processed with the same procedure through the same software, should yield more comparable results across sites and an increase in their reproducibility (Poldrack and Poline,2015). The next step for DPABl is to create a data-sharing platform,and encourage users to share R-fMRl maps processed with DPABl. A large database of R-fMRl maps of subjects across various brain disorders could be accumulated through such a platform. Making R-fMRl maps available reduces computational demands and neuroimaging preprocessing skill requirements,thus allowing researchers from multiple disciplines to utilize big data to perform innovative studies. Moreover, such accumulated big data furthers the open science agenda to propose and address critical scientific questions (Milham,2012).

In sum，we assert that DPABl is user-friendly，allowing users to process data with a graphic user interface (GUl) (command line alternative available)， process statistical analyses and view the results.We hope this open-source toolbox willassist novices (via the user-friendly GUl） and expert users (by efficient command line） and continue to support advancing R-fMRl methodology and its application to clinical translational studies.

# Information Sharing Statement

The source code of DPABl is openly shared at http://rfmri.org/DPABl.

# Acknowledgements

The authors appreciate the editorial assistance and support of Dr. Francisco X. Castellanos. Dr. Yan and Dr. Zuo acknowledge the support of the Hundred Talents Program of the Chinese Academy of Sciences (CGY: Y5CX072006; XNZ: Y2CS112006). Dr. Yan and Dr. Zuo are also members of the international collaboration team (under its trial stage with Pl: Dr. Xun Liu) supported by the CAS K.C.Wong Education Foundation. Dr. Zang is partly supported by “Qian Jiang Distinguished Professor” program.

# Conflict of interest statement

DPABl is hosted at the R-fMRl Network (http://fmri.org)，which is a non-commercial resource for the R-fMRl community.

# References

ADHD-200-Consortium (2012). The ADHD-200 Consortium: A Model to Advance the Translational Potential of Neuroimaging in Clinical Neuroscience. Front Syst Neurosci, 6,62,doi:10.3389/fnsys.2012.00062.

Anderson， J.S., Druzgal, T.J.，Froehlich，A.，DuBray，M.B., Lange，N., Alexander, A.L., Abildskov，T.，Nielsen，J.A.，Cariello，A.N.，Cooperrider，J.R.，Bigler，E.D., Lainhart， J.E. (2011). Decreased interhemispheric functional connectivity in autism.Cerebral cortex,21(5), 1134-1146,doi:10.1093/cercor/bhq190.

Ashburner，J. (20o7).A fast diffeomorphic image registration algorithm.Neuroimage, 38(1), 95-113, doi:10.1016/j.neuroimage.2007.07.007.

Ashburner， J. (2012). SPM: a history. Neuroimage, 62(2), 791-800, doi:10.1016/j.neuroimage.2011.10.025.

Ashburner, J.， Friston, K.J. (2005). Unified segmentation. Neuroimage, 26(3), 839-851, doi:S1053-8119(05)00110-2 [pi]

10.1016/j.neuroimage.2005.02.018.

Bandettini， P.A. (2012). Twenty years of functional MRl: the science and the stories. Neuroimage,62(2), 575-588, doi:10.1016/j.neuroimage.2012.04.026.

Behzadi, Y., Restom,K., Liau, J.,Liu,T.T. (20o7). A component based noise correction method (CompCor) for BOLD and perfusion based fMRl. Neuroimage，37(1), 90-101, doi:10.1016/j.neuroimage.2007.04.042.

Birn,R.M. (2012). The role of physiological noise in resting-state functional connectivity.

Neuroimage, 62(2), 864-870,doi:10.1016/j.neuroimage.2012.01.016.

Biswal, B., Yetkin, F.Z., Haughton, V.M., Hyde, J.S.(1995). Functional connectivity in the motor cortex of resting human brain using echo-planar MRl. Magn Reson Med, 34(4), 537-541.

Biswal, B.B., Mennes, M., Zuo, X.N., Gohel, S., Kelly, C., Smith, S.M., Beckmann, C.F.,Adelstein,J.S.， Buckner， R.L.， Colcombe,S.，Dogonowski， A.M.， Ernst,M.,Fair,D.,Hampson, M., Hoptman, M.J., Hyde, J.S.， Kiviniemi, V.J.， Kotter, R., Li, S.J.,Lin,C.P., Lowe, M.J., Mackay, C., Madden, D.J., Madsen, K.H.，Margulies, D.S.,Mayberg，H.S.，McMahon，K.， Monk， C.S.， Mostofsky， S.H.， Nagel， B.J.， Pekar,

J.J.，Peltier， S.J.， Petersen， S.E.， Riedl，V.， Rombouts，S.A.， Rypma，B,Schlaggar, B.L., Schmidt, S., Seidler, R.D., G, J.S., Sorg, C., Teng, G.J., Veijola,

J.，Villringer，A.，Walter， M.，Wang，L.，Weng，X.C.，Whitfield-Gabrieli，S., Williamson，P.，Windischberger， C., Zang，Y.F.， Zhang，H.Y.，Castellanos,F.X., Milham，M.P. (2010). Toward discovery science of human brain function. Proc Natl Acad Sci U S A, 107(10), 4734-4739, doi:0911855107 [pi]

10.1073/pnas.0911855107.

Buckner, R.L., Krienen,F.M., Yeo, B.T. (2013). Opportunities and limitations of intrinsic functional connectivity MRl. Nat Neurosci, 16(7), 832-837, doi:10.1038/nn.3423.

Buckner， R.L.， Sepulcre，J.， Talukdar，T.， Krienen， F.M.， Liu， H.， Hedden，T. Andrews-Hanna， J.R.，Sperling，R.A.，Johnson，K.A. (2009)． Cortical hubs revealed by intrinsic functional connectivity: mapping, assessment of stability, and

relation to Alzheimer's disease. J Neurosci, 29(6), 1860-1873, doi:29/6/1860 [pii] 10.1523/JNEUROSCI.5062-08.2009.

Castellanos，F.X.， Di Martino，A.， Craddock，R.C.，Mehta， A.D.， Milham，M.P. (2013).Clinical applications of the functional connectome. Neuroimage，80，527-540,doi:10.1016/j.neuroimage.2013.04.083.

Chai，X.J., Castanon，A.N.， Ongur，D.,Whitfield-Gabrieli， S. (2012).Anticorrelations in resting state networks without global signal regression. Neuroimage，59(2), 1420-1428, doi:10.1016/j.neuroimage.2011.08.048.

Cole,D.M., Smith， S.M., Beckmann, C.F. (2010). Advances and pitfalls in the analysis and interpretation of resting-state FMRl data. Front Syst Neurosci， 4，8, doi:10.3389/fnsys.2010.00008

Cox, R.W. (2012). AFNl: what a long strange trip it's been. Neuroimage, 62(2), 743-747, doi:10.1016/j.neuroimage.2011.08.056.

Di Martino, A., Yan, C.G., Li, Q., Denio, E., Castellanos, F.X., Alaerts, K., Anderson, J.S.,Assaf, M.， Bookheimer， S.Y.， Dapretto，M., Deen,B.，Delmonte,S.， Dinstein, I.,Ertl-Wagner, B.， Fair, D.A., Gallagher,L., Kennedy, D.P., Keown, C.L., Keysers,C.,Lainhart, J.E.， Lord， C.， Luna，B.，Menon，V.， Minshew，N.J.，Monk， C.S.,Mueller， S.，Muller，R.A.，Nebel， M.B.，Nigg， J.T.，O'Hearn，K.， Pelphrey，K.A.,Peltier， S.J.， Rudie，J.D.， Sunaert， S.， Thioux，M.， Tyszka，J.M.， Uddin，L.Q.,Verhoeven，J.S.，Wenderoth，N.，Wiggins, J.L.，Mostofsky， S.H.，Milham，M.P.

(2014). The autism brain imaging data exchange: towards a large-scale evaluation of the intrinsic brain architecture in autism. Mol Psychiatry，19(6), 659-667,doi:10.1038/mp.2013.78.

Fair, D.， Nigg, J.T., lyer, S., Bathula, D.， Mils,K.L., Dosenbach，N.U., Schlaggar, B.L.,Mennes, M., Gutman, D., Bangaru, S., Buitelaar, J.K., Dickstein, D.P., Di Martino,A.， Kennedy， D.N.， Kelly， C.， Luna，B.， Schweitzer， J.B.， Velanova,K.，Wang,Y.-F.，Mostofsky， S.H.，Castellanos，F.X.，Milham，M.P. (2012). Distinct NeuralSignatures Detected for ADHD Subtypes After Controling for Micro-Movements inResting State Functional Connectivity MRl Data. Front Syst Neurosci， 6,doi:10.3389/fnsys.2012.00080.

Fox，M.D.，Greicius，M. (2010). Clinical applications of resting state functional connectivity. Front Syst Neurosci, 4，19, doi:10.3389/fnsys.2010.00019.

Fox, M.D., Raichle, M.E. (2o07). Spontaneous fluctuations in brain activity observed with functional magnetic resonance imaging. Nat Rev Neurosci, 8(9), 700-711.

Friedman，L.，Glover，G.H. (2006). Report on a multicenter fMRl quality assurance protocol. J Magn Reson Imaging, 23(6), 827-839, doi:10.1002/jmri.20583.

Friston， K.J.， Williams， S.， Howard， R.， Frackowiak， R.S.， Turner， R. (1996).Movement-related effects in fMRl time-series. Magn Reson Med, 35(3), 346-355.

Greicius，M. (2oo8). Resting-state functional connectivity in neuropsychiatric disorders. Curr Opin Neurol, 21(4), 424-430,doi:10.1097/WCO.0b013e328306f2c5 00019052-200808000-00007 [pi].

Huettel， S.， Song，A.， McCarthy， G. (2004). Functional magnetic resonance imaging:

SinauerAssociatesSunderland,MA

Hutchison, R.M., Everling, S.(2012). Monkey in the middle: why non-human primates are needed to bridge the gap inresting-state investigations. Frontiersin neuroanatomy,6,29, doi:10.3389/fnana.2012.00029.

Ihalainen,T.， Sipila, O., Savolainen， S. (2004). MRl quality control: six imagers studiedusing eleven unified image quality parameters. Eur Radiol， 14(10)， 1859-1865,doi:10.1007/s00330-004-2278-4.

Jenkinson,M.， Bannister,P.,Brady，M.， Smith，S. (2002). Improved optimization for the robust and accurate linear registration and motion correction of brain images. Neuroimage, 17(2), 825-841.

Jenkinson,M.,Beckmann, C.F., Behrens,T.E.,Woolrich,M.W., Smith,S.M.(2012).FSL.Neuroimage, 62(2)， 782-790, doi:10.1016/j.neuroimage.2011.09.015.

Kelly，C.， Biswal， B.B.，Craddock，R.C.， Castellanos，F.X.，Milham，M.P. (2012). Characterizing variation in the functional connectome: promise and pitfalls. Trends Cogn Sci, 16(3), 181-188,doi:10.1016/j.tics.2012.02.001.

Lowe，M.J.，Mock，B.J.， Sorenson， J.A. (1998). Functional connectivity in single and multislice echoplanar imaging using resting-state fluctuations. Neuroimage,7(2), 119-132.

McLaren， D.G.，Kosmatka，K.J.，Kastman， E.K.，Bendlin，B.B.， Johnson，S.C. (2010).Rhesus macaque brain morphometry: a methodological comparison of voxel-wiseapproaches.Methods, 50(3)，157-165,doi:10.1016/j.ymeth.2009.10.003.

McLaren， D.G., Kosmatka, K.J.， Oakes， T.R., Kroenke, C.D., Kohama， S.G., Matochik, J.A., Ingram, D.K., Johnson, S.C. (2009). A population-average MRl-based atlas collection of the rhesus macaque. Neuroimage，45(1), 52-59, doi:10.1016/j.neuroimage.2008.10.058.

Mennes,M., Biswal, B.B., Castellanos, F.X., Milham, M.P. (2013). Making data sharing work: The FCP/INDI experience. Neuroimage, 82, 683-691, doi:10.1016/j.neuroimage.2012.10.064.

Milham,M.P.(2012). Open neuroscience solutions for the connectome-wide association era. Neuron, 73(2),214-218,doi:10.1016/j.neuron.2011.11.004.

Poldrack，R.A.， Poline， J.B. (2015).The publication and reproducibility challenges of shared data. Trends Cogn Sci, 19(2), 59-61, doi:10.1016/j.tics.2014.11.008.

Power， J.D.，Barnes，K.A.， Snyder， A.Z.，Schlaggar， B.L.， Petersen，S.E. (2012a). Spurious but systematic correlations in functional connectivity MRl networks arise from subject motion. Neuroimage, 59(3), 2142-2154, doi:S1053-8119(11)01181-5 [pii]

10.1016/j.neuroimage.2011.10.018.

Power, J.D., Barnes, K.A., Snyder, A.Z., Schlaggar, B.L., Petersen, S.E. (2012b). Steps toward optimizing motion artifact removal in functional connectivity MRl; a reply to Carp. Neuroimage,doi:10.1016/j.neuroimage.2012.03.017.

Power， J.D.， Mitra，A.， Laumann， T.O.， Snyder， A.Z.， Schlaggar， B.L.， Petersen， S.E.(2014). Methods to detect， characterize，and remove motion artifact in restingstate fMRl. Neuroimage,84C, 320-341, doi:10.1016/j.neuroimage.2013.08.048.

Power, J.D.， Schlaggar， B.L.， Petersen, S.E. (2015). Recent progress and outstanding issues in motion correction in resting state fMRl. Neuroimage，105， 536-551, doi:10.1016/j.neuroimage.2014.10.044.

Satterthwaite, T.D., Elliott, M.A., Gerraty, R.T., Ruparel, K., Loughead,J., Calkins, M.E., Eickhoff， S.B.，Hakonarson，H.，Gur， R.C.，Gur， R.E.，Wolf, D.H. (2013).An improved framework for confound regression and filtering for control of motion artifact in the preprocessing of resting-state functional connectivity data. Neuroimage, 64,240-256,doi:10.1016/j.neuroimage.2012.08.052.

Satterthwaite, T.D., Wolf, D.H., Loughead, J., Ruparel, K., Elliott, M.A., Hakonarson, H., Gur，R.C.，Gur， R.E. (2012). Impact of in-scanner head motion on multiple measures of functional connectivity: Relevance for studies of neurodevelopment in youth. Neuroimage, 60(1), 623-632, doi:10.1016/j.neuroimage.2011.12.063.

Sawiak, S.,Wiliams, G.,Wood, N., Morton, A., Carpenter, T., 2009.SPMMouse: A new toolbox for SPM in the animal brain. ISMRM 17th Scientific Meeting & Exhibition, April, pp.18-24.

Schwarz, A.J., Danckaert, A., Reese, T., Gozzi, A., Paxinos, G., Watson, C., Merlo-Pich, E.V., Bifone,A. (2006). A stereotaxic MRl template set for the rat brain with tissue class distribution maps and co-registered anatomical atlas: application to pharmacological MRI. Neuroimage, 32(2), 538-550, doi:10.1016/j.neuroimage.2006.04.214.

Shehzad, Z.， Kely, A.M.，Reiss,P.T.， Gee, D.G.， Gotimer, K.， Uddin, L.Q., Lee， S.H.,Margulies, D.S.， Roy, A.K., Biswal, B.B.， Petkova, E., Castellanos, F.X., Milham,M.P.(2009). The resting brain: unconstrained yet reliable. Cereb Cortex, 19(10),2209-2229,doi:bhn256 [pi]

10.1093/cercor/bhn256 [doi].

Shrout, P.E., Fleiss,J.L.(1979). Intraclass correlations: uses in assessing rater reliability. Psychol Bull, 86(2)， 420-428.

Simmons，A.，Moore，E.，Williams， S.C.(1999). Quality control for functional magnetic resonance imaging using automated data analysis and Shewhart charting. Magn Reson Med, 41(6), 1274-1278.

Song,X.W., Dong, Z.Y., Long, X.Y., Li, S.F., Zuo, X.N., Zhu, C.Z., He, Y., Yan, C.G., Zang，Y.F. (2011). REST: A Toolkit for Resting-State Functional Magnetic Resonance Imaging Data Processing. PLoS ONE, 6(9), e25031, doi:10.1371/journal.pone.0025031   
PONE-D-11-09456 [pii].

Taylor， P.A.， Saad， Z.S. (2013). FATCAT: (an efficient) Functional and Tractographic Connectivity Analysis Toolbox. Brain Connect, 3(5), 523-535, doi:10.1089/brain.2013.0154.

Van Dijk, K.R., Sabuncu, M.R., Buckner, R.L. (2012). The influence of head motion on intrinsic functional connectivity MRI. Neuroimage, 59(1), 431-438, doi:10.1016/j.neuroimage.2011.07.044.

Whitfield-Gabrieli, S., Nieto-Castanon, A. (2012). Conn: a functional connectivity toolbox for correlated and anticorrelated brain networks. Brain Connect, 2(3)， 125-141, doi:10.1089/brain.2012.0073.

Xia, M., Wang,J., He,Y. (2O13). BrainNet Viewer: a network visualization tool for human brain connectomics. PLoS ONE, 8(7), e68910, doi:10.1371/journal.pone.0068910.

Yan,C., Zang, Y. (2010). DPARSF: A MATLAB Toolbox for "Pipeline" Data Analysis of Resting-State fMRl. Front Syst Neurosci, 4， 13, doi:10.3389/fnsys.2010.00013.

Yan, C.G.， Cheung， B., Kelly, C.， Colcombe, S., Craddock， R.C., Di Martino,A., Li, Q.,Zuo， X.N.， Castellanos， F.X.， Milham， M.P. (2013a)． A comprehensiveassessment of regional variation in the impact of head micromovements onfunctional connectomics. Neuroimage, 76, 183-201,doi:10.1016/j.neuroimage.2013.03.004.

Yan, C.G., Craddock, R.C., Zuo, X.N., Zang, Y.F., Milham, M.P. (2013b). Standardizing the intrinsic brain: towards robust measurement of inter-individual variation in 1000 functional connectomes. Neuroimage, 80, 246-262, doi:10.1016/j.neuroimage.2013.04.081.

Yan，C.G., Li, Q.， Gao,L. (2014). PRN: a preprint service for catalyzing R-fMRl and neuroscience related studies. F1000Res, 3, 313, doi:10.12688/f1000research.5951.2.

Zang,Y.F.， He, Y.， Zhu, C.Z., Cao, Q.J., Sui, M.Q., Liang, M.， Tian,L.X., Jiang,T.Z.,

Wang,Y.F. (2007). Altered baseline brain activity in children with ADHD revealed by resting-state functional MRl. Brain Dev, 29(2), 83-91.

Zang，Y.F.， Jiang，T.Z.， Lu，Y.L.，He，Y.， Tian，L.X. (2004). Regional homogeneity approach to fMRl data analysis. Neuroimage,22(1),394-400.

Zou, Q.H., Zhu, C.Z., Yang, Y., Zuo, X.N., Long, X.Y., Cao, Q.J., Wang, Y.F., Zang, Y.F. (2008). An improved approach to detection of amplitude of low-frequency fluctuation (ALFF） for resting-state fMRl: fractional ALFF. J Neurosci Methods, 172(1), 137-141, doi:S0165-0270(08)00245-8 [pi]

10.1016/j.jneumeth.2008.04.012.

Zuo,X.N., Ehmke，R., Mennes,M., Imperati, D., Castellanos, F.X., Sporns, O., Milham, M.P.(2012). Network Centrality in the Human Functional Connectome. Cereb Cortex,22(8)， 1862-1875,doi:10.1093/cerc0r/bhr269.

Zuo,X.N., Kelly, C., Adelstein, J.S., Klein, D.F., Castellanos, F.X., Milham, M.P. (2010a). Reliable intrinsic connectivity networks: test-retest evaluation using ICA and dual regression approach. Neuroimage, 49(3), 2163-2177, doi:10.1016/j.neuroimage.2009.10.080.

Zuo，X.N.，Kelly，C.，Di Martino，A.，Mennes，M.，Margulies，D.S.，Bangaru，S., Grzadzinski, R., Evans, A.C., Zang, Y.F., Castellanos, F.X., Milham, M.P. (2010b). Growing together and growing apart: regional and sex differences in the lifespan developmental trajectories of functional homotopy. J Neurosci， 30(45), 15034-15043,doi:10.1523/JNEUROSCI.2612-10.2010.

Zuo，X.N.， Xing， X.X. (2011). Effects of non-local diffusion on structural MRl preprocessing and default network mapping: statistical comparisons with isotropic/anisotropic diffusion. PLoS ONE, 6(10), e26703, doi:10.1371/journal.pone.0026703.

Zuo, X.N., Xing, X.X. (2014). Test-retest reliabilities of resting-state FMRl measurements in human brain functional connectomics: a systems neuroscience perspective. Neurosci Biobehav Rev, 45, 100-118, doi:10.1016/j.neubiorev.2014.05.009.

Zuo, X.N., Xu, T., Jiang, L., Yang, Z., Cao, X.Y., He, Y., Zang, Y.F., Castellanos, F.X., Milham，M.P. (2013). Toward reliable characterization of functional homogeneity inthe human brain: Preprocessing， scan duration， imaging resolution and computational space. Neuroimage, 65, 374-386, doi:10.1016/j.neuroimage.2012.10.017.

# Figure Legends

Fig1 DPABl's graphical user interface.

Fig 2 The quality control user interface.Quality control steps include assessing the quality of raw functional and structural images, spatial normalization, coverage and head motion.

Fig 3 Quality control for spatial normalization. Upper left: normalized structural image with the standard grey matter/white matter boundary overlaid; upper right: normalized functional image； lower left: normalized gray matter segmentation； lower right: MNl template; middle: interface for users to give QC scores and comment.

Fig 4 The group mask generated by including voxels present in at least $90 \%$ of participants.

Fig 5 The test-retest reliability (indexed by intra-class correlations) of the R-fMRl measures with and without standardization.

Fig 6 The age effects of R-fMRl measures with and without standardization.Warm colors indicate positive correlations with age and cool colors indicate negative correlations with age.

![](images/e6cc81db9b888096442256cd49db96dee6727064a30f869e1831fe598a5bd816.jpg)

![](images/f1d28bc7c51c36f6660c4c2f6c0f4f387ecf4c8fd72fa80045645a5d513413ed.jpg)

![](images/78e68fe4a7ce1b879bc24f1174b3aa7cbe312f310e466b89d8f92787eae6c85c.jpg)

![](images/6d7bb7e4f7e0f0e43b33a4e32753dcee1c4b611be7f4cece4e1c3523125aea58.jpg)

![](images/d157cac6016cc3d65701a5132fe47883753d0243ad0b3c596678915c91641607.jpg)