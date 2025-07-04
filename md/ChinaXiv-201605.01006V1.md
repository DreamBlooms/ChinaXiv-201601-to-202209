# Strategy of tuning gene expression ratio in prokaryotic cell from perspective of noise and correlation

Rui Liä, Liufang ${ \sf X } { \bf u } ^ { \mathrm { \Delta b } }$ ,Hualin Shi a,\*

StateKeyLboratoryoforeticalysics,siuteofeorticalysicsiesecdemyfiences,eijingin b Departmentof Physics and Biophysics & Complex System Center,Jilin University,Changchun 130012,China

# HIGHLIGHTS

·Strategy of tuning gene expression ratio from perspective of noise and correlation is discussed.   
·Analyticalresultsof genes expression noiseand corelation for the two-stateand theconstitutive promoterare given.   
·Noisesadcoelaioofgeeexpressosiopeoniththetostatepromerareighertaninoperonithtostiutieooter ·Polar effect obviously lowers the correlation between genes in operons.   
· Tuning translation rates is the optimal strategy to tune gene expression ratio in operon.

# ARTICLEINFO

Article history:   
Received 1 April 2014   
Received in revised form   
31 October 2014   
Accepted 3 November 2014   
Available online 11 November 2014   
Keywords:   
Polar effect   
The two-state promoter   
Transcription terminator   
Gene expression correlation   
Operon structure

# ABSTRACT

Genes are organized into operons in procaryote,and these genes in one operon generally have related functions.However, genes in the same operon are usually not equally expressed,and the ratio needs to be fine-tuned for specific functions.We examine the diference of gene expression noise and correlation when tuning the expression level at the transcriptional or translational level in a bicistronic operon driven by a constitutive or a two-state promoter. We get analytic results for the noise and correlation of gene expresson levels,which is confirmed by our stochastic simulations.Both the noise and the correlation of gene expressions in an operon with a two-state promoter are higher than in an operon with a constitutive promoter. Premature termination of mRNA induced by transcription terminator in the intergenic region or changing translation rates can tune the protein ratio at the transcriptional level or at the translational level. We find that gene expresson correlation between promoter-proximal and promoter-distal genes at the protein level decreases as termination increases.In contrast,changing translation rates in the normal range almost does not alter the correlation.This explains why the translation rate is a key factor of modulating gene expressons in an operon. Our results can be useful to understand the relationship between the operon structure and the biological function of a gene network, and also may help in synthetic biology design.

$\circledcirc$ 2014 Elsevier Ltd.All rights reserved.

# 1．Introduction

An operon is a unit of genomic DNA containing a cluster of genes under the control of a single promoter (Jacob and Monod, 1961).Genes in an operon generally belong to the same function class (Salgado and Moreno-Hagelsieb,2ooo; Dandekar et al.,1998), and they are transcribed together into a mRNA strand.Their expressions can be regulated coordinately,which is one of the reasons that genes are organized into operons (Price et al.,2005).

Gene expression is noisy,which can influence its function (Eldar and Elowitz, 201O;Hao et al., 2011a; Paulsson et al., 2000; Rayand Igoshin,2012；Chalancon et al.，2012).Noise from the stochasticity of transcription and translation process is recognized as the intrinsic noise.Noise introduced by other factors such as different concentrations of RNA polymerase,ribosome or transcription factors is recognized as the extrinsic noise.The extrinsic noise is relatively slow in the same environment (Taniguchi et al., 2010;Rosenfeld et al., 2Oo5). Intrinsic and extrinsic noises together determine the gene expression profile (Taniguchi et al., 2010; Rosenfeld et al., 2005;Paulsson, 2004).

Proteins work together to execute specific functions in the cell. Different components in the same pathway need to be coordinated to get the robust result.For example,protein complex formation is most efficient when subunits of a protein complex are expressed with the needed ratio (Carmi et al.,2006,2009；Swain,2004). Expressions of enzymes ina metabolism pathwayusually need to be correlated to avoid intermediate product cumulation(Rayand Igoshin,2012）which may be toxic. Experiment shows that gene expressions in the same operon are more correlated together than those in the separated operons even with identical promoters, especially when gene expression levels are low(Tabor et al., 2008). The strengthened correlation can be explained by co-transcription (Sneppen et al.,2010;Swain,2004;Ray and Igoshin, 2012;Iber, 2006) or in some cases also by co-translation (Swain,2oO4;Iber, 2006).Statistics from Escherichia coli genomics indicate that for genes with products in linear metabolic pathways,with physical interactions and in covalent modification modules,they are more likely to be organized into operons(Rayand Igoshin,2O12). Noise of the genes expression from one operon can be further attenuated bydifferent mechanisms,for example,transcriptional or translational feedback(Swain,2oo4). Sometimes subunits of macromolecular complex are produced from different operons.Swain (2004) shows that both translational and transcriptional feedback canincrease the correlation between these subunits,but translational feedback is more efficient.

However,even in the same operon,genes are not expressed at the equivalent level. The cell needs to fine-tune the gene expression ratio to fit their biological functions.The tuning can be executed at the transcriptional or the translational level. In this work,we try to study the difference of noise and correlation when the cell takes distinct tuning strategies.

Tuning transcription rate or stability of mRNA can change the mRNA level,which will be passed to the protein levels by translation.Lifetime of mRNAsin bacteriaisrelatively short.Most mRNAs will be degraded by various ribonucleases(Condon,2007) and live only several minutes (Selinger et al., 2oo3; Bernstein et al., 2002；Kristoffersen et al.,2O12). Different transcription rates can be introduced by the internal promoter or terminator. Intergenic Rho-dependent or Rho-independent (Lesnik et al.,2Oo1） terminator can introduce the polar effect which means genes in the promoter-proximal region are transcribed more compared with the promoter-distal ones.Recently, transcriptome sequencing of Mycoplasma pneumoniae (Giell et al., 2Oo9) and synthetic biology studies in E. coli(Nishizaki etal.,20O7;Hiroe etal.,2012) indicate that this effect might be a global phenomenon even foran operon without an obvious termination signal in the intergenic region.As for mRNA degradation rate，although distinct regions in one operon may have different degradation rates (Selinger et al., 2003；Kristoffersen et al.，2012)，for those genes with close function relationship,their transcripts seem to have the similar degradation rates (Bernstein et al.,2Oo2; Kristoffersen et al., 2012; Quax et al.,2O13).Previous works indicate that co-transcription of genes in one operon is the main source of correlation (Sneppen et al., 2010; Swain, 2004; Ray and Igoshin, 2012; Iber, 2006), so it can be expected that tuning gene expression ratio at transcriptional level would lower the correlation.

Although it cannot be ruled out that tuning translation degradation would be one of the mechanisms to adjust the protein expression level,it is well known that most proteins in the prokaryotic cell are not degraded to avoid wasting (Gur et al., 2011).It is more likely that cells tune a protein level byadjusting protein synthesis rate.Many features embedded in coding and non-coding regions of the mRNA sequence can influence the translation initiation and elongation rate.The Shine-Dalgarno sequence and its distance to translation initiation codon will affect the assembling of translation complex(Vellanoweth and Rabinowitz,1992;Chen et al.,1994). The structure of $5 ^ { \prime }$ -UTRwill affect the accessibility of the ribosome binding site(Goodman et al.,2013；Bentele et al., 2013;Hao et al., 2011b). Codon usage willinfluencetranslation elongation(Tulleret al.， 2010; Cannarrozzi et al.，2010； Klumpp et al.， 2012). The internal Shine-Dalgarno like sequence may induce translation pausing(Li et al., 2012; Wen et al., 2008).

In this work,we use stochastic models to describe the transcription and translation processes of a bicistronic operon driven bya constitutive ora two-state promoter (Fig.1A) respectively.We get analytical results of intrinsic noise and correlation of gene expressions.We utilize termination efficiency of terminator to characterize the stiffness of polar effect,i.e.,the ratio of transcripts that are prematurely terminated.Stochastic simulations confirm our analytical results.Our results show that the correlation between proteins decreases monotonously as termination efficiency increases and the correlation almost does not varyas the translation rate changes in the normal range.It may help to understand gene organization and its evolution in prokaryotes.

# 2.The bicistronic operon with the constitutive promoter

In our analysis,we focus on the statistics when the system is in the steady state.We use $\langle q \rangle$ and $\delta q ^ { 2 }$ to denote the mean and variance of numbers of species $q$ ，the Fano factor $\nu = \delta q ^ { 2 } / \langle q \rangle$ and coefficient of variance $\dot { \eta } = \sqrt { \delta q ^ { 2 } } / \langle q \rangle$ to characterize noise.The Fano factor can be a measurement for deviation from the Poisson behavior.It takes the value of 1 for a Poisson process.We use the Pearson_correlation coefficient $\rho = \langle ( q _ { 1 } - < q _ { 1 } > ) ( q _ { 2 } - < q _ { 2 } > ) \rangle / \$ $\sqrt { \delta q _ { 1 } ^ { 2 } \delta q _ { 2 } ^ { 2 } }$ to denote the correlation of the numbers of two species $q _ { 1 }$ and $q _ { 2 }$

![](images/570deb99ccb8cbbb324418ac03d0f9326bd46aa526daeb60fb12fb430e095f37.jpg)  
Fig.1.(A) Two kinds of promoters used in our study.(B) Gene expression process of the bicistronic operon with the constitutive promoter.T1 represents any kind of polar effect mechanism:Rho-dependent or Rho-independent terminator in intergenic region of operon or other possible mechanisms (Güiell et al.,2Oo9).The termination efficiency of $\mathrm { T } 1$ is e,the transcription rate of promoter is $K ,$ the translation rates of RFP and GFP are $K _ { P R }$ and $K _ { P G }$ ,the degradation rates of R,RG,RFP and GFP are respectively $\gamma _ { R }$ ，YRG， $\gamma _ { P R }$ and $\gamma _ { P G }$ .For the two-state promoter $K$ should be replaced with $k _ { T X } ,$ and transcription happens only when the promoter is in the on state.

# 2.1.The model of the bicistronic operon with the constitutive promoter

The state of a gene expression system can be specified by the numbers of mRNA molecules and proteins.For the stochasticity of gene expression,there are fluctuations in these numbers.We can describe this kind system by a joint distribution function $f ( q _ { 1 } , q _ { 2 } , . . . q _ { i } . . . , q _ { n } ; t )$ ,here $q _ { i }$ is the number of i-th molecule,which will be mRNA or protein.We simply write $f ( q _ { 1 } , q _ { 2 } , . . . q _ { i } . . . , q _ { n } ; t )$ as $f _ { q _ { i } }$ ,and $i$ is ranging from 1 to n. For simplicity,we suppose that the birth and death rates of molecules in the system are linearly dependent on the numbers of different species.Then dynamic evolution of $f _ { q _ { i } }$ is described in the scheme:

$$
\begin{array} { l } { { f _ { q _ { i } } \overset { k _ { i } ^ { + } ( q _ { j } ) } { \longrightarrow } f _ { q _ { i } + 1 } } } \\ { { \ } } \\ { { f _ { q _ { i } } \overset { k _ { i } ^ { - } ( q _ { j } ) } { \longrightarrow } f _ { q _ { i } - 1 } } } \\ { { \ } } \\ { { k _ { i } ^ { + } ( q _ { j } ) = \sum _ { j } { A _ { i j } q _ { j } } , \quad k _ { i } ^ { - } ( q _ { j } ) = \sum _ { j } { T _ { i j } q _ { j } } , } } \end{array}
$$

where $k _ { i } ^ { + } ( q _ { j } )$ and $k _ { i } ^ { - } ( q _ { j } )$ denote the birth and death rates of $i .$ -th molecule,matrices $A$ and $\boldsymbol { { \cal T } }$ provide the coefficients of their linear dependence on the molecular numbers.

We study the system of a bicistronic operon as described in Fig.1B.We use RFP and GFP to denote genes in the operon with RFP near the promoter. These two fluorescent proteins can be employed in an experiment to check our theoretical results.T1 is Rho-dependent or independent terminator or any other possible mechanism that would attenuate downstream gene transcription. T2is the terminator that defines the end of the operon. Termination efficiency of T1 isdenoted as e,which also represents the stiffness of polar effect for the operon.For simplicity,we suppose that transcription and translation rates do not depend on each other.Although transcription and translation are coupled together in prokaryote,this assumption is still suitable for most of the cases.

We first study the bicistronic operon with the constitutive promoter. Transcription start from the constitutive promoter at the rate $K$ as shown in Fig.1B.Two kinds of mRNA are transcribed from this operon. One is full-length mRNA with both RFP and GFP, which is denoted as RG.The other one is attenuated mRNA only with RFP,which is denoted as $R .$ The synthesis rate of $R$ and RG are $K _ { R } = e K$ and $K _ { R G } = ( 1 - e ) K$ ，The translation rates of RFP and GFP are $K _ { P R }$ and $K _ { P G }$ ，the degradation rates of $R ,$ RG,RFP and GFP are respectively $\gamma _ { R } , \gamma _ { R G } , \gamma _ { P R }$ and $\gamma _ { P G }$ . If we consider the growth dilution, the effective degradation rate $\gamma = \gamma _ { d e g r a d } + \mu$ where $\gamma _ { d e g r a d }$ is the degradation rate and $\mu$ is the growth rate of the cell.In our system, $q _ { i } = \{ D , R , R G , R F P , G F P \}$ ，where $D$ is the number of DNA,i.e.,the copy number of the operon.Matrices $A$ and $\boldsymbol { { \cal T } }$ for this bicistronic operon with the constitutive promoter are:

$$
A = \left[ \begin{array} { c c c c c } { 0 } & { 0 } & { 0 } & { 0 } & { 0 } \\ { K _ { R } } & { 0 } & { 0 } & { 0 } & { 0 } \\ { K _ { R G } } & { 0 } & { 0 } & { 0 } & { 0 } \\ { 0 } & { K _ { P R } } & { K _ { P R } } & { 0 } & { 0 } \\ { 0 } & { 0 } & { K _ { P G } } & { 0 } & { 0 } \end{array} \right] , \quad T = \left[ \begin{array} { c c c c c } { 0 } & { 0 } & { 0 } & { 0 } & { 0 } \\ { 0 } & { \gamma _ { R } } & { 0 } & { 0 } & { 0 } \\ { 0 } & { 0 } & { \gamma _ { R G } } & { 0 } & { 0 } \\ { 0 } & { 0 } & { 0 } & { \gamma _ { P R } } & { 0 } \\ { 0 } & { 0 } & { 0 } & { 0 } & { \gamma _ { P G } } \end{array} \right] .
$$

Transcription process of the bicistronic operon with the constitutive promoter includes a transcription initiation at rate $K$ followed by a termination at the T1 terminator with a possibility of e(Fig.1B). In our model,we used an equivalent description:two independent transcription processes of $R$ and RG with the rates of $K _ { R } = e K$ and $K _ { R G } = ( 1 - e ) K$ .It is easy to prove that these two descriptions give the same distributions of $R$ and RG: two independent Poisson distributions.

2.1.1.Method to get the means and variances.

We use a similar approach as Thattai and van Oudenaarden (2001）in our theoretical derivations.The above scheme for our model can be described by the following Master Equation:

$$
\dot { f } _ { q _ { i } } = ( E _ { i } ^ { - 1 } - 1 ) \left( \sum _ { j } A _ { i j } q _ { j } \right) f _ { q _ { i } } + ( E _ { i } ^ { + 1 } - 1 ) \left( \sum _ { j } { \cal T } _ { i j } q _ { j } \right) f _ { q _ { i } } ,
$$

where $E$ isthe step operator defined as $E _ { i } ^ { k } f ( . . . , q _ { i } , . . . ) =$ $f ( . . . , q _ { i } { + } k , . . . )$ .This equation can be solved using generating functionmethod.Firstwedenotegeneratingfunction $\begin{array} { r } { F ( z _ { j } , t ) = \sum _ { q _ { \nu } = 1 , \dots \infty } ( \prod _ { \nu = 1 , \dots n } z _ { \nu } ^ { q _ { \nu } } ) f _ { q _ { \nu } } } \end{array}$ . In our system, $\boldsymbol { { \cal T } }$ is diagonal: $\begin{array} { r } { { \cal { T } } _ { i j } = \delta _ { i j } { \cal { T } } _ { i } } \end{array}$ ,and then $\dot { F }$ obeys

$$
\dot { F } = \underset { i } { \sum } ( 1 - z _ { i } ) \Bigg ( T _ { i } F _ { i } - \underset { j } { \sum } A _ { i j } z _ { j } F _ { j } \Bigg ) ,
$$

where $F _ { j } = \partial _ { z _ { j } } F$ .In the steady state, ${ \dot { F } } = 0$

The mean and variance of species will be given by following properties of generating function: $F | \sb 1 = 1 ; F _ { j } | \sb 1 = \Big \langle q _ { j } \Big \rangle ; \sp { \circ } F _ { i i } = \langle q _ { i } ^ { 2 } \rangle -$ $\left. q _ { i } \right.$ ; and if $i \ne j , F _ { i j } | _ { 1 } = \biggl < q _ { i } q _ { j } \biggr >$ ，where $F _ { i j } = \partial _ { z _ { i } } \ \partial _ { z _ { j } } F$ and $\mid _ { 1 }$ denotes evaluation at $z _ { j } = 1$ forall $j$ Successive differentiations of Eq.(3) will generate linear equations of higher order moments.First we define the vector $J _ { i } = F _ { i }$ ,and the matrix $K _ { i j } = F _ { i j }$ ,where the indexes of $K$ mean row and column and the indexes of $F$ mean differentiation.Differentiating Eq.(3） up to the second moment,we obtain the following equations for the steady state:

$$
( A - { \Gamma } ) J = 0 , \quad [ ( A - { \Gamma } ) K + L ] = - [ ( A - { \Gamma } ) K + L ] ^ { T } ,
$$

where $L _ { i j } = A _ { i j } J _ { j }$ (not summation）(Thattai and van Oudenaarden, 2001).

For our bicistronic operon model, $J = ( \langle D \rangle , \langle R \rangle , \langle R G \rangle , \langle R F P \rangle , \langle G F P \rangle )$ By solving Eq. (4)，we got the mean $( J ,$ ）andvariance $( K )$ of gene expression,and the correlation of different genes in the steady state.

2.2.Results of the bicistronic operon with the constitutive promoter

# 2.2.1． Statistics of mRNAs

Both $R$ and RG obey the Poisson distribution,which means their Fano factors are equal to 1.They are also independent with each other.The average numbers of $R$ and $R G$ are

$$
\langle R \rangle = \frac { K _ { R } } { \gamma _ { R } } = \frac { e K } { \gamma _ { R } } ,
$$

$$
\langle R G \rangle = \frac { K _ { R G } } { \gamma _ { R G } } = \frac { ( 1 - e ) K } { \gamma _ { R G } } .
$$

Coefficient of variance of mRNAsare

$$
\eta _ { R } = \frac { \sqrt { \delta R ^ { 2 } } } { \langle R \rangle } = \sqrt { \frac { \gamma _ { R } } { e K } } = \frac { 1 } { \sqrt { \langle R \rangle } } ,
$$

$$
\eta _ { R G } = \frac { \sqrt { \delta R G } ^ { 2 } } { \langle R G \rangle } = \sqrt { \frac { \gamma _ { R G } } { ( 1 - e ) K } } = \frac { 1 } { \sqrt { \langle R G \rangle } } .
$$

From these two equations,we can see that lower level of mRNA expression leads to larger fluctuation.

# 2.2.2．Statistics of proteins

During the short lifetime of the mRNA,proteins are synthesized by ribosomes with the mRNA,so the profile of translation of protein is bursty as shown in Fig.2B.This is one of the sources of the intrinsic noise.The number of protein produced froma single mRNA obeys the geometric distribution (Berg,1978).We use $b$ to denote the burstiness of the translation process.It is the average number of protein translated by ribosomes during the lifetime of one mRNA,for example, $b _ { P R - R } = K _ { P R } / \gamma _ { R }$ is the average number of

![](images/468b7da3be0cc6e95deef9abc34cc73bf031aff0c59ae5adb5b1132e332fc6f4.jpg)  
g correlation. In the simulations $\gamma _ { P R } = \gamma _ { P G } = 0 . 0 0 0 2 9 \ s ^ { - 1 }$ $\gamma _ { R } = \gamma _ { R G } = 0 . 0 0 3 3 \ s ^ { - 1 } , K = 0 . 0 0 0 5 \ s ^ { - 1 } , e = 0 $ ,other parameters in (A) $K _ { \mathrm { P R } } = K _ { \mathrm { P G } } = 0 . 0 0 3 3 \ s ^ { - 1 }$ ,the average translational burst size of RFP and GFP are $b _ { P R } = b _ { P G } = 1$ ： (B) $K _ { \mathrm { P R } } = K _ { \mathrm { P G } } = 0 . 0 6 6 s ^ { - 1 }$ $b _ { \mathrm { P R } } = b _ { \mathrm { P G } } = 2 0$

RFP protein translated in the lifetime of one RG mRNA. Similarly, we denote $b _ { P R - R G } = K _ { P R } / \gamma _ { R G }$ and $b _ { P G } = K _ { P G } / \gamma _ { R G }$ . In the cell,protein lives much longer than mRNA, i.e., $\gamma _ { P R } , \gamma _ { P G } \ll \gamma _ { R } , \gamma _ { R G }$ ，so we made approximations under this assumption below. Average numbers of proteinsare

$$
\begin{array} { c } { { \displaystyle \langle R F P \rangle = \frac { K _ { P R } } { \gamma _ { P R } } ( \langle R \rangle + \langle R G \rangle ) = \frac { K _ { P R } } { \gamma _ { P R } } ( \frac { K _ { R } } { \gamma _ { R } } + \frac { K _ { R G } } { \gamma _ { R G } } ) } } \\ { { = \displaystyle \frac { K } { \gamma _ { P R } } [ e b _ { P R - R } + ( 1 - e ) b _ { P R - R G } ] , } } \end{array}
$$

$$
\langle G F P \rangle = \frac { K _ { P G } } { \gamma _ { P G } } \langle R G \rangle = \frac { K _ { P G } } { \gamma _ { P G } } \frac { K _ { R G } } { \gamma _ { R G } } = \frac { ( 1 - e ) K } { \gamma _ { P G } } b _ { P G } .
$$

The ratio between them is

$$
\frac { \langle R F P \rangle } { \langle G F P \rangle } { = } \frac { K _ { P R } / K _ { P G } } { \gamma _ { P R } / \gamma _ { P G } } \biggl [ \frac { e / ( 1 - e ) } { \gamma _ { R } / \gamma _ { R G } } + 1 \biggr ] .
$$

We can see different strategies tuning protein expression ratio in one operon: changing termination efficiency e,changing the translation rate ratio $K _ { P R } / K _ { P G }$ ，changing the protein or mRNA stability ratio,i.e., $\gamma _ { P R } / \gamma _ { P G }$ ，or $\gamma _ { R } / \gamma _ { R G }$ . Although tuning protein ratio at protein degradation rates cannot be ruled out,it seems that the prokaryotic cell avoids to degrade protein to avoid wasting (Gur et al.,2O11).For functional related proteins in the same operon,especially for those without transcriptional regulatory function,mRNAs tend to have the similar lifetimes (Bernstein et al., 2002;Kristoffersen et al., 2012;Quax et al., 2013). It seems that adjusting translation rates or termination efficiency is widely used mechanism in the prokaryotic cell to tune the gene expression ratio (Quax et al., 2013; Cho et al., 2009; Güell et al., 2009).

The Fano factor of GFP is

$$
\frac { \delta G F P ^ { 2 } } { \langle G F P \rangle } = \frac { K _ { P G } } { \gamma _ { P G } + \gamma _ { R G } } + 1 \approx \frac { K _ { P G } } { \gamma _ { R G } } + 1 = b _ { P G } + 1 ,
$$

whichis the sameasin Thattaiand van Oudenaarden (2oO1).The distribution for the molecule numbers of protein is broader than the Possion distribution.

Coefficient of Variance of GFP protein is

$$
\eta _ { G F P } = \sqrt { \frac { 1 } { \langle G F P \rangle } + \frac { 1 } { 1 + \displaystyle { \frac { \gamma _ { R G } } { \gamma _ { P G } } } } \frac { 1 } { \langle R G \rangle } }
$$

$$
\begin{array} { l } { \approx \sqrt { \frac { 1 } { \langle G F P \rangle } + \frac { \gamma _ { P G } } { ( 1 - e ) K } } } \\ { = \sqrt { \frac { \gamma _ { P G } } { ( 1 - e ) K } \biggl ( \frac { 1 } { b _ { P G } } + 1 \biggr ) } . } \end{array}
$$

If we fix other parameters,the intrinsic noise of GFP is decreasing as the burst size $b _ { P G }$ increasing.When $b _ { P G }$ is small,burst of translation is a critical source of intrinsic noise,when $b _ { P G }$ isbig, the intrinsic noise is mainly determined by the transcription process, i.e., by $K$ and e,considering $\gamma _ { P G }$ is primarily determined by growth dilution. Increasing promoter strength $( K )$ or decreasing premature termination (e) would repress mRNA expression noise as shown in Eq.(8),and then lower noise would be passed to the protein level. Our result agrees with Swain et al. (2002).

When $e \neq 0$ and $e \neq 1$ ,the Fano factor of protein RFP is

$$
\begin{array} { c } { { \displaystyle \frac { \delta R F P ^ { 2 } } { \langle R F P \rangle } = \displaystyle \frac { K _ { P R } } { ( \gamma _ { R G } + \gamma _ { P R } ) } \bigg [ \frac { \langle R G \rangle } { \langle R G \rangle + \langle R \rangle } \bigg ] + \displaystyle \frac { K _ { P R } } { ( \gamma _ { R } + \gamma _ { P R } ) } \bigg [ \frac { \langle R \rangle } { \langle R G \rangle + \langle R \rangle } \bigg ] + 1 } } \\ { { \approx b _ { P R - R G } \left( \displaystyle \frac { 1 } { 1 + \displaystyle \frac { e } { 1 - e } \frac { \gamma _ { R G } } { \gamma _ { R } } } \right) + b _ { P R - R } \left( \displaystyle \frac { 1 } { 1 + \displaystyle \frac { 1 - e } { e } \frac { \gamma _ { R } } { \gamma _ { R G } } } \right) + 1 . } } \end{array}
$$

Here we can see that the noise of RFP is derived from the Poisson processes of the translations from the two kinds of mRNAs.The ratio depends on their ratio in the total mRNA.When $e \to 1$ ,then

$$
\frac { \delta R F P ^ { 2 } } { < R F P > } \to \frac { K _ { P R } } { ( \gamma _ { R } + \gamma _ { P R } ) } + 1 ,
$$

and when $e {  } 0$ ，then

$$
\frac { \delta R F P ^ { 2 } } { < R F P > } \to \frac { K _ { P R } } { ( \gamma _ { R G } + \gamma _ { P R } ) } + 1 .
$$

Under these two conditions,RFP protein is produced from only $R$ or RG,so RFP has the similar distribution as GFP (Eq.(12)).

When $\gamma _ { R G } = \gamma _ { R }$ $b _ { P R - R G } = b _ { P R - R } = b _ { P R }$ 、And then the Fano factor of RFP can be simplified into

$$
\frac { \delta R F P ^ { 2 } } { \langle R F P \rangle } = ( 1 - e ) b _ { P R - R G } + e b _ { P R - R } + 1 = b _ { P R } + 1 ,
$$

the Fano factor only depends on the translational burst size of RFP, which is in agreement with the well-known result for single gene expression (Thattai and van Oudenaarden, 2001).

Coefficient of variance ofRFP protein is

$$
\eta _ { R F P } = \sqrt { \frac { 1 } { \langle R F P \rangle } + \left[ \frac { 1 } { \left( 1 + \frac { \gamma _ { R G } } { \gamma _ { P R } } \right) } \left( \frac { 1 } { 1 + \frac { e } { 1 - e } \frac { \gamma _ { R G } } { \gamma _ { R } } } \right) + \frac { 1 } { \left( 1 + \frac { \gamma _ { R } } { \gamma _ { P R } } \right) } \left( \frac { 1 } { 1 + \frac { 1 - e } { e } \frac { \gamma _ { R } } { \gamma _ { R G } } } \right) \right] \frac { 1 } { \langle R G \rangle + \langle R \rangle } } .
$$

f $\gamma _ { R } = \gamma _ { R G }$ ,then

$$
\begin{array} { c } { { \eta _ { R F P } = \sqrt { \displaystyle \frac { 1 } { \langle R F P \rangle } } + \frac { 1 } { \left( 1 + \frac { \gamma _ { R G } } { \gamma _ { P R } } \right) } \frac { 1 } { \langle R G \rangle + \langle R \rangle } } } \\ { { \approx \sqrt { \displaystyle \frac { 1 } { \langle R F P \rangle } + \frac { \gamma _ { P R } } { K } } } } \\ { { = \sqrt { \displaystyle \frac { 1 } { \langle R F \rangle } } \frac { 1 } { \left( \frac { 1 } { b _ { R } } + 1 \right) } , } } \end{array}
$$

where $b _ { P R } = b _ { P R - R } = b _ { P R - R G }$ ，RFP can be translated equally from both $R$ and RG,and these two kinds mRNAs have the same degradation rates as assumed.So termination effciency(e) would not influence the noise of RFP.From Eqs.(13）and(17),clearly noise of RFP comes from:(1） noise inherited from the transcription process which is measured by transcription rate $1 / K ;$ ：(2）noise from burstiness of translation measured by burst size $b _ { P R }$ When transcription rate $K$ or burst size $b _ { P R }$ is small, the fluctuation of RFP expression would be significant.

# 2.2.3．The correlation between RFP and GFP mRNAs

In order to see how much correlation at the mRNA level would be passed to the protein level,we first analyze the correlation between numbers of mRNAs that contains RFP or GFP.

$$
\begin{array} { r l } & { \rho _ { m E - m G } = \frac { \langle ( R G + R ) - \langle R G + R \rangle \langle R G - \langle R G \rangle \rangle } { \sqrt { \delta ( R G + R ) ^ { 2 } } \sqrt { \delta R G ^ { 2 } } } } \\ & { \qquad = \frac { 1 } { \sqrt { 1 + \frac { \delta R ^ { 2 } } { \delta R G ^ { 2 } } } } } \\ & { \qquad = \sqrt { \frac { \langle R G \rangle } { \langle R G \rangle + \langle R \rangle } } } \\ & { \qquad = 1 / \sqrt { 1 + \frac { e ^ { - \gamma _ { R G } } } { 1 - e ^ { - \gamma _ { R G } } } } . } \end{array}
$$

which is square root of the ratio of RG mRNA in the total mRNA. This equation shows that the correlation between mRNAs that contains RFP and GFP is from co-transcription of RFP and GFP. Longer lifetime of RG relative to $R$ will lead to stronger correlation.

$$
\rho _ { m R - m G } = \sqrt { 1 - e } ,
$$

the correlation between RFP and GFP at the mRNA level is only dependent on the termination efficiency $e$ of the terminator.

# 2.2.4.The correlation between mRNA and protein

We then calculate the correlation between mRNA and protein expressions.The Pearson correlation coefficient between RG and GFP is

$$
\rho _ { m G - G F P } = \sqrt { \frac { 1 } { \left( 1 + \frac { 1 } { K _ { P G } / \gamma _ { R G } } + \frac { 1 } { K _ { P G } / \gamma _ { P G } } \right) \left( 1 + \frac { \gamma _ { R G } } { \gamma _ { P G } } \right) } } ,
$$

where $m G$ is RG,which is the only mRNA coding GFP protein. Proteins live much longer than mRNAs,which means

$$
\frac { 1 } { K _ { P G } / \gamma _ { R G } } \gg \frac { 1 } { K _ { P G } / \gamma _ { P R } } \quad \mathrm { a n d } \quad \frac { \gamma _ { P G } } { \gamma _ { R G } } \approx 0 ,
$$

then

$$
\rho _ { R G - G F P } \approx \sqrt { \frac { \gamma _ { P G } / \gamma _ { R G } } { 1 + \frac { 1 } { K _ { P G } / \gamma _ { R G } } } } \approx 0 .
$$

When $\gamma _ { R G } = \gamma _ { R }$ and $\gamma _ { P R } = \gamma _ { P G }$ ，we got the correlation between mRNAs and RFP protein:

$$
\rho _ { m R - R F P } = \sqrt { \frac { 1 } { \left( 1 + \frac { 1 } { K _ { P R } / \gamma _ { R } } + \frac { 1 } { K _ { P R } / \gamma _ { P R } } \right) \left( 1 + \frac { \gamma _ { R } } { \gamma _ { P R } } \right) } } \approx \sqrt { \frac { \gamma _ { P R } / \gamma _ { R } } { 1 + \frac { 1 } { K _ { P R } / \gamma _ { R } } } } \approx 0 ,
$$

where $m R$ indicates the total number of transcripts containing RFP coding sequence,which include full-length transcripts RG and short ones R.From Eqs.(21) and (22),we see that there isalmost no correlation between mRNA and protein due to $\gamma _ { p r o t e i n } \ll \gamma _ { m R N A }$ Actually,experiments show that protein levels do not or just weakly correlate with mRNA levels (Taniguchi et al., 2O1O; Golding et al.，2oo5).Due to the much longer lifetime of protein,the fluctuation at the mRNA level is smoothed out at the protein level, which leads to the weak correlation between mRNA and protein.

# 2.2.5.The correlation between RFP and GFP proteins

Next we calculate gene expression correlation between two proteins,which has the biology significance for large protein complex formation,and for reaction systems sensitive to enzyme correlation (Ray and Igoshin,2O12). The Pearson correlation coefficient of the numbers of RFP and GFP protein is

$$
\rho _ { R F P - G F P } = \frac { \langle R F P \cdot G F P \rangle - \langle R F P \rangle \langle G F P \rangle } { \sqrt { \delta R F P ^ { 2 } } \sqrt { \delta G F P ^ { 2 } } } .
$$

The general analytic formula isa little complex,and we do not show it here.In order to get intuitive understanding of the dependence of $\rho _ { R F P - G F P }$ on different parameters,we make simplifications below.

f $\gamma _ { R G } = \gamma _ { R }$ $\gamma _ { P R } = \gamma _ { P G }$ ,then the correlation coeficient of RFP and GFP can be simplified into

$$
\begin{array} { c } { \rho _ { R F P - G P } = \displaystyle \frac { \sqrt { 1 - e } } { \sqrt { \left( 1 + \displaystyle \frac { 1 } { K _ { P R } / \gamma _ { R G } } + \displaystyle \frac { 1 } { K _ { P R } / \gamma _ { P R } } \right) \left( 1 + \displaystyle \frac { 1 } { K _ { P G } / \gamma _ { R G } } + \displaystyle \frac { 1 } { K _ { P G } / \gamma _ { P G } } \right) } } } \\ { \displaystyle \approx \frac { \sqrt { 1 - e } } { \sqrt { \left( 1 + \displaystyle \frac { 1 } { K _ { P R } / \gamma _ { R G } } \right) \left( 1 + \displaystyle \frac { 1 } { K _ { P G } / \gamma _ { R G } } \right) } } } \\ { \displaystyle = \frac { \sqrt { 1 - e } } { \sqrt { \left( 1 + \displaystyle 1 / b _ { P R } \right) \left( 1 + 1 / b _ { P G } \right) } } , } \end{array}
$$

where $b _ { P R } = b _ { P R - R } = b _ { P R - R G } .$ ，for $\gamma _ { R G } = \gamma _ { R }$ Changingpromoter strength $( K )$ would not influence the correlation,although it can influence noise of mRNA and protein.When $e { = } 0$ ,our result is the same as Ray and Igoshin (2012). In Eq. (24), the numerator $\sqrt { 1 - e }$ represents protein correlation inherited from the mRNA level (see Eq.(19))and the denominator shows the influence from the bursty translation process. If $b _ { R F P }$ or $b _ { G F P }$ is small, then the number of RFP or GFP produced in the lifetime of one RG has large fluctuation (Eq.(17)).But translation events of RFP and GFP are independent and their fluctuations are unrelated,which means correlation between RFP and GFP would be low.This has been shown by the stochastic simulations in Fig.2A (simulation method see Appendix B). However,when both of $b _ { R F P }$ and $b _ { R F P }$ are much larger than 1, fluctuations of RFP or GFP are both small (Eqs.(13) and (17)). So bursty translations have little effect on the correlation of two proteins,which has been shown by the simulation results in Fig.2B.From Eq.(24) we can see that when both $b _ { P R }$ and $b _ { P G }$ are much bigger than 1 (Fig. 3A), $\rho _ { R F P - G F P } \approx \sqrt { 1 - e }$ ，which means the correlation is mainly determined by the polar effect at the transcriptional level.

![](images/6e3796c65ba1f3b20717f86cf651481efa35c7b89c23bdb60f59bb085f9f6d9a.jpg)  
Fig.3.Dependence of the correlation between RFP and GFP on terminator efficiency e,translation burst size $b$ ,translation rates of proteins and the degradation rates of mRNAsinbicistrocoithtstitieprooterFalltaaebadfothalyall,saceeouf $\rho _ { R F P - G F P }$ (G) Cycles are got from stochastic simulationsand linesare got fromanalytical results.Inallfigures $\gamma _ { P R } = \gamma _ { P G } = 0 . 0 0 0 2 9 \ s ^ { - 1 } ,$ other parameters in each subplot are specified as follows: in （A) $e = 0 . 3 , \gamma _ { R } = \gamma _ { R G } = 0 . 0 0 3 3 s ^ { - 1 }$ ；(B) $\gamma _ { R } = \gamma _ { R G } = 0 . 0 0 3 3 \ s ^ { - 1 } , K _ { P R } = 0 . 1 6 s ^ { - 1 }$ ;(C） $e = 0 . 3 , \gamma _ { R } = 0 . 0 0 3 3 s ^ { - 1 } , K _ { P G } = 0 . 1 6 s ^ { - 1 }$ ；(D） $e = 0 . 3 , \gamma _ { R } = 0 . 0 0 3 3 \ s ^ { - 1 } , K _ { P R } = 0 . 1 6 s ^ { - 1 }$ ：， (E) $e = 0 . 3 , \gamma _ { R G } = 0 . 0 0 3 3 \ s ^ { - 1 } , K _ { P G } = 0 . 1 6 \ s ^ { - 1 }$ ； (F) $e = 0 . 3 , \gamma _ { R G } = 0 . 0 0 3 3 \ s ^ { - 1 } , K _ { P R } = 0 . 1 6 \ s ^ { - 1 }$ ； (G) $K = 0 . 3 ~ { s ^ { - 1 } } , K _ { P R } = 0 . 1 6 ~ s ^ { - 1 } , \gamma _ { R G } = \gamma _ { R } = 0 . 0 0 3 3 ~ { s ^ { - 1 } }$ .

We plot the relationship between $\rho _ { R F P - G F P }$ and other parameters in Fig. 3 using the formula of $\rho _ { R F P - G F P }$ (Eq. (23)) without any simplification except supposing $\gamma _ { P R } = \gamma _ { P G }$ . In Fig. 3G,we can see stochastic simulations agree with our analytical results very well. In Fig.3B and G we can see that $\rho _ { R F P - G F P }$ decreases as $e$ increases,i.e.,transcription terminationat the internal terminator directly lowers the protein correlation.This result can explain why Monte Carlo simulation of Liang et al.(2013) only showed a small effect of intergenic terminator on the correlation.They take $e { = } 0 . 5$ $\rho _ { R F P - G F P } \approx \sqrt { 1 - e } \approx 0 . 7$ and the correlation is lowered just about $30 \%$ Taking bigger e,for example, $e { = } 0 . 9$ $\rho _ { R F P - G F P } \approx \sqrt { 1 - e } \approx 0 . 3 2$ then the polar effect will lower the correlation about $70 \%$ ,and the influence of polar effect would be obvious.In prokaryotic cells, mRNAs live about several minutes on average (Selinger et al, 2003; Bernstein et al.,2002; Kristoffersen et al., 2012). In the range of mRNA degradation rate(half-life of mRNA $0 . 5 { - } 1 5 \operatorname* { m i n }$ ),adjusting the translation rate almost does not alter the protein correlation except translation rate isvery small (Fig.3B-G).This means adjusting protein expressions at the translation level will be the optimal strategy to tune the gene expression ratio in the same operon.If we take the half-life of mRNA 5 min,we can tune the translation rate between O.O1 and $1 \ : s ^ { - 1 }$ without obviously changing the correlation of the proteins (Fig.3G). Actually, comparative genomic study of Quax et al.(2o13) shows that different translation rate is a key determinant of the gene expression ratio in an operon.Only those RFPs translated from RG contribute to the correlation with GFP.Decreasing the stability of mRNA R (increas$\operatorname { i n g } \gamma _ { R } .$ ）or increasing the stability of mRNA RG (decreasing $\gamma _ { R G }$ will increase the ratio of RFP correlated with GFP protein,which leads to a higher correlation (Fig.3C-F).At the same time, increasing the stability of mRNA RG(decreasing $\gamma _ { R G }$ ）will increase the burst size of correlated RFP and GFP translation from RG,which also leads to a higher correlation (Fig. 3C and D).

# 3.The bicistronic operon with the two-state promoter

Some single-cell experiments showthat mRNAsynthesisisalso bursty for some promoters which can be described by the twostate model (Golding et al., 2005；So et al.， 2011; Chong et al. 2014).As shown in Fig.1A, these promoters stochastically transit between ‘on'and‘off states.The mRNA can be synthesized with the transcription rate $k _ { T X }$ onlywhen the promoter is in the on state.The transition rate from the off state to the on state is $k _ { o n } .$ which determines the average duration time of off state $( 1 / k _ { o n } )$ = The transition rate from the on state to the off state is $k _ { o f f }$ which means the average duration of transcription pulse is $1 / k _ { o f f }$ . The average transcription burst size,i.e.,the average number of mRNA synthesized in one period of on state is $k _ { T X } / k _ { o f f }$ .We study the gene expression noise in the bicistronic operon driven by the two-state promoter (Fig.1).By solving the Master Equation,we get analytical results for the noisesand the correlationat the mRNA level and the protein level.These analytical results are confirmed by stochastic simulation (procedure in Appendix B).

# 3.1.The model of the bicistronic operon with the two-state promoter

As in the system with the constitutive promoter,we use $f _ { q _ { i } } ( i = 1 . . . n )$ to describe the system.Here the state of the promoter is indicated by $q _ { 1 }$ ， $q _ { 1 } = 1$ for the on state and $q _ { 1 } = 0$ for the off

state.The molecular numbers of other species are indicated by $q _ { i }$ $( i = 2 . . . n )$ ,and $q _ { i } = 0 , 1 \ldots \infty$ .Werewrite $f _ { q _ { i } }$ as $f _ { q _ { 1 } , q _ { i } }$ （ $( i = 2 . . . n )$ ,the dynamic evolution of $f _ { q _ { 1 } , q _ { i } }$ is described in the scheme:

$$
\begin{array} { r l } & { f _ { 0 , q _ { i } } \overset { k , \_ e q _ { f } } { k _ { \omega } } f _ { 1 , q _ { i } } } \\ & { } \\ & { f _ { q _ { 1 } , q _ { i } } \overset { k ^ { + } ( q _ { j } ) } { \underset { g ^ { + } } { k _ { i } ^ { + } } } f _ { q _ { 1 } , q _ { i } + 1 } } \\ & { } \\ & { f _ { q _ { 1 } , q _ { i } } \overset { k ^ { - } ( q _ { j } ) } { \underset { g ^ { + } } { k _ { i } ^ { + } } } f _ { q _ { 1 } , q _ { i } - 1 } } \\ & { k _ { i } ^ { + } ( q _ { j } ) = \sum _ { j } A _ { i j } q _ { j } , \quad k _ { i } ^ { - } ( q _ { j } ) = \sum _ { j } ^ { T } r _ { i j } q _ { j } , } \end{array}
$$

$$
( i = 2 . . . n , \ j = 1 . . . n ) ,
$$

where $k _ { i } ^ { + } ( q _ { j } )$ and $k _ { i } ^ { - } ( q _ { j } )$ denote the birth and death rates of $i .$ -th molecule,matrices $A$ and $\boldsymbol { \varGamma }$ provide the coefficients of their linear dependence on the molecular numbers.In our systems, $q _ { i } =$ $\{ D , R , R G , R F P , G F P \}$ ，where $D$ is the number of active promoter, i.e., the number of the operon that can be transcribed.Matrices A and $\boldsymbol { { \cal T } }$ are same as those we used for the operon with the constitutive promoter (Eq.(1)).

# 3.1.1.Method to get themeansand variances

The above scheme for the two-state promoter can be described by the following Master Equation:

$$
\begin{array} { r l } & { \dot { f } _ { q _ { 1 } , q _ { i } } = ( E _ { i } ^ { - 1 } - 1 ) \Bigg ( \sum _ { j } A _ { i j } q _ { j } \Bigg ) f _ { q _ { 1 } , q _ { i } } + ( E _ { i } ^ { + 1 } - 1 ) \Bigg ( \sum _ { j } \Gamma _ { i j } q _ { j } \Bigg ) f _ { q _ { 1 } , q _ { i } } } \\ & { \quad \quad \quad + ( - 1 ) ^ { q _ { 1 } } ( k _ { o f f } f _ { 1 , q _ { i } } - k _ { o n } f _ { 0 , q _ { i } } ) . } \end{array}
$$

For the promoter in the on or the off state we denote the generating functions:

$$
F _ { o n } ( z _ { j } , t ) = \sum _ { q _ { \nu } = 0 , . . . \infty } \left( \prod _ { \nu = 2 , . . . n } z _ { \nu } ^ { q _ { \nu } } \right) f _ { 1 , q _ { \nu } } ,
$$

$$
F _ { o f f } ( z _ { j } , t ) = \sum _ { q _ { \nu } = 0 , . . . \infty } \left( \prod _ { \nu = 2 , . . . n } z _ { \nu } ^ { q _ { \nu } } \right) f _ { 0 , q _ { \nu } } ,
$$

andforthewholesystem thegenerating functionis $F ( z _ { j } , t ) = z _ { 1 } F _ { o n } ( z _ { j } , t ) + F _ { o f f } ( z _ { j } , t )$ ，Inoursystem, $\boldsymbol { { \cal T } }$ isdiagonal: $\begin{array} { r } { { \cal { T } } _ { i j } = \delta _ { i j } { \cal { T } } _ { i } } \end{array}$ ，then $\dot { F }$ obeys

$$
\begin{array} { l } { \displaystyle { \dot { F } = \sum _ { i = 2 \dots n } ( 1 - z _ { i } ) \Bigg ( r _ { i } F _ { i } - \sum _ { j = 1 \dots n } A _ { i j } z _ { j } F _ { j } \Bigg ) + z _ { 1 } ( k _ { o n } F _ { o f f } - k _ { o f f } F _ { o n } ) } } \\ { \displaystyle { \quad \quad + ( k _ { o f f } F _ { o n } - k _ { o n } F _ { o f f } ) , } } \end{array}
$$

where $F _ { j } = \partial _ { z _ { j } } F$ .In the steady state, ${ \dot { F } } = 0$

The mean and variance of species will be given by following properties of generating function: $F _ { j } | _ { 1 } = \big < q _ { j } \big > ; F _ { i i } = \big < q _ { i } ^ { 2 } \big > ^ { \circ } - \big < q _ { i } \big >$ ; and if $\boldsymbol { i } \neq \boldsymbol { j } , F _ { i j } | _ { 1 } = F _ { j i } | _ { 1 } = \left. \boldsymbol { q } _ { i } \boldsymbol { q } _ { j } \right.$ ，where $F _ { i j } \stackrel { \cdot } { = } \partial _ { z _ { i } } ^ { ' } \partial _ { z _ { j } } F$ and $\mid _ { 1 }$ denotes evaluation at $z _ { j } = 1$ for all $j$ .Specially, $F _ { 1 1 } | _ { 1 } = 0$ ; and if $i \neq 1$ ,then $F _ { o n i } | _ { 1 } + F _ { o f f i } | _ { 1 } = \langle q _ { i } \rangle , \ F _ { o n i } | _ { 1 } = F _ { 1 i } | _ { 1 }$ ． Successive differentiations of Eq.(28) will generate linear equations of higher order moments.

We denote $\begin{array} { r } { f _ { o n } = F _ { o n } | _ { 1 } = \sum q _ { \nu } = 0 , . . . \infty } f _ { 1 , q _ { \nu } }  \end{array}$ which is the possibility that promoter stays in the on state,and similarly $f _ { o f f } = F _ { o f f } | _ { 1 }$ $\textstyle = \sum q _ { \nu } = 0 , \dots \infty  f _ { 0 , q _ { \nu } }$ is the possibility of the off state.From the normalization of the possibility,we know that:

$$
f _ { o n } + f _ { o f f } = 1 .
$$

First we define the vector $J _ { i } = F _ { i }$ ,and the matrix $K _ { i j } = F _ { i j }$ ,where the indexes of $K$ mean row and column and the indexes of $F$ mean differentiation.Differentiating Eq.(28)up to the second moment, we obtain the following equations for the steady state:

$$
k _ { o n } f _ { o f f } - k _ { o f f } f _ { o n } = 0 ,
$$

$$
{ \cal T } _ { i } K _ { i 1 } - \sum _ { j = 1 \ldots n } A _ { i j } K _ { j 1 } - A _ { i 1 } J _ { 1 } + k _ { o f f } K _ { 1 i } - k _ { o n } ( J _ { i } - K _ { 1 i } ) = 0 \ ( i = 2 \ldots n ) ,
$$

$$
( A - { \cal T } ) J = 0 , \quad [ ( A - { \cal T } ) K + L ] _ { i j } = - [ ( A - { \cal T } ) K + L ] _ { j i } \ ( i , j = 2 . . . n ) ,
$$

where $\begin{array} { r } { L _ { i j } = A _ { i j } J _ { j } } \end{array}$ (not summation).

# 3.2.Results of the bicistronic operon with the two-state promoter

By solving Eqs.(29)-(32) we get the noise and the correlation between molecules for the bicistronic operon with the two-state promoter.The results are shown below.

# 3.2.1．Statistics of mRNAs

The average number of mRNAs are

$$
\langle R \rangle = \frac { e f _ { o n } k _ { T X } } { \gamma _ { R } } ,
$$

$$
\langle R G \rangle = \frac { ( 1 - e ) f _ { o n } k _ { T X } } { \gamma _ { R G } } ,
$$

where $f _ { o n } = k _ { o n } / ( k _ { o n } + k _ { o f f } )$ is the fraction of time or the possibility that the promoter is in the on state.If we denote $K = f _ { o n } k _ { T X }$ as the effective transcription rate of the two-state promoter, then the average number of R and RG take the same formula as Eqs.(5)and (6) for the constitutive promoter.

The Fano factors of mRNAs are

$$
\frac { \delta R ^ { 2 } } { \langle R \rangle } = 1 + e A _ { R } ,
$$

$$
\frac { \delta R G ^ { 2 } } { \langle R G \rangle } = 1 + ( 1 - e ) A _ { R G } ,
$$

where

$$
A _ { R } = \frac { k _ { o f f } } { k _ { o n } + k _ { o f f } } \frac { k _ { T X } } { ( \gamma _ { R } + k _ { o n } + k _ { o f f } ) } \quad \mathrm { a n d } \quad A _ { R G } = \frac { k _ { o f f } } { k _ { o n } + k _ { o f f } } \frac { k _ { T X } } { ( \gamma _ { R G } + k _ { o n } + k _ { o f f } ) } ,
$$

which characterize the influence of the two-state promoter. Our results of the Fano factors for the mRNAs are the same as previous results (Peccoud and Ycart,1995).The Fano factors of R and RG are bigger than 1,which means the distribution of R and RG is not Poisson. Experimental measurements of mRNA show that the Fano factors of some mRNAs are greater than 1 (Golding et al., 2005). This implies that the two-state promoter model may be a more realistic description of these promoters (Golding et al., 2005；So et al., 2011; Chong et al., 2014).

Coefficients of Variance of mRNAsare

$$
\eta _ { R } = \frac { \sqrt { \delta R ^ { 2 } } } { \langle R \rangle } = \sqrt { \frac { 1 } { \langle R \rangle } ( 1 + e A _ { R } ) } ,
$$

$$
\eta _ { R G } = \frac { \sqrt { \delta R G ^ { 2 } } } { \langle R G \rangle } = \sqrt { \frac { 1 } { \langle R G \rangle } [ 1 + ( 1 - e ) A _ { R G } ] } .
$$

The noise of mRNA depends on the mean expression level: the lower the expression level, the higher the noise.This behavior is similar to the mRNA transcribed from the constitutive promoter (Eqs.(7) and (8)).However if we keep the same average expression level of mRNA,the operon with the two-state promoter has higher noise of mRNA compared with the constitutive promoter. If we adjust the parameters of the two-state promoter and let $A _ { R } , A _ { R G }  0$ ,then the Fano factors and coefficients of variance of the mRNAs will be the same as those for the operon with the constitutive promoter (Eqs. (5)-(8)).

# 3.2.2.Statistics of proteins

The average expression levels of proteins are

$$
\langle R F P \rangle = \frac { K _ { P R } } { \gamma _ { P R } } ( \langle R \rangle + \langle R G \rangle ) = \frac { f _ { o n } k _ { T X } } { \gamma _ { P R } } [ e b _ { P R - R } + ( 1 - e ) b _ { P R - R G } ] ,
$$

$$
\langle G F P \rangle = \frac { K _ { P G } } { \gamma _ { P G } } \langle R G \rangle = \frac { ( 1 - e ) f _ { o n } k _ { T X } } { \gamma _ { P G } } b _ { P G } ,
$$

where $b _ { P R - R G } = k _ { P R } / \gamma _ { R G }$ ， $b _ { P R - R } = k _ { P R } / \gamma _ { R }$ and $b _ { P G - R G } = k _ { P G } / \gamma _ { R G }$ are the translational burst sizes of RFP and GFP.If we use the effective transcription rate $K = f _ { o n } k _ { T X }$ in Eqs.(39） and (40), the average expressions of the RFP and GFP for the two-state promoters take the same formula as those for the constitutive promoter (Eqs. (9) and (10)).

When $\gamma _ { R G } = \gamma _ { R }$ ，then $b _ { P R - R G } = b _ { P R - R } = b _ { P R }$ and the Fano factors of GFP and RFP are

$$
\frac { \delta G F P ^ { 2 } } { \langle G F P \rangle } = \frac { K _ { P G } } { \gamma _ { P G } + \gamma _ { R G } } [ 1 + ( 1 - e ) B _ { G } ] + 1 \approx b _ { P G } [ 1 + ( 1 - e ) B _ { G } ] + 1 ,
$$

$$
\frac { \delta R F P ^ { 2 } } { \langle R F P \rangle } = \frac { K _ { P R } } { \gamma _ { P R } + \gamma _ { R G } } ( 1 + B _ { R } ) + 1 \approx b _ { P R } ( 1 + B _ { R } ) + 1 ,
$$

where

$$
B _ { G } = \frac { k _ { o f f } } { k _ { o n } + k _ { o f f } } \frac { k _ { T X } ( \gamma _ { R G } + \gamma _ { P G } + k _ { o n } + k _ { o f f } ) } { ( \gamma _ { R G } + k _ { o n } + k _ { o f f } ) ( \gamma _ { P G } + k _ { o n } + k _ { o f f } ) }
$$

and

$$
B _ { R } = \frac { k _ { o f f } } { k _ { o n } + k _ { o f f } } \frac { k _ { T X } ( \gamma _ { R G } + \gamma _ { P R } + k _ { o n } + k _ { o f f } ) } { ( \gamma _ { R G } + k _ { o n } + k _ { o f f } ) ( \gamma _ { P R } + k _ { o n } + k _ { o f f } ) } .
$$

We can see that the bigger the translational burst size,the bigger the Fano factors. The Fano factors of GFP and RFP (Eqs.(41) and(42)） for the two-state promoter are bigger than those for the constitutive promoter (Eqs.(12)and (14)),and the influence of the two-state promoter is characterized by $B _ { G }$ and $B _ { R }$

When $\gamma _ { R G } = \gamma _ { R }$ ,the coeficients of variance of GFP and RFP are

$$
\begin{array} { c } { { \eta _ { G F P } = \displaystyle \sqrt { \displaystyle \frac { 1 } { \langle G F P \rangle } \bigg ( 1 + \frac { k _ { P G } } { \gamma _ { R G } + \gamma _ { P G } } \bigg ) + \frac { 1 } { 1 + \displaystyle \frac { \gamma _ { R G } } { \gamma _ { P G } } \langle R G \rangle } ( 1 - e ) B _ { G } } } } \\ { { \displaystyle \approx \sqrt { \displaystyle \frac { 1 } { \langle G F P \rangle } ( 1 + b _ { P G } ) + \frac { \gamma _ { P G } } { ( 1 - e ) f _ { o n } k _ { T X } } ( 1 - e ) B _ { G } } } } \\ { { \displaystyle = \sqrt { \displaystyle \frac { \gamma _ { P G } } { ( 1 - e ) f _ { o n } k _ { T X } } \Big [ \frac { 1 } { b _ { P G } } + 1 + ( 1 - e ) B _ { G } \Big ] } , } } \end{array}
$$

$$
\eta _ { R F P } \approx \sqrt { \frac { \gamma _ { P R } } { f _ { o n } k _ { T X } } \biggl [ \frac { 1 } { b _ { P R } } + 1 + B _ { R } \biggr ] } .
$$

We can see that noises of RFP and GFP are bigger than those for the constitutive promoter (see Eqs.(13）and (17))，and the influence the two-state promoter is characterized by $B _ { R }$ and $B _ { G }$ The bigger the translational burst size,the smaller the noise of the proteins,which is the same as the operon with the constitutive promoter.

3.2.3.The correlation between mRNAs and the correlation between proteins

For the operon with the constitutive promoter,both synthesis and degradation of RG and Rare independent with each other,so numbers of RG and R are uncorrelated.However, for the operon with the two-state promoter,mRNAs RG and R are synthesized only when the promoter is in the on state,and both mRNAs are justunder degradation in the off state.This will bring correlation between numbers of RG and R,which is clearly shown in the stochastic simulation (Fig.4B).The correlation between RG and R depends on the dynamics parameters of the two-state promoter: $k _ { o n } , k _ { o f f }$ and $k _ { T X } .$ Wewill get the analytical result for the correlation and discuss the influences of these parameters.

When $\gamma _ { R G } = \gamma _ { R }$ ,then $A _ { R } = A _ { R G } = A$ ,we will get

$$
\begin{array} { l } { \rho _ { R G - R } = \displaystyle \frac { 1 } { \sqrt { \left( 1 + \displaystyle \frac { 1 } { A e } \right) \left( 1 + \displaystyle \frac { 1 } { A ( 1 - e ) } \right) } } , } \\ { \rho _ { m R - m G } = \displaystyle \frac { \sqrt { 1 - e } } { \sqrt { 1 - \displaystyle \frac { e } { 1 + \displaystyle \frac { 1 } { A } } } } , } \end{array}
$$

where

$$
A = \frac { k _ { o f f } } { k _ { o n } + k _ { o f f } } \frac { k _ { T X } } { ( \gamma _ { R G } + k _ { o n } + k _ { o f f } ) } .
$$

Unlike the operon with the constitutive promoter where $\rho _ { R G - R } = 0$ ，mRNAs RG and R transcribed from a two-state promoter have nontrivial correlation which is dependent on $e$ and $A$ 、If we adjust the dynamics parameters of the two-state promoters,the correlation will increase as $A$ become larger. The first product term of $A$ is $f _ { o f f } = k _ { o f f } / ( k _ { o n } + k _ { o f f } )$ which is the possibility that promoter is in the off state.The effects of $f _ { o f f }$ on the correlation are shown in Fig.4A and B.If the promoter staysin the on state too long,the correlation between RG and R will be disturbed by the independent synthesis of RG and R (Fig.4A). The second product term is $k _ { T X } / ( \gamma _ { R G } + k _ { o n } + k _ { o f f } )$ .It quantifies the influence of the transcriptional burst size $( k _ { T X } / k _ { o f f } )$ on the correlation.If the transcriptional burst size is very small, the possibility that both RG and Rare synthesized in a period of on state will be small.This leads to small correlation between the numbers of RG and R(Fig.4C,both the burst sizes of RG and R are O.15). Taken together all of these results,we get the conclusion that the more time promoter stays in the off state and the bigger transcriptional burst size,the bigger the correlation between mRNAs.When $A \gg 1$ ， $\rho _ { m R - m G } \to 1$ ，which means promoter dynamics strongly influences the correlation.

When $\gamma _ { R G } = \gamma _ { R }$ and $\gamma _ { P R } = \gamma _ { P G }$ ,then $B _ { R } = B _ { G } = B$ ，the correlation between proteins is

$$
\begin{array} { r l } { \rho _ { R F P - G F P } = \frac { \sqrt { 1 - e } } { \sqrt { \left( 1 + \frac { 1 } { b _ { R R } } \left( \gamma _ { R G } + \gamma _ { R G } \right) \right)}  \left[ 1 + \frac { 1 } { b _ { R G } } \left( \gamma _ { R G } + \gamma _ { R G } \right) - \frac { e } { 1 + \frac { 1 } { B } } \right] } } \\ { \approx \frac { \sqrt { 1 - e } } { \sqrt { \left( 1 + \frac { 1 } { b _ { R R } \left( 1 + B \right) } \right) \left( 1 + \frac { 1 } { b _ { P G } \left( 1 + B \right) } - \frac { e } { 1 + \frac { 1 } { B } } \right) } } } \end{array}
$$

![](images/d83d0e1273d5eea483d26e77d433a12f7b342b837ba31c2213c70309fcd0f09e.jpg)  
Figl transcription burst size(C） would lower the correlation between two mRNAs.In the simulations $\gamma _ { R } = \gamma _ { R G } = 0 . 0 0 3 3 \ s ^ { - 1 } , e = 0 . 5 , k _ { o n } = 0 . 0 0 6 \ s ^ { - 1 } , k _ { T X } = 0 . 3 \ s ^ { - 1 }$ ：other parameters in (A) $k _ { o f f } = 0 . 0 0 0 7 5 s ^ { - 1 }$ $f _ { o f f } \approx 0 . 1 1$ ,the average transcriptional burst sizes of RG and R are $b _ { R G } = b _ { R } = 2 0 0$ ：(B) $k _ { o f f } = 0 . 0 0 6 s ^ { - 1 }$ $f _ { o f f } = 0 . 5$ ， $b _ { R G } = b _ { R } = 2 5$ (C) $k _ { o f f } = 1 \ s ^ { - 1 } , f _ { o f f } \approx 1$ $b _ { R G } = b _ { R } = 0 . 1 5$

When YRG  Y PG

$$
B \approx \frac { k _ { o f f } } { k _ { o n } + k _ { o f f } } \frac { k _ { T X } } { ( \gamma _ { P G } + k _ { o n } + k _ { o f f } ) } .
$$

We can see the correlation between proteins is bigger than in the operon with the constitutive promoter (Eq.(24)).Changing dynamics parameters of the two-state promoters could change the correlation between proteins.If we adjust the parameters of two-state promoter and let $B {  } 0$ ，correlation between proteins will be the same for the constitutive promoter.

# 3.2.4.Effectsof dynamicsparametersonthe correlation

Among three dynamics parameters of the two-state promoter, E.coli cell seems to adjust $k _ { o f f }$ to modulate the transcription strength (So et al.,2O11).We first investigate how the correlation depends on $k _ { o f f } .$ Both the stochastic simulation and analytical results are shown in Fig.5Aand B.They agree with each other very well.As we discussed above，the two-state promoter would increase the correlation between proteins compared with the constitutive promoter. When $k _ { o f f }$ decreases to zero (Fig. 4A),the promoter dynamics will be the same as the constitutive promoter, and the promoter will not be turned off. When $k _ { o f f } \gg k _ { o n }$ (Fig. 4C), the promoter stays in the on state only for a very short time and the transcriptional burst sizes are very small.So the possibility that both RG and Rare synthesized in same period of on state wil be small,and the correlation between RG and R will be lost. Between these two limits,the correlation would increase first and then decrease as $k _ { o f f }$ increase further (Fig.5A and B). The exact theoretical $k _ { o f f }$ at which $\rho _ { R F P - G F P }$ gets the maximal value is a little complicated for general case.But from Eq.(47),we can see that $\rho _ { R F P - G F P }$ get its maximal value when $B$ get the maximal value for the case of $\gamma _ { R } = \gamma _ { R G }$ and $\gamma _ { P R } = \gamma _ { P G }$ . When $\gamma _ { R G } \gg \gamma _ { P G }$ ，

$$
B \approx \frac { k _ { o f f } } { k _ { o n } + k _ { o f f } } \frac { k _ { T X } } { ( \gamma _ { P G } + k _ { o n } + k _ { o f f } ) }
$$

will get the maximal value at $k _ { o f f } = \sqrt { k _ { o n } ( k _ { o n } + \gamma _ { P G } ) }$ ，which means the correlation between RFP and GFP will get the maximal value at this point.

Wealso study the correlation between proteins with different dynamics parameters while keeping the average expression level constant.When we adjust $k _ { o f f }$ or $k _ { o n } ,$ we adjust $k _ { T X }$ accordingly to keep the effective transcription rate $K = k _ { o n } k _ { T X } / ( k _ { o n } + k _ { o f f } )$ unchanged.Analytical results and stochastic simulations for the correlation between proteins are shown in Fig.5C-F.If we adjust the dynamics parameters of transcription,the correlation between the numbers of mRNAs coding for RFP and GFP will change,and the correlation between proteins varies accordingly.In the case of fixing $k _ { o n }$ and increasing $k _ { o f f }$ the duration time of one transcription burst decreases,and the time that the promoter stays in the off state are not changed.The average numbers of mRNAs R and RG areunchanged,but these mRNAs are synthesized in a series of shorter time windows and in other times are just degraded.This will lead to larger correlation between mRNAs,which will transmit to proteins level (Fig.5C and D). Based on similar reason, fixing $k _ { o f f }$ and increasing $k _ { o n }$ will decrease the correlation between the number of mRNAs coding for RFP and GFP,and then decrease the correlation between proteins (Fig.5E and F).

In Fig.5A,Cand E,a variation of terminator efficiency does not significantly change the correlation between proteins in some regimes.This is because the correlation between R and RG is significant in these regimes (see Eq.(46)),so the ratio of RG in the total mRNA(determined bye）would not obviously influence the correlation between proteins.This phenomenon is one of the main differences between these two kinds of promoters.Outside of these regimes,the polar effect will affect the correlation between proteins obviously: the larger the termination efficiency，the smaller the correlation (see Fig.5A, C,and E). However, changing the translation rate in the normal range $( 0 . 0 1 - 1 \ s ^ { - 1 } )$ almost does not vary the correlation (see Fig.5B,D,and F).The dependence is obvious only when the translation rate is very small (below $0 . 0 0 1 \ s ^ { - 1 }$ ）which is quite rare for protein synthesis in bacteria. So adjusting translation rate is still a better strategy than adjusting termination efficiency to tune expression ratio of genes in the operon. This is the same with the constitutive promoter.

# 4.Discussion

In the post-genome era,understanding the relationship between gene sequences,genes organization and biological functions isa great challenge.In this work,we study noise of gene expression in the bicistronic operon with polar effect.We try to figure out howdifferent parametersaffect the correlation of these two gene expressions.Our result may be helpful to understand which mechanism cell chooses to coordinate gene expression levels and why.

Previous experiments have shown that the expression correlation between two genes in the same operon is stronger than those in two separate operons even with identical promoters (Ray and Igoshin,2012；Tabor et al.,20o8). This strengthened correlation comes from co-transcription of the two genes (Sneppen et al., 2010；Swain,2004；Ray and Igoshin,2012；Iber,2006). It makes sense that intergenic terminator would lower the correlation. If co-translation is not considered,translation processes of different genes in the same operon are independent with each other.This may lead the correlation of gene expressions to be further reduced at the protein level.

For the large protein complex synthesis,subunits need to be produced in a determined ratio to avoid wasting and to increase the efficiency (Carmi et al., 2006,2009; Swain,2004).As shown in Figs.3 and 5,if the cell tunes the subunit expression level in transcription level using terminator in the intergenic region,the correlation of these two proteins would be lowered,which is not favored by the cell.However,altering the translation rate almost does not alter the correlation in a large parameter space (Figs.3 and 5).So tuning the protein levels with the translation rate would be a better strategy. Actually, recent work by Quax et al. (2013）shows that different translation rates are a key factor determining expression levels of genes in an operon. Correlative expressions of enzymes in the same metabolic pathway will avoid intermediate cumulation which may be harmful.Thus putting these enzyme genes in an operon without obvious polar effect would benefit cell growth (Ray and Igoshin,2012).

Using bioinformatic methods,it was found that there are a lot of terminators in the intergenic region of the operons (Lesnik et al., 2001). It is practical that a cell may tune the expression ratio at the transcriptional level for those genes in an operon by inserting terminators between genes.So there is a balance between the advantage of co-regulation in the same operon and the detrimental effect of lowered correlation by the polar effect.For those circumstances that function are not sensitive with the correlation, operon with intergenic terminator would be one of the choices to tune the expression ratio.For example,recA and recX genes form an operon with an intergenic terminator in E. coli (Pagés et al, 2003). RecA and RecX are two proteins with the opposite functions in the process of repairing of double strand DNA breaking.Normal cell function needs both of them (Stohl et al.,20o3).RecA forms poly-RecA to repair DSB(double strand breaking),and RecX can inhibit functionofRecAastheratio of RecXto RecAvariesina broad range (Stohl et al., 2oo3). So low correlation between them would have little impact on their function. It is no wonder why a cell utilizing a terminator with $e \approx 0 . 9$ maintains a relatively lower level of RecX with RecA without affecting their functions.

![](images/b654aced710766127787728d326a572feaae0872068cc53c3214c059a682a9cb.jpg)  
igfec aalytal $k _ { o n } , k _ { T X }$ are fixed, only $k _ { o f f }$ is changed; in (C,D) $k _ { o n }$ and the average mRNA expression levels are fixed, $k _ { o f f }$ is changed and $k _ { T X }$ is changed correspondingly;in (E,F) $k _ { o f f }$ and the average mRNA expression levels are fixed, $k _ { o n }$ is_changed and $k _ { T X }$ ischangedcorrespondingly.Parametersused areas follows: $\gamma _ { P R } = \gamma _ { P G } = 0 . 0 0 0 2 9 s ^ { - 1 }$ L $\gamma _ { R } = \gamma _ { R G } = 0 . 0 0 3 3 s ^ { - 1 }$ ， $K _ { P R } = 0 . 1 6 ~ { s ^ { - 1 } }$ , in (A,C,E) $k _ { P G } = 0 . 1 6 s ^ { - 1 }$ ; (B,D,F) $e { = } 0 . 7$ (A,B) $k _ { o n } = 0 . 0 0 6 s ^ { - 1 }$ $k _ { T X } = 0 . 3 \ s ^ { - 1 }$ ; (C,D) $k _ { o n } = 0 . 0 0 6 s ^ { - 1 }$ ; (E,F) $k _ { o f f } = 0 . 0 0 6 s ^ { - 1 }$ ，

Changing mRNA stability can tune the protein expression ratio, but it will also change the protein correlation significantly. Increasing lifetime of full-length mRNA will enhance the correlation,and increasing lifetime of the short one gets the opposite effect. It is because a longer lifetime of full-length mRNA would lead to a bigger translation burst,and a larger ratio of protein produced from the full-length mRNA，both of which can increase the correlation.Increasing the lifetime of short mRNA just lowers the ratio ofuncorrelated RFP from total RFP protein.However, the cell seems to avoid tuning the mRNA stability for different parts of one operon when the proteins they code have related function (Bernstein et al., 2002; Kristoffersen et al., 2012; Quax et al., 2013).

Intrinsic and extrinsic noises together determine gene expression profiles (Taniguchi et al.，2O1O； Rosenfeld et al.，2005; Paulsson,2oo4). In this work,we just consider the former. The intrinsic noise is the main source of noise when the average number of protein is low (Taniguchi et al.,2O1O;Elowitz et al., 2002).For a single cell,extrinsic noise varies relatively slowly. Experiments show it would introduce correlation for independent expressed proteins in the time of $2 0 \mathrm { m i n }$ to one cell-cycle (Taniguchi et al., 2010；Rosenfeld et al., 2005). However, $2 0 \mathrm { m i n }$ isalong time for fast growing cells,so our intrinsic results would not lose the sense.

Genes work as a network.So to understand the genome design principle we need to consider interactions between genes,including the influence from the stochasticity of gene expression. Our analytical results can give direct estimation for the relation of noise and correlation of gene expression,which may help to understand the relationship between genome structure and robust gene interaction network.Recent development of single cell or molecule experiment offers quantitative measurement of gene expression in time and space dimension(Taniguchi et al.,2010;So et al.，2011；Nevo-Dinur et al.,2011). Our results may help to design and understand this kind of experiments.

# Acknowledgments

The Work was supported by the National Basic Research Program of China (Grant no.2O13CB83410O), National Natural Science Foundation of China（Grant nos.11121403 and 11274320）and Open Project Program of State Key Laboratory of TheoreticalPhysics, Institute of Theoretical Physics,Chinese Academy of Sciences,China (no.Y4KF171CJ1).H.S.thanks Weimou Zheng for useful discussions. L.X.acknowledges support from National Natural Science Funds for Young Scholar(no.113O4115)and support from China Postdoctoral Science Foundation (no.2013M541282).

# Appendix A. Parameter estimation for gene expression in E. coli

1. The mRNA degradation rate:about $80 \%$ of mRNAs have a half-life time $3 { - } 8 \mathrm { m i n }$ (Bernstein et al.， 2002). We use $\beta _ { m R N A } = 1 / 5$ $\operatorname* { m i n } ^ { - 1 } \sim 0 . 0 0 3 3 \ s ^ { - 1 }$ by default,and vary mRNAs half-life just in the range of $0 . 5 { - } 1 5 \operatorname* { m i n }$ when we discuss the parameter dependence.   
2.The protein degradation rate: protein is only under growth dilutioninbacteria,almostnodegradation,so $\beta _ { p r o t e i n } = \ln$ $2 / T = 0 . 0 0 0 2 9 s ^ { - 1 }$ ， $T$ is the doubling time of bacterial cell,we choose $T { = } 4 0 \ \mathrm { m i n }$ ：   
3.The translation rate:considering the limit for translation elongation and the time needed for translation initiation (about ${ \mathrm { ~ 1 ~ s , ~ } }$ （204 Proshkin et al.，2O1O),the fastest translation rate should be around $1 s ^ { - 1 }$ ，the smallest we use $0 . 0 0 1 1 s ^ { - 1 }$ (average one translation happens from the most stable mRNA during its $1 5 \mathrm { m i n }$ half-life time). The average translation rate is in the range of $0 . 1 - 0 . 3 \ s ^ { - 1 }$ (Bremer and Dennis,1996). For E. coli with doubling time $T { = } 4 0 \ \mathrm { m i n }$ ,theaverage translation rate isaround $0 . 1 6 s ^ { - 1 }$ which we used as default (Bremer and Dennis,1996).   
4.The transcription rate:the highest estimation $1 s ^ { - 1 }$ is from rrn genes transcription for the fast growing E.coli cell (Bremer and Dennis, 1996).

5.The two-state promoter parameters: from Fig.S12C and D of So et al. (2011)， we use $k _ { o n } = 0 . 0 0 6 s ^ { - 1 }$ ， $k _ { o n } = 0 . 0 0 6 s ^ { - 1 }$ ， $k _ { T X } =$ $0 . 3 \ \mathsf { s } ^ { - 1 }$ as default.

# Appendix B. Stochastic simulation method

The Gillespie(1977) algorithm, developed byDaniel T.Gillespie in 197Os,is well known as an effective stochastic simulation algorithm.Bycalculating the reaction probability density function (RPDF) $P ( \tau , \mu )$ using the current reaction rate and reactant species combination number,probability of when the next reaction will occur $( \tau )$ and which reaction will occur $( \mu )$ can be provided.Then we renew the molecular number of relevant species.In this way, we get a statistically correct evolution trajectory of the chemical system,which is rigorously equivalent to that produced by the distribution function $f ( q _ { 1 } , . . . , q _ { n } ; t )$ as the solution of the master equation. We use Gillespie algorithm (Gillespie,1977；Hao et al., 2011a） to simulate the biochemical reactions shown in Fig.1. Parameters used in the simulations are shown in Appendix A.We first generate a long enough stochastic evolution trajectory for each chemical species.With these trajectories,we start the sampling after the system reaches the steady state (the waiting time we used is 1O protein half-lives).In order to make sure that thestatistic pointsare fully independent of each other,we select the points in the trajectories with the interval of 2 protein halflives time,and then calculate the correlation between different species.Each data point of the simulation results is the result of at least 10,000 trials.

# References

Bentele，K.，Saffert,P.，Rauscher，R.,， Ignatova，Z.，Blüithgen，N.，2O13.Efficient translation initiation dictates codon usage at gene start. Mol. Syst. Biol. 9, 675.   
Berg,O.G.,1978.A model for the statistical fluctuations of protein numbers in a microbial population. J. Theor. Biol. 71, 587-603.   
Bernstein, J.A.,Khodursky, A.B., Lin,P.-H., Lin-Chao, S., Cohen, S.N.,2002.Global analysis of mRNA decay and abundance in Escherichia coli at single-gene resolution using two-color fluorescent DNA microarrays. Proc. Natl. Acad. Sci. USA 99, 9697-9702.   
Bremer，H.，Dennis,P.P.，1996.Modulation of chemical composition and other parameters of the cell by growth rate. In: Neidhardt,F.C.(Ed.), Escherichia coli and Salmonella. ASM Press, Washington, D.C., pp. 1553-1569.   
Cannarozzi, G., Schraudolph,N.N., Faty,M., vonRohr,P.,Friberg,M.T.,Roth,A.C., Gonnet, P., Gonnet, G.,Barral, Y., 2010. A role for codon order in translation dynamics. Cell 141, 355-367.   
Carmi,S., Levanon,E.,Havlin,S., Eisenberg,E., 2oo6. Connectivity and expression in protein networks: proteins in a complex are uniformly expressed. Phys. Rev. E 73,031909.   
Carmi, S., Levanon, E.Y., Eisenberg,E., 2Oo9. Efficiency of complex production in changing environment. BMC Syst. Biol. 3,3.   
Chalancon, G., Ravarani, C.N.J.,，Balaji, S.，Martinez-Arias,A., Aravind,L., Jothi, R, Babu,M.M.,2012. Interplay between gene expression noise and regulatory network architecture. Trends Genet. 28,221-232.   
Chen,H., Bjerknes,M.,Kumar, R.,Jay,E.,1994. Determination of the optimal aligned spacing between the Shine-Dalgarno sequence and the translation initiation codon of Escherichia coli mRNAs.Nucleic Acids Res.22, 4953-4957.   
Cho,B.-K., Zengler, K., Qiu, Y., Park,Y.S., Knight, E.M., Barrett, C.., Gao,Y.,Palsson,B.O., 2009.The transcription unit architecture of the Escherichia coli genome. Nat. Biotechnol. 27,1043-1049.   
Chong, S., Chen, C., Ge, H., Xie, X.S.,2014. Mechanism of transcriptional bursting in bacteria. Cell 158,314-326.   
Condon,C.， 2Oo7. Maturation and degradation of RNA in bacteria. Curr. Opin. Microbiol.10,271-278.   
Dandekar, T., Snel, B., Huynen,M., Bork, P., 1998. Conservation of gene order:a fingerprint of proteins that physically interact. Trends Biochem. Sci. 23, 324-328.   
Eldar,A., Elowitz, M.B., 2010. Functional roles for noise in genetic circuits. Nature 467, 167-173.   
Elowitz, M.B., Levine, A.J., Siggia,E.D.,Swain,P.S., 20o2. Stochastic gene expression in a single cell. Science 297, 1183-1186.   
Gillespie,D.T., 1977. Exact stochastic simulation of coupled chemical reactions. J. Phys. Chem. 81, 2340-2361.   
Golding, I., Paulsson, J., Zawilski, S.M., Cox,E.C., 20o5. Real-time kinetics of gene activity in individual bacteria. Cell 123,1025-1036.   
Goodman,D.B., Church, G.M., Kosuri, S., 2013. Causes and effects of N-terminal codon bias in bacterial genes. Science 342, 475-479.   
Guiell,M., van Noort, V., Yus,E., Chen, W.-H.,Leigh-Bell, J.,Michalodimitrakis, K., Yamada,T.，Arumugam，M.，Doerks，T.，Kihner，S.，Rode,M.，Suyama，M., Schmidt, S., Gavin, A.-C., Bork, P., Serrano, L., 2oo9. Transcriptome complexity in a genome-reduced bacterium. Science 326, 1268-1271.   
Gur,E., Biran, D., Ron, E.Z., 2011. Regulated proteolysis in Gram-negative bacteria一 how and when? Nat. Rev. Microbiol. 9, 839-848.   
Hao,Y., Xu,L., Shi, H.,2011a. Theoretical analysis of catalytic-sRNA-mediated gene silencing. J. Mol. Biol. 406, 195-204.   
Hao,Y., Zhang, Z.J., Erickson, D.W., Huang, M., Huang, Y., Li,J., Hwa,T., Shi, H., 2011b. Quantifying the sequence-function relation in gene silencing by bacterial small RNAs. Proc. Natl. Acad. Sci. USA 108, 12473-12478.   
Hiroe, A., Tsuge, K., Nomura, C.T., Itaya, M., Tsuge, T., 2O12. Rearrangement of gene order in the phaCAB operon leads to effective production of ultrahighmolecular-weightpoly[(R)-3-hydroxybutyrate] in genetically engineered Escherichia coli. Appl. Environ. Microbiol. 78,3177-3184.   
Iber,D., 2oo6. A quantitative study of the benefits of co-regulation using the spolIA operon as an example. Mol. Syst. Biol.2,43.   
Jacob，F.，Monod, J.，1961. Genetic regulatory mechanisms in the synthesis of proteins. J. Mol. Biol. 3, 318-356.   
Klumpp，S., Dong, J.，Hwa,T.，2012. On ribosome load,codon bias and protein abundance. PLoS One 7, e48542.   
Kristoffersen, S.M., Haase, C., Weil, M.R., Passalacqua, K.D., Niazi, F., Hutchison, S.K., Desany,B., Kolsto,A.-B., Tourasse, N.J.,Read, T.D.,Okstad, O.A., 2012.Global mRNA decay analysis at single nucleotide resolution reveals segmental and positional degradation patterns in a Gram-positive bacterium. Genome Biol. 13, R30.   
Lesnik, E.A., Sampath,R.,Levene, H.B., Henderson,T.J., McNeil, J.A., Ecker, D.J.,2001. Prediction of rho-independent transcriptional terminators in Escherichia coli. Nucleic Acids Res. 29, 3583-3594.   
Liang,L.W.,Hussein,R., Block, D.H.S.，Lim，H.N.，2013.Minimal effect of gene clustering on expression in Escherichia coli. Genetics 193,453-465.   
Li, G.-W., Oh,E.,Weissman, J.S.,2012. The anti-Shine-Dalgarno sequence drives translational pausing and codon choice in bacteria. Nature 484, 538-541.   
Nevo-Dinur, K., Nussbaum-Shochat, A., Ben-Yehuda, S., Amster-Choder, O., 2011. Translation-independent localization of mRNA in E. coli. Science331, 1081-1084.   
Nishizaki, T.,Tsuge, K., Itaya, M., Doi, N., Yanagawa, H., 2OO7. Metabolic engineering of carotenoid biosynthesis in Escherichia coli by ordered gene assembly in Bacillus subtilis. Appl. Environ. Microbiol. 73,1355-1361.   
Pagés, V., Koffel-schwartz, N., Fuchs, R.P.P., 20O3. recX, a new SOS gene that is cotranscribed with the recA gene in Escherichia coli. DNA Repair (Amst）2, 273-284.   
Paulsson, J., 2oo4. Summing up the noise in gene networks. Nature, 415-418.   
Paulsson，J.，Berg，O.G.，Ehrenberg，M.，2Ooo. Stochastic focusing:fluctuationenhanced sensitivity of intracellular regulation. Proc. Natl. Acad. Sci. USA 97, 7148-7153.   
Peccoud, J., Ycart, B., 1995. Markovian modeling of gene-product synthesis. Theor. Popul. Biol. 48, 222-234.   
Price,M.N., Huang, K.H., Arkin, A.P., Alm, E.J.,20o5. Operon formation is driven by co-regulation and not by horizontal gene transfer. Genome Res. 15, 8o9-819.   
Proshkin, S., Rahmouni, A.R., Alexander, M., Nudler,E., 2010. Cooperation between translating ribosomes and RNA polymerase in transcription elongation. Science 328, 504-508.   
Quax,T.E.F., Wolf, Y.L., Koehorst,J.J., Wurtzel, O., van der Oost,R., Ran,W., Blombach,F, Makarova, K.S., Brouns, S.J.J., Forster, A.C., Wagner, E.G.H., Sorek,R., Koonin,E.V., van der Oost,J.,2013. Differential translation tunes uneven production of operonencoded proteins. Cell Rep. 4, 938-944.   
Ray, J.C.J., Igoshin, O.A., 2012. Interplay of gene expression noise and ultrasensitive dynamics affects bacterial operon organization. PLoS Comput. Biol. 8, e1002672.   
Rosenfeld,N., Young,J., Alon, U., Swain,P., Elowitz, M.,20o5. Gene regulation at the single-cell level. Science 307,1962-1965.   
Salgado,H.，Moreno-Hagelsieb,G.，20oo. Operons in Escherichia coli: genomic analyses and predictions. Proc. Natl. Acad. Sci. USA 97, 6652-6657.   
Selinger, D.W., Saxena, R.M., Cheung, K.J., Church, G.M., Rosenow, C.,20o3.Global RNA half-life analysis in Escherichia coli reveals positional patterns of transcript degradation. Genome Res. 13, 216-223.   
Sneppen, K., Pedersen, S., Krishna,S., Dodd,I., Semsey,S., 2010. Economy of operon formation: cotranscription minimizes shortfall in protein complexes. MBio 1 e00177-10.   
So,L.-H., Ghosh,A., Zong, C., Sepulveda, L.A., Segev, R., Golding, I., 2O11. General properties of transcriptional time series in Escherichia coli. Nat. Genet. 43, 554-560.   
Stohl, E.a., Brockman, J.P., Burkle, K.L.,Morimatsu, K., Kowalczykowski, S.C., Seifert, H.S.,20o3. Escherichia coli RecX inhibits RecA recombinase and coprotease activities in vitro and in vivo. J. Biol. Chem. 278,2278-2285.   
Swain, P.S., 2Oo4. Efficient attenuation of stochasticity in gene expression through post-transcriptional control. J. Mol. Biol. 344, 965-976.   
Swain, P.S., Elowitz, M.B., Siggia, E.D., 2oo2. Intrinsic and extrinsic contributions to stochasticity in gene expression. Proc. Natl. Acad. Sci. USA 99, 12795-12800.   
Tabor,J.J.， Bayer,T.S.， Simpson, Z.B., Levy,M., Ellington, A.D.， 2O08. Engineering stochasticity in gene expression. Mol. Biosyst. 4, 754-761.   
Taniguchi, Y.,Choi, P.J., Li, G.-W., Chen,H., Babu, M., Hearn, J., Emili, A., Xie, X.S., 2010.Quantifying E. coli proteome and transcriptome with single-molecule sensitivity in single cells. Science 329, 533-538.   
Thattai, M., van Oudenaarden, A.,2oo1. Intrinsic noise in gene regulatory networks. Proc. Natl. Acad. Sci. USA 98, 8614-8619.   
Tuller,T., Carmi, A., Vestsigian, K., Navon, S., Dorfan, Y., Zaborske,J., Pan, T.,Dahan, O.,Furman,I.,Pilpel,Y.,2010. An evolutionarily conserved mechanism for controlling the efficiency of protein translation. Cell 141, 344-354.   
Vellanoweth，R.，Rabinowitz,J.，1992. The influence of ribosome-binding-site elements on translational eficiency in Bacillus subtilis and Escherichia coli in vivo. Mol. Microbiol. 6, 1105-1114.   
Wen，J.-D.， Lancaster，L.， Hodges,C.， Zeri， A.-C., Yoshimura， S.H.，Noller，H.F., Bustamante, C.， Tinoco，I., 2oo8. Following translation by single ribosomes one codon at a time. Nature 452, 598-603.