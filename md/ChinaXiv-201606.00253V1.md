# Perceptually Weighted Analysis-by-Synthesis Vector Quantization for Low Bit Rate MFCC Codec

Gang Min, Xiongwei Zhang,Xia Zou,and Jibin Yang

Abstract-This letter presents a perceptually weighted analysis -by-synthesis vector quantization(VQ) algorithm for low bit rate MFCC codec.Different from conventional VQ of MFCCs vector, thisalgorithm uses an analysis-by-synthesis technique and aims to minimize the perceptually weighted spectral reconstruction distortion rather than the distortion of MFCCs vector itself. Also,to reduce the computational complexity，we propose a practical suboptimal codebook searching technique and embed it into the split and multistage vector quantization framework. Objective and subjective experimental results for Mandarin speech show that the proposed algorithm yields intelligible and natural sounding speech for speech coding at 6oo-24oo bit/s. Compared to current VQ in MFCC codec,the output speech qualityis substantiallyimproved in terms of frequency-weighted segmental SNR,STOI,PESQ and MOS score.

Index Terms-MFCCs,vector quantization,speech coding, analysis-by-synthesis.

# I.INTRODUCTION

through quantization of mel-frequency cepstral coeffcients (MFCCs),which provides a promising new approach for speech coding throughout 60O-480O bit/s.The speech quality of MFCC codec even exceeds the output of state-of-the-art MELPe codec [1]-[2]. Also,high-resolution MFCCs vector encoded in MFCC codec could be easily down-converted to low-resolution MFCCs vector for distributed speech recognition (DSR) in ETSI Aurora DSR standard [3]. Despite natural sounding speech yielded from MFCC codec, there is still room for further improving the speech quality.For example,there exists the phenomenon of spectrum smearing since the triangle frequency window used for MFCCs extraction is overlapped. Moreover， the quantization process of MFCCs vector will further aggravate this problem,which degrades the articulation of the coded speech for MFCC codec.

Vector quantization (VQ) plays important role in reducing the bit rate of speech coding.However, the quantization error increases rapidly with the decreasing of quantization bits [4],which is the main reason accounting for degradation of speech quality.In the current MFCC codec，MFCCs vector is directly quantized with the objective of minimizing the quantization distortion of itself,i.e., the codeword of minimum square error is selected as the quantized vector [2]. Yet,this conventional VQ method can not straightly illustrate the effect of quantization on the final speech distortion.Inspired by the perceptual weighting technique used in the low bit rate codec [5]-[6],which considers the auditory masking properties of the human's ear, we change the objective of VQ of MFCCs vector as: the codeword of minimum perceptually weighted spectral reconstruction distortion is selected as the quantized MFCCs vector: To achieve this objective,we propose a new framework for VQ of MFCCs vector to minimize the end-toend perceptually weighted spectral distortion for speech signal rather than the quantization distortion for MFCCs vector. The proposed method strategically use a closed-loop technique known as analysis-by-synthesis (AbS),which has been broadly used for speech coding and the quantization of compressed sensing measurements [7]-[1O]. The synthesis step employs a speech power spectrum reconstruction technique for measuring the effect of MFCCs vector quantization on the final speech quality,and the analysis step is performed followed by the synthesis step in order to select an appropriate codeword to minimize the perceptually weighted spectral distortion. To the best of our knowledge,the perceptually weighted AbS approach has not been used for VQ of MFCCs vector earlier, which is shown to provide a much better speech quality than the conventional VQ method that directly quantizes the MFCCs vector itself in an open-loop fashion. Since AbS requires higher computational cost,a low complexity suboptimal codebook searching technique is also proposed.

Notations: for the $k ^ { t h }$ speech frame $( k = 1 , 2 , . . . , K )$ ， $y _ { k }$ and $f _ { k }$ denote the power spectrum and MFCCs vectors, $\hat { y } _ { k }$ and $\hat { f } _ { k }$ denote their quantized_values, $\boldsymbol { W _ { k } }$ denotes the perceptual weighting matrix. $\mathcal { F } = \{ \tilde { f } _ { 1 } , \tilde { f } _ { 2 } , . . . , \tilde { f } _ { J } \}$ ， $\mathcal { F } _ { s } = \{ \tilde { f } _ { 1 } , \tilde { f } _ { 2 } , . . . , \tilde { f } _ { I } \}$ denote the codebook and suboptimal codebook of MFCCs vector, respectively. $\tilde { f } _ { j } , j = 1 , \overset { \cdot } { 2 } , . . . , J$ denotes the codeword (also called centroid in this paper). $\tilde { y } _ { j }$ denotes the power spectrum reconstructed from $\tilde { f } _ { j } . \ : { \mathcal { C } } _ { j } , j = 1 , 2 , . . . J$ denotes the jth cluster in the codebook training phase.

# II.ANALYSIS-BY-SYNTHESISVECTORQUANTIZATION

# A.Mel-frequency cepstral coeficients

The extracting procedure of MFCCs begins with enframing the speech waveforms $x ( n )$ by a window $w \left( n \right)$

$$
x _ { m } \left( n \right) = x \left( m R + n \right) w \left( n \right)
$$

where $N ( 0 \leq n \leq N - 1 )$ is the window length, $R$ is the frame shift, $m$ is the frame index.Then,the speech frame could be concisely denoted as,

$$
\pmb { x } = [ x _ { m } \left( 0 \right) , x _ { m } \left( 1 \right) , . . . , x _ { m } \left( N - 1 \right) ] ^ { \intercal }
$$

The power spectrum of each speech frame is,

$$
{ \pmb y } = \left| \mathrm { F } \left\{ { \pmb x } \right\} \right| ^ { 2 }
$$

where $\mathrm { ~ F ~ } \{ { \pmb x } \}$ is the $N$ -point FFTof $x , | \cdot |$ denotes the modulus of a complex number.

The latter $N / 2 - 1$ elements of $_ y$ will be discarded due to the symmetry. Then, the power spectrum is Mel-filtered by a set of weighting functions,i.e., the Mel-scale weighting matrix $\Phi \in \mathbf { R } ^ { M \times \left( N / 2 + 1 \right) }$ ， where $M$ is the number of Mel-filter bands. Generally, $\Phi$ is designed based on human perception of pitch frequency and implemented in the form of a bank of filters, each filter is with a triangular frequency response [2]. Finally, MFCCs vector is computed through the $\log ( \cdot )$ and discrete cosine transform (DCT),

$$
\pmb { f } = \mathrm { D C T } \{ \log ( \pmb { \Phi } \pmb { y } ) \} = \pmb { \mathrm { D } } \log ( \pmb { \Phi } \pmb { y } )
$$

where $\mathbf { D }$ is the $M \times M$ DCT matrix.

The power spectrum $_ y$ could be approximately reconstructed from MFCCs vector $f$ as follows [1]-[2],

$$
\pmb { y } = \pmb { \Phi } ^ { \dag } \mathrm { e x p } ( \mathbf { D } ^ { - 1 } \pmb { f } ) = { ( \pmb { \Phi } ^ { \dag } \pmb { \Phi } ) } ^ { - 1 } \pmb { \Phi } ^ { \dag } \mathrm { e x p } ( \mathbf { D } ^ { - 1 } \pmb { f } )
$$

where $\Phi ^ { \dagger }$ denotes the Moore-Penrose pseudo-inverse of $\Phi$

# B. Distance measure for $\mathit { V Q }$ of MFCCs vector

Conventionally, the MFCCs vector $f$ is directly quantized using the Euclidean distance measure [2],

$$
d \left( \pmb { f } , \hat { \pmb { f } } \right) = \left\| \pmb { f } - \hat { \pmb { f } } \right\| _ { 2 } ^ { 2 } = \sum _ { i = 0 } ^ { M - 1 } \left( f _ { i } - \hat { f } _ { i } \right) ^ { 2 }
$$

here,we consider the perceptual weighting filter $P ( z )$

$$
P \left( z \right) = \frac { H \left( \gamma ^ { - 1 } z \right) } { H \left( \beta ^ { - 1 } z \right) } = \frac { 1 - \displaystyle \sum _ { i = 1 } ^ { p } a _ { i } \beta ^ { i } z ^ { - i } } { 1 - \displaystyle \sum _ { i = 1 } ^ { p } a _ { i } \gamma ^ { i } z ^ { - i } }
$$

where $H \left( z \right) = 1 \mathord { \left/ { \vphantom { 1 \sum _ { i = 1 } ^ { p } { { a _ { i } } z ^ { - i } } } } \right. \kern - delimiterspace } \left( 1 - \sum _ { i = 1 } ^ { p } { { a _ { i } } z ^ { - i } } \right)$ is the linear prediction (LP） synthesis filter, $a _ { i }$ is the short-term LP coefficients and $p$ is the prediction order. $0 < \gamma < \beta \leq 1$ are the perceptual weighting factors that control the energy of the error in the formant regions [11]. Referring to the EVRC codec,we choose $\beta = 0 . 9 , \gamma = 0 . 5$ ,respectively[12].

Let $P ( \omega )$ denote the frequency response of perceptual weighting filter defined in(7),

$$
P \left( \omega \right) = P \left( z \right) | _ { z = e ^ { j \omega } }
$$

In the spectral domain,the perceptual weighting matrix $W$ could be expressed as a diagonal matrix,

$$
W = \left[ \begin{array} { c c c c } { { w _ { 0 } } } & { { 0 } } & { { \cdot \cdot \cdot } } & { { 0 } } \\ { { 0 } } & { { w _ { 1 } } } & { { \cdot \cdot \cdot } } & { { 0 } } \\ { { \vdots } } & { { \vdots } } & { { \ddots } } & { { \vdots } } \\ { { 0 } } & { { \cdot \cdot \cdot } } & { { 0 } } & { { w _ { N / 2 } } } \end{array} \right]
$$

here,

$$
w _ { i } = P \left( \omega \right) \Big | _ { \omega = \frac { 2 \pi } { N } i } \ , \quad i = 0 , 1 , . . . , N / 2 .
$$

As mentioned above, $N$ is the FFT length

Consequently, the perceptually weighted spectral distortion between the original power spectrum $_ y$ and the quantized power spectrum $\hat { \pmb { y } }$ could be expressed as,

$$
d \left( \pmb { y } , \hat { \pmb { y } } \right) = \sum _ { i = 0 } ^ { N / 2 } w _ { i } ( y _ { i } - \hat { y } _ { i } ) ^ { 2 } = ( \pmb { y } - \hat { \pmb { y } } ) ^ { \top } \pmb { W } \left( \pmb { y } - \hat { \pmb { y } } \right)
$$

# C. Overview of perceptually weighted AbS VQ

As is shown in Fig.1, the proposed perceptually weighted AbS VQ mainly consists of two steps:a synthesis step that reconstructs the speech power spectrum from the MFCCs codeword $\tilde { f } _ { j }$ and an analysis step that extracts the power spectrum of the $k ^ { t h }$ speech frame and calculates the perceptually weighted spectral distortion between $y _ { k }$ and $\tilde { y } _ { j }$ . These two steps will be repeated $J$ times for searching the whole codebook $\mathcal { F }$ .Finally, the codeword of minimum $d ( \pmb { y } _ { k } , \tilde { \pmb { y } } _ { j } )$ is selected as the quantized MFCCs vector.

![](images/cf6e2e9fb92f045dc61e9813602a491df6ee98e60f2ecef04339ee5bd86ec7cd.jpg)  
Fig.1.Diagram of perceptually weighted AbS VQ.

# D. Codebook training

To train the codebook $\mathcal { F }$ ,there are two problems to resolve. The first is how to assign each training sample into a cluster, the second is how to determine the centroid of each cluster. Conventionally, the first can be resolved via the nearest neighbor criterion.However,the second needs further derivations.

Let $\tilde { y } _ { j }$ denote the power spectrum reconstructed from the centroid of the $j ^ { t h }$ cluster. For any training sample $\pmb { y } _ { k }$

$$
d \left( { \pmb y } _ { k } , { \tilde { \pmb y } } _ { j } \right) = d \left( { \pmb y } _ { k } , \pmb { \Phi } ^ { \dagger } \mathrm { e x p } ( { \bf D } ^ { - 1 } { \tilde { \pmb f } } _ { j } ) \right)
$$

Then, $\pmb { y } _ { k }$ can be assigned into a cluster $\mathscr { C } _ { j }$ according to the nearest neighbor criterion,

$$
\begin{array} { r } { \mathcal { C } _ { j } = \{ \pmb { y } _ { k } | d \left( \pmb { y } _ { k } , \tilde { \pmb { y } } _ { j } \right) < d \left( \pmb { y } _ { k } , \tilde { \pmb { y } } _ { i } \right) , k = 1 , 2 , . . . , K \mathrm { ~ , ~ } } \\ { i = 1 , 2 , . . . , J , i \neq j \} } \end{array}
$$

Consequently, for $K$ speech frames as training，the total distortion is,

$$
\begin{array} { l } { { \displaystyle e _ { t } = \sum _ { k = 1 } ^ { K } d \big ( y _ { k } , \hat { y } _ { k } \big ) = \sum _ { j = 1 } ^ { J } \sum _ { y _ { k } \in \mathcal { C } _ { j } } d \big ( y _ { k } , \tilde { y } _ { j } \big ) } } \\ { ~ = \sum _ { j = 1 } ^ { J } \sum _ { y _ { k } \in \mathcal { C } _ { j } } \big ( y _ { k } - \tilde { y } _ { j } \big ) ^ { \top } W _ { k } \big ( y _ { k } - \tilde { y } _ { j } \big ) }  \\ { ~ = \displaystyle \sum _ { j = 1 } ^ { J } \sum _ { y _ { k } \in \mathcal { C } _ { j } } \big \| \sqrt { W _ { k } } \big ( y _ { k } - \tilde { y } _ { j } \big ) \big \| _ { 2 } ^ { 2 } } \\ { ~ = \displaystyle \sum _ { j = 1 } ^ { J } \sum _ { y _ { k } \in \mathcal { C } _ { j } } \Big \| \sqrt { W _ { k } } \Big ( y _ { k } - \Phi ^ { \dagger } \mathrm { e x p } ( \mathbf { D } ^ { - 1 } \tilde { f } _ { j } ) \Big ) \Big \| _ { 2 } ^ { 2 } } \end{array}
$$

let $e _ { j } = \sum _ { \pmb { y } _ { k } \in \mathcal { C } _ { j } } \left\| \sqrt { \pmb { W } _ { k } } \left( \pmb { y } _ { k } - \pmb { \Phi } ^ { \dag } \exp \left( \mathbf { D } ^ { - 1 } \tilde { \pmb { f } } _ { j } \right) \right) \right\| _ { 2 } ^ { 2 }$ denote the total distortion associated with all samples which belong to the $j ^ { t h }$ cluster, then $\boldsymbol { e } _ { t }$ could be concisely represented as,

$$
e _ { t } = \sum _ { j = 1 } ^ { J } e _ { j }
$$

With respect to the centroid $\tilde { f } _ { j } , e _ { t }$ could be minimized,

$$
\frac { \partial e _ { t } } { \partial \tilde { f } _ { j } } = \frac { \partial \sum _ { j = 1 } ^ { J } e _ { j } } { \partial \tilde { f } _ { j } } = \frac { \partial e _ { j } } { \partial \tilde { f } _ { j } }
$$

Applying the chain rule and setting det = O,we have, af

$$
\frac { \partial \Phi ^ { \dag } \exp \left( \mathbf { D } ^ { - 1 } \widetilde { \mathbf { f } } _ { j } \right) } { \partial \widetilde { f } _ { j } ^ { \mathrm { T } } } \frac { \partial e _ { j } } { \partial \Phi ^ { \dag } \exp \left( \mathbf { D } ^ { - 1 } \widetilde { \mathbf { f } } _ { j } \right) } = 0
$$

Let us recall the definition of $e _ { j }$ ，it is apparent that the solution of(18) is also the solution of(17),

$$
\frac { \partial \sum _ { y _ { k } \in \mathcal { C } _ { j } } \left. \sqrt { W _ { k } } \left( y _ { k } - \Phi ^ { \dagger } \mathrm { e x p } ( \mathbf { D } ^ { - 1 } \tilde { f } _ { j } ) \right) \right. _ { 2 } ^ { 2 } } { \partial \Phi ^ { \dagger } \mathrm { e x p } ( \mathbf { D } ^ { - 1 } \tilde { f } _ { j } ) } = 0
$$

that is,

$$
\left( \sum _ { y _ { k } \in \mathcal { C } _ { j } } W _ { k } \right) \Phi ^ { \dagger } \exp \left( \mathbf { D } ^ { - 1 } \tilde { \mathbf { f } } _ { j } \right) = \sum _ { y _ { k } \in \mathcal { C } _ { j } } W _ { k } y _ { k }
$$

$\boldsymbol { W _ { k } }$ is a diagonal non-zero matrix, then $\sum \textbf { \em W } _ { k }$ is non$\boldsymbol { y } _ { k } \in \boldsymbol { C } _ { j }$ singular. Hence, the optimal centroid for the $j ^ { t h }$ cluster is,

$$
\tilde { f } _ { j } = \mathbf { D } \log \left( \Phi \left( \sum _ { y _ { k } \in \mathcal { C } _ { j } } W _ { k } \right) ^ { - 1 } \sum _ { y _ { k } \in \mathcal { C } _ { j } } W _ { k } y _ { k } \right)
$$

Insummary, the codebook training algorithm for perceptually weighted AbS VQ is shown in Algorithm1.

# $E$ 、Low complexity suboptimal codebook searching

Different from the codebook training phase,the codebook searching procedure should be performed in an online fashion, so the computational complexity becomes a major issue.In the primary perceptually weighted AbS VQ scheme in Fig.1,we should reconstruct speech power spectrum from each codeword $\tilde { f } _ { j }$ in $\mathcal { F }$ and calculate the corresponding perceptually weighted spectral distortion. The computational complexity is too high because the number of codewords in $\mathcal { F }$ ，i.e., $J$ isvery large.Consequently，we propose a low complexity suboptimal codebook searching technique as is shown in Fig.2. Through the conventional VQ of MFCCs vector $f _ { k } , K$ optimal candidate codewords are selected from $\mathcal { F }$ to constitute the suboptimal codebook $\mathcal { F } _ { s }$ .For $\forall \tilde { { \pmb f } } _ { j } \in \mathcal { F } _ { s } , \forall \tilde { { \pmb f } } _ { i } \in \mathcal { F } \backslash \mathcal { F } _ { s }$

$$
\left\| \pmb { f } _ { k } - \tilde { \pmb { f } } _ { j } \right\| _ { 2 } ^ { 2 } < \left\| \pmb { f } _ { k } - \tilde { \pmb { f } } _ { i } \right\| _ { 2 } ^ { 2 }
$$

Only the codewords in $\mathcal { F } _ { s }$ are used for the reconstruction of speech power spectrum and the calculation of perceptually weighted spectral distortion, so the computational complexity will be reduced dramatically, since we will choose $I \ll J$

Algorithm 1 Codebook training algorithm.   
Input: training samples $\begin{array} { r } {  { \mathcal { V } } ~ = ~ \left\{ \ b { y } _ { 1 } , \ b { y } _ { 2 } , . . . , \ b { y } _ { K } \right\} } \end{array}$ ，weighting matrixes $\mathcal { W } = \{ W _ { 1 } , W _ { 2 } , . . . , W _ { K } \}$   
Output: MFCCs codebook $\mathcal { F } = \{ \tilde { f } _ { 1 } , \tilde { f } _ { 2 } , . . . , \tilde { f } _ { J } \}$   
1i: Initialiation: $n = 1 , e _ { t } ^ { ( 0 ) } = \mathrm { { \stackrel { \sim } { 0 } } }$ 1， $\mathrm { ~ T ~ } = 5 0$ ， $\delta = 0 . 1$ ， $\mathcal { F }$ s initialized randomly.   
2: while $n \leq \mathrm { T } , \triangle e _ { t } \geq \delta$ do   
3: （20 $/ /$ Line 4 reconstructs the power spectrum $\tilde { y } _ { j }$ from $\tilde { f } _ { j }$ 4: $\tilde { \pmb { y } } _ { j } = \pmb { \Phi } ^ { \dagger } \exp \left( \mathbf { D } ^ { - 1 } \tilde { \pmb { f } } _ { j } \right)$   
5: // Line 6 assigns each sample ${ \pmb y } _ { k }$ into a cluster $\mathcal { C } _ { j }$ ： 6: $\mathcal { C } _ { j } = \{ \pmb { y } _ { k } | d \left( \pmb { y } _ { k } , \tilde { \pmb { y } } _ { j } \right) < d \left( \pmb { y } _ { k } , \tilde { \pmb { y } } _ { i } \right) , i = 1 , 2 , . . . , J , i \neq j \}$ 7: //Line 8 updates the cluster centroid $\tilde { f } _ { j }$ ：   
8: $\tilde { f } _ { j } = \mathbf { D } \log \left( \Phi \left( \sum _ { y _ { k } \in \mathcal { C } _ { j } } W _ { k } \right) ^ { - 1 } \sum _ { y _ { k } \in \mathcal { C } _ { j } } W _ { k } y _ { k } \right)$   
9: // Line 10_computes the total distortion $e _ { t }$ ：   
10: $e _ { t } ^ { ( n ) } = \sum _ { j = 1 } ^ { J } \sum _ { y _ { k } \in \mathcal { C } _ { j } } ^ { \mathrm { ~ \normalfont ~ ( ~ ) ~ } } \left\| \sqrt { { W } _ { k } } \left( y _ { k } - \Phi ^ { \dagger } \exp \left( \mathbf { D } ^ { - 1 } \tilde { \mathbf { f } } _ { j } \right) \right) \right\| _ { 2 } ^ { 2 }$ 11: // Line 12 computes the variation of et, $\triangle e _ { t }$ ：：   
12: $\begin{array} { l } { \triangle e _ { t } = \| e _ { t } ^ { ( n ) } - \dot { e } _ { t } ^ { ( n - 1 ) } \| _ { 2 } ^ { 2 } } \\ { n = n + 1 } \end{array}$   
13:   
14:end while

![](images/120d633688023ae09e7ef8c0061227fcbcf6d17a4830c29cd058afcbd9d06954.jpg)  
Fig.2.Diagram of low complexity suboptimal codebook searching.

# F.AbS based split and multistage VQ

Furthermore, from the perspective of practical applications, split VQ(SVQ) or multistage VQ(MSVQ) is usually adopted as an alternative of direct VQ to reduce the storage and computational complexity.In order to embed AbS VQ into the SVQ and MsVQ framework,we will keep $Q$ optimal candidate codewords in each sub-vector codebook or sub-stage codebook to constitute the final suboptimal codebook $\mathcal { F } _ { s }$ . It should be mentioned that there is only one stage codebook as a result of limited bits for quantization when the speech coding rate is $6 0 0 ~ \mathrm { b i t / s }$ . As is shown in Tab.I,we will design a fourstage AbS vector quantizer to quantize the formant and pitch information for speech coding at $2 4 0 0 ~ { \mathrm { b i t / s } }$ ，where each stage has 4096 codewords.As for speech coding at $1 2 0 0 \ \mathrm { b i t / s }$ a two-stage AbS vector quantizer is designed,where the first stage has 4O96 codewords and the second stage has 2048 codewords.The bit allocation scheme of AbS SVQ is the same as which in [2]. Therefore, $\mathcal { F } _ { s }$ will consist of $Q ^ { 4 } , Q ^ { 2 }$ $Q$ codewords for speech coding at 2400,120O and 60O bit/s, respectively. If $Q = 1$ ，the AbS SVQ method will regress to be the conventional VQ method in [1]-[2].

TABLEI BITALLOCATIONOFABSMULTISTAGEVQ.   

<html><body><table><tr><td>Rate (bit/s)</td><td>Bits/ Frame</td><td>Energy (C1)</td><td>Formant&Pitch (C2-C60)</td></tr><tr><td>2400</td><td>54</td><td>6-bit SQ</td><td>(12-12-12-12)-bit AbSMSVQ</td></tr><tr><td>1200</td><td>27</td><td>4-bit SQ</td><td>(12-11)-bitAbSMSVQ</td></tr></table></body></html>

# III.EXPERIMENTS AND RESULTS

# A.Dataset and evaluation metrics

We use 40oo chosen utterances spoken by 4O speakers (20 males and 2O females) from CASIA Chinese database[13] to train the MFCCs codebook.The duration of training speech is ${ \sim } 3 . 5 \mathrm { h }$ ，which contains1,682,162 speech frames( $3 0 ~ \mathrm { m s }$ time frames, $7 . 5 ~ \mathrm { m s }$ frame shifts).Another 96 chosen utterances from the same database,spoken by unseen 16 speakers (8 males and8females),are used as the test set.The duration of test speech is ${ \sim } 5 \mathrm { ~ m ~ }$ .Both the training speech and the test speech are downsampled at $8 \mathrm { k H z }$ .We choose $N = 2 4 0$ ， $M =$ $6 0 , p = 1 0$ to extract MFCCs vector and perform LP analysis.

We use three metrics to evaluate the quality of coded speech, which are frequency-weighted segmental SNR (fwsegSNRs) [14],perceptual evaluation of speech quality (PESQ)[15] and short-time objective intelligibility(STOI） [16].FwsegSNRs andPESQ measures illustrate the overall speech quality while the STOI measure illustrates the speech intelligibility.

# B.Objective evaluation of speech quality

The results of objective evaluation are shown in Tables IIV, in which the reuslts of conventional VQ method are marked in underline while the best results are highlighted in bold. It is clearly illustrated that the proposed AbS VQ method yields substantiallyhigherfwsegSNRs,PESQ,andSTOI score thanthe conventional VQmethod,which demonstrates that the speech quality is much better.Moreover, $\mathcal { F } _ { s }$ will approach $\mathcal { F }$ with the increasing of $Q$ ,so the speech quality continues being improved.Specifically,the final improvement is impressive in the case of speech coding at 24OO bit/s， the average fwsegSNRs,PESQ and STOI score is improved by 1.2dB, 0.12 and $2 \%$ ,respectively.

In addition,we can see that AbS MSVQ substantially yields better results than AbS SVQ, this is because it fully exploits the redundancy between the components of MFCCs vector. As mentioned above,larger $Q$ will lead to more codewords in $\mathcal { F } _ { s }$ ,hence,to make the trade-off between speech quality and computational complexity,we will choose $Q = 2 , 4 , 5$ in the case of speech coding at 2400,120O and 600 bit/s,respectively.

TABLEII COMPARISON ON THE STOI SCORE $( \% )$ ·   

<html><body><table><tr><td rowspan="2">Rate (bit/s)</td><td rowspan="2">Quantization method</td><td colspan="5">Q</td></tr><tr><td>1</td><td>2</td><td>3</td><td>4</td><td>5</td></tr><tr><td>2400</td><td>AbS SVQ</td><td>91.15</td><td>92.31</td><td>92.64</td><td>92.77</td><td>92.89</td></tr><tr><td>2400</td><td>AbS MSVQ</td><td>91.48</td><td>92.69</td><td>92.98</td><td>93.04</td><td>93.35</td></tr><tr><td>1200</td><td>AbS SVQ</td><td>88.24</td><td>89.52</td><td>89.83</td><td>89.98</td><td>90.02</td></tr><tr><td>1200</td><td>AbS MSVQ</td><td>88.32</td><td>89.58</td><td>89.86</td><td>90.12</td><td>90.17</td></tr><tr><td>600</td><td>AbS SVQ</td><td>84.98</td><td>85.86</td><td>85.89</td><td>86.00</td><td>86.07</td></tr></table></body></html>

TABLEIV COMPARISON ON THE PESQ SCORE.   

<html><body><table><tr><td rowspan="2">Rate (bit/s)</td><td rowspan="2">Quantization method</td><td colspan="5">Q</td></tr><tr><td>1</td><td>2</td><td>3</td><td>4</td><td>5</td></tr><tr><td>2400</td><td>AbS SVQ</td><td>3.22</td><td>3.25</td><td>3.28</td><td>3.29</td><td>3.32</td></tr><tr><td>2400</td><td>AbS MSVQ</td><td>3.23</td><td>3.30</td><td>3.32</td><td>3.34</td><td>3.35</td></tr><tr><td>1200</td><td>AbS SVQ</td><td>2.91</td><td>2.98</td><td>2.99</td><td>3.01</td><td>3.02</td></tr><tr><td>1200</td><td>AbSMSVQ</td><td>2.94</td><td>3.00</td><td>3.01</td><td>3.02</td><td>3.03</td></tr><tr><td>600</td><td>AbS SVQ</td><td>2.63</td><td>2.66</td><td>2.66</td><td>2.67</td><td>2.68</td></tr></table></body></html>

# C. Subjective listening test

14native Chinese volunteers (7 males and 7 females) are invited to participate in a subjective listening test.Each volunteer is asked to rate the coded speech through the standard five point mean opinion score(MOS）[17]. Each volunteer is presented with two speech files (one male and one female)encoded byVQ and AbS MSVQ based MFCC codec at 2400,1200 and $6 0 0 ~ { \mathrm { b i t / s } }$ ，respectively. The results of subjective listening test are illustrated in Tab.V,which show a good match with PESQ evaluation.

TABLEV SUBJECTIVEEVALUATIONRESULTS.   

<html><body><table><tr><td>Rate (bit/s)</td><td>2400</td><td>1200</td><td>600</td></tr><tr><td>AbS MSVQ</td><td>3.24±0.10</td><td>2.92±0.12</td><td>2.70±0.15</td></tr><tr><td>VQ[1]-[2]</td><td>3.16±0.15</td><td>2.82±0.14</td><td>2.65±0.15</td></tr></table></body></html>

# D.Discussion on further performance improvement

Instead of utilizing the Moore-Penrose pseudo-inverse to reconstruct the speech power spectrum in (5), the synthesis stage of AbS VQ could be improved by some new algorithms [18]- [19],which is expected to further improve the speech quality. Furthermore，the speech waveforms could be reconstructed from the power spectrum using the improved algorithm in [20] rather than the inverse short-time Fourier transform magnitude algorithm in [21],which is also beneficial for yielding higher speech quality by taking into account the differences between voiced speechandunvoicedspeech.

TABLEI COMPARISON ON THE FWSEGSNRS(DB).   

<html><body><table><tr><td rowspan="2">Rate (bit/s)</td><td rowspan="2">Quantization method</td><td colspan="5">Q</td></tr><tr><td>1</td><td>2</td><td>3</td><td>4</td><td>5</td></tr><tr><td>2400</td><td>AbS SVQ</td><td>13.74</td><td>14.20</td><td>14.42</td><td>14.52</td><td>14.56</td></tr><tr><td>2400</td><td>AbSMSVQ</td><td>13.84</td><td>14.55</td><td>14.75</td><td>14.87</td><td>14.94</td></tr><tr><td>1200</td><td>AbS SVQ</td><td>11.91</td><td>12.25</td><td>12.44</td><td>12.51</td><td>12.56</td></tr><tr><td>1200</td><td>AbSMSVQ</td><td>12.05</td><td>12.41</td><td>12.56</td><td>12.65</td><td>12.70</td></tr><tr><td>600</td><td>AbS SVQ</td><td>10.75</td><td>10.91</td><td>10.97</td><td>11.01</td><td>11.02</td></tr></table></body></html>

# IV.CONCLUSION

In this paper, we propose a perceptually weighted AbS VQ approach for low bit rate MFCC codec.The objective of VQ is changed to minimize the perceptually weighted spectral reconstruction distortion rather than the distortion of MFCCs vector itself.A suboptimal codebook searching technique is proposed for practical implication. Objective and subjective tests show that the speech quality is substantially improved when compared to the output of current MFCC codec.

# REFERENCES

[1]L.E.Boucheron,P.L.De Leon,and S.Sandoval,“Hybrid Scalar/Vector Quantization of Mel-Frequency Cepstral Coefficients for Low Bit-Rate Coding of Speech,’Data Compression Conference (DCC),Mar. 2011, pp.103-112.   
[2]L.E.Boucheron,P.L.De Leon,and S. Sandoval,“Low Bit-Rate Speech Coding Through Quantization of Mel-Frequency Cepstral Coefficients," IEEE Trans. Audio,Speech,and Language Processvol. 20, no. 2, pp. 610-619,Feb.2012.   
[3]ETSI ES 2O2 212,“Speech Processing,Transmission and Quality aspects (STQ)；Distributed speech recognition;Extended advanced front-end feature extraction algorithm;Compression algorithms；Back-end speech reconstruction algorithm,”2005.   
[4]R.M.Gray and D.L.Neuhoff,“Quantization,”IEEE Trans.Inforamtion theory.vol.44,no.6,pp.2325-2383,Oct.1998.   
[5]B.S.Atal and M.R.Schroeder,“Predictive coding of speech and subjective error criteria,”IEEE Trans.Acoust.，Speech,Signal Process. vol.ASSP-27,pp.247-254,Mar.1979.   
[6] P.Kroon and B.S.Atal,“Predictive coding of speech using analysisby-synthesis techniques,"inAdvances in SpeechSignal Process.S.Furui and M. Sondhi,Eds.New York:Marcel Dekker,1992,pp.141-164.   
[7]P.Kroon and E.Deprettere,“A class of analysis-by-synthesis predictive coders for high quality speech coding at rates between 4.8 and 16 kbit/s," IEEE Journal Select.Areas Commun.vol.6,no.2,pp.353-363,Feb. 1988.   
[8]E.George and M. Smith,“Speech analysis/synthesis and modification usingan analysis-by-synthesis/overlap-add sinusoidal model,”IEEE Trans. Speech and Audio Process.vol.5,no.5,pp.389-406, Sep.1997.   
[9]S.Chatterjee and T.V.Sreenivas,“Analysis-by-Synthesis based switched transform domain split VQ using Gaussian mixture model,”IEEE Int. Conf.Acoust., Speech,Signal Process.(ICASSP),May 20O9,pp.4117- 4120.   
[10]A. Shirazinia,S.Chatterjee,M. Skoglund,“Analysis-by-Synthesis Quantization for Compressed Sensing Measurements,”IEEE Trans.Signal Process.vol.61,no.22,pp.5789-5800,Nov.2013.   
[11]J.H.Chen,R.V.Cox,Y.C.Lin,et al,“ALow-Delay CELP Coder for the CCITT $1 6 ~ \mathrm { k b / s }$ Speech Coding Standard,”IEEE Journal Select. Areas Commun.vol.10,no.5,pp.830-849,Jun.1992.   
[12]3GPP2 C.SO014-D,“Enhanced Variable Rate Codec,Speech Service Options3,68,70 and 73 forWideband Spread SpectrumDigital Systems, Oct.2010.   
[13] 2015 [Online].Available:http://www.chineseldc.org.   
[14]J.Tribolet,P.Noll,B.McDermott,etc,“A study of complexity and quality of speech waveform coders,IEEE Int.Conf.Acoust.，Speech, Signal Process.(ICASSP),May 1978,pp.586-590.   
[15]A.W.Rix,J.G.Beerends,M.P.Hollier,etc,“Perceptual evaluation of speech quality (PESQ)-a new method for speech quality assessment of telephone networksand codecs,IEEE Int. Conf.Acoust.,Speech,Signal Process.(ICASSP),May 2001 vol.II, pp.749-752.   
[16]C.H.Taal,R.C.Hendriks,R.Heusdens,etc,“An Algorithm for intelligibility prediction of time-frequency weighted noisy speech,”IEEE Trans.Acoust.,Speech,and Signal Process.vol.19,no.7.pp.2125-2136, Jul. 2011.   
[17]P.C.Loizou, Speech Enhancement:Theory and Practice.Boca Raton, FL:CRC,2007.   
[18]G.Min,X.W. Zhang,J.B.Yang,etc,“Speech reconstruction from mel-frequency cepstral coefficients via $\ell _ { 1 }$ -norm minimization,”IEEEInt. Workshop on Multimedia Signal Process.(MMSP'15),Oct.2015,pp.1-5.   
[19]G.Min,X.W.Zhang,J.B.Yang,etc,“Speech Reconstruction from MFCC based on nonnegative and sparse priors,’IEICE Trans.Fundamentals.vol.E98A,no.7,pp.1540-1543,Jul.2015.   
[20]W.B.Jiang,R.D.Ying,P.L.Liu,“Speech reconstruction for MFCCbased low bit-rate speech coding,’IEEE Int.Conf.on Multimedia & Expro (ICME),Oct.2014,pp.1-6.   
[21]D.W.Griffin and J.S.Lim,“Signal estimation from modified short time fourier transform,IEEE Trans.Acoust.,Speech,and Signal Process.vol. 32,no.2, pp.236-243,Apr.1984.