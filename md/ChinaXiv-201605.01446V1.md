# A fast line-scanning-based detection algorithm for real-time SAR ship detection

Xiaolong Wang $\cdot \cdot$ Cuixia Chen

Received: 20 July2013/Revised: 27 August 2014/Accepted: 27August 2014/Published online:11September 2014   
$\circledcirc$ Springer-VerlagLondon 2014

AbstractSynthetic aperture radar (SAR) provides a powerful surveillance capability allowing the observation of target,independently from weather effects and from the day and night cycle.Unfortunately, the automatic interpretation of SAR images is often complicated and time consuming. In support of real-time vessel monitoring,a fast line-scanning detector designed for detecting ships from SAR imagery is proposed in this paper. The detector does not require any prior knowledge about ships and background observation. It uses a novel local gray-level gathering degree algorithm to detect potential targets and then a complementary filtering scheme to reject false alarms.The performance analysis over real SAR images confirms that the proposed detector works well in various circumstances with high detection rate, fast detection speed and perfect shape preservation.

KeywordsLocal gray-level gathering degree (LGGD) : Real-time $\cdot \cdot$ Ship detection $\cdot \cdot$ Synthetic aperture radar (SAR)

# 1 Introduction

Ship detection is of great significance for various mandates associated with marine monitoring,such as traffic surveillance,military reconnaissance,fishery monitoring,as well as vessel search and rescue [1].With the increasing volume of image data that are collected from air-and space-borne SAR systems,a large amount of investigations have proven that SAR can be used for ship detection purpose.During the last two decades,much effort has been devoted in developingalgorithms,establishing infrastructures and even buildingautomatic target recognition(ATR) systems for processing marine SAR images [2-8].The distributed constant false alarm rate (CFAR) framework is the most widely accepted conceptual model. CFAR-like detectors,as the widely used ship detection approach on which several current operational systems rely[5], involve the parameter estimations of ships and local clutters.Also,the threshold setting is essential so that a constant false alarm probability is guaranteed for all values of unknown clutter parameters.The strong dependence of the CFAR schemes on prior knowledge about ships and background observation limits their application in automatic detection.Besides,due to differences in environmental conditions such as changes in clutter edge,multiple targets or jamming, the target detection is often corrupted.

The developmentof maritime ATR systemaimed at implementinga simple,yeteffective means of rapidlyalerting and cueing the supervisors to regions within high-resolution SAR imagery that could contain targets of interest [9,1O]. Automatic detection is the key step of the maritime SAR ATR system.Although great effort has beenpaid, fast and robust ship detection still remains a challenge.Currently, the developed algorithms mostly emphasize the detection rate but not the time,without regard to construct a practical system, just as some CFAR-like methods.Actually, real-time processing is usually a requirement for the operational ship detection systems.In recent years,Duman et. al.used region covariance(RC) and codifference algorithms to solve SAR ATR target detection problem [11,12]. The proposed method is shown to deliver high detection accuracies and low false alarm rates.However, its computational complexity is still high due to RC algorithm,codifference algorithmand training and testing steps with support vector machines (SVMs), although directional filters have been introduced to decrease the search space.Computational complexity is a major problemin developing a fast detection algorithm.High computational complexity always causes a large computation cost, hence,affecting the system's implemental efficiency.Therefore,it has become an urgent problem to improve the detection speed on the condition of high detection rate.None but simple and fast ship detection algorithm can afford to meet the expanding requirements of intelligence,surveillance,and reconnaissance.

Motivated by the characteristics of spatial intensity distribution as observed in any SAR images,a“local gray-level gathering degree (LGGD)” algorithm for ship detection is developed.Based on this,a fast line-scanning detector is proposed in support of real-time vessel monitoring. The detector constituted by a linear LGGD algorithm and a postpositive complementary filtering scheme,is named S-LGGD detector. The merit of a postpositive filtering scheme rather than a prepositive one(which is generally adopted by most detectors）is the latter always reduces target information during noise suppressing.Performances of the detector have been investigated on several real SAR images,and moreover,a practical real-time ship detection system for an X-band airborne SAR system has also been established.Experiments show that the proposed detector works well in various circumstances with high detection rate,fast detection speed and perfect shape preservation.

# 2 Algorithms and methods

Cell detection is the first canonical problem to be treated in developing a framework for automatic exploitation of ship information from SAR imagery.Many systems rely on the CFAR approach which interprets the difference between the target and its surrounding ocean clutter as a difference of intensity levels.However, the validity of the CFAR approach strictly depends on assumptions,hypotheses and even prior knowledge about ships and background observation,which increase its computational complexity and put its applications into a dilemma of the choice between performance and speed.To solve the problem,the new detection algorithm must exhibit low computational complexity and a reasonable false alarm rate.

# 2.1 Description of LGGD algorithm

The intensity of each resolution cell in SAR imagery denotes the radar scattering characteristics of a random ground object. Cells with different intensities and spatial distributions often represent the various ground objects.Suppose that a cell

$C _ { 1 } ( i , j )$ with intensity $I$ has the same observed intensity with another cell $C _ { 2 } ( i + \Delta i , j + \Delta j )$ ,they are coherent and therefore the ground objects represented by the two cells should be the correlative objects.Accordingly,a gathering relationship of the cell pair $( C _ { 1 } , C _ { 2 } )$ at position $( i , j )$ can be expressed by

$$
G = 1 / \left( \exp ( \Delta i ) + \exp ( \Delta j ) \right) , ( ( \Delta i ) ^ { 2 } + ( \Delta j ) ^ { 2 } \neq 0 ) ,
$$

where $\Delta i$ and $\Delta j$ represent the spatial intervals of the cells in two directions (range and azimuth), respectively. For all cell pairs in relation to the cell $C _ { 1 } ( i , j )$ , a gray-level gathering relationship of the intensity $I$ at $( i , j )$ ，namely gray-level gathering degree,can be computed as

$$
G _ { I } \left( i , j \right) = \sum _ { \Delta i = 1 } ^ { M } \sum _ { \Delta j = 1 } ^ { N } 1 / \left( \exp ( \Delta i ) + \exp ( \Delta j ) \right) ,
$$

where $M$ and $N$ represent the spatial dimensions of the SAR image known as azimuth and range,respectively.

The $G _ { I }$ describes the spatial distribution of cells and intensities,and hence,itis able to highlight the changes of the spatial information.Unfortunately,its computational cost is increased with the image dimensions.To decrease computational cost,aLGGD is adopted by limiting a calculation range (window).It is obvious that the LGGD algorithm is related not only with the number of matched cells,but also with their spatial distributions.If the cells with gray-level $I$ come from the same surface of a ship target, they are gathering and hence $G _ { I }$ is large,while if they come from the ocean clutter noise,they are discrete and then $G _ { I }$ is small. Thus, ships should be detected if an appropriate threshold $G _ { \mathrm { t h } }$ is chosen.

# 2.2Design of S-LGGD detector

The LGGD algorithm does not require any prior knowledge about ships and background observation.The speed and intensity sensitivity are its outstanding merits.With these advantages,a novel ship detectoris proposed in consideration of the line-by-line data downlink and processing mode for most real-time SAR systems (especially for airborne SAR systems).The block diagram of the developed detector is shown in Fig.1.Alinear sliding windowis designed for performing a line-scanning detection.The window constituted byguard windows and reference windows includes $2 N + 2 L$ range samples (range cells) corresponding to $2 N$ reference cells and $2 L$ guard cells surrounding the test cell. Due to lack of ability for distinguishing bright cells from dark cells, the LGGD algorithm cannot distinguish from false alarms corresponding to speckle noises,sea clutters and even dark areas (such as low-wind areas,oil spills or rain cells).As a countermeasure,a complementary filtering scheme of graylevel discrimination and isolated point removal is designed to reject the false alarms.The detection process can be divided into three steps:

![](images/3eab58827a2581f5e1be4730ca747b5437d24ad9f6678dd189df0e8096c695bc.jpg)  
Fig.1 Structure of the proposed detector (S-LGGD detector).

(1）LGGD detection: For each inputted line,a sliding detection is executed by computing the LGGD value of each cell with its $2 N$ reference cells.Owing to the higher intensities of ship cells,there are often no matched cells in the sliding window for them,that is,a zero value of $G _ { I }$ is universal for ship cells.Therefore,potential target cells corresponding to the zero value of $G _ { I }$ are presented.   
(2）Gray-level discrimination: For each potential target cell, an auxiliary gray-level discrimination based on its image intensityis made,and then,target cells are differentiated from false alarms.   
(3） Targets confirmation:For the remaining target cells, througha supplementarynoise elimination, the isolated cells are removed and the ship cells are confirmed.

The window size is vital to the real-timeLGGD detention. Too large size is disadvantageous to calculation efficiency, while too small size is not enough to calculation stability.In orderto obtainareasonable size forautomatic detection,we have investigated relationships of the LGGD value with the increasing window size by statistical analysis method.For the guard window,comparisons derived from several SAR images under different background noises have shown that: Fivepixelswindow size( $\begin{array} { r } { L = 5 } \end{array}$ )is enough to protect the test cell,and more pixels could hardly contribute to a different result.For the reference window,a series of theoretical maximumLGGD values with the increased cells are calculated on the assumption that their internal cells are all coherent. Due to the exponential operator in the LGGD algorithm, the calculated valuestendto be invariablewhenreference cells are over 2O pixels.Thus,the window sizes of 3O-4Opixels 0 $2 N = 2 0 - 3 0$ and $2 L = 1 0$ ）are suggested in our scheme, while too small sizes less than 2O pixels are not suggested for its bad calculation stability.In fact, the detection performance,in case studies,is almost always improved with the increasing size of the reference windows;however, the improvement is not obvious,but computational cost is significant when the size is over 3O pixels.That is, the 4O pixels size is enough for a satisfying detection performance.Any window larger than this size is meaningless for performance improvement but can contribute a lot to computational cost.

In addition, for overcoming the limitation of the LDDG algorithm itself in distinguishing between bright cells from dark cells,we have adopted a simple and effective graylevel discrimination rule.The empirical formula for adaptive discrimination threshold $I _ { \mathrm { t h } }$ ，which is based on the average intensity $I _ { a }$ of the inputted line,is assigned for ship cells as

$$
\begin{array} { r } { I _ { \mathrm { t h } } \left\{ \begin{array} { l l } { 1 0 0 , } & { I _ { a } < 5 0 } \\ { 5 0 + I _ { a } , } & { 5 0 \le I _ { a } < 1 0 0 } \\ { I _ { a } + \left( 2 0 0 - I _ { a } \right) / 2 , } & { 1 0 0 \le I _ { a } \le 2 0 0 } \\ { I _ { a } } & { I _ { a } > 2 0 0 } \end{array} \right. . } \end{array}
$$

# 2.3 Analysis of computational complexity

To analyze the computational complexity, the typical twoparameter CFAR method [2],as the widely used ship detection algorithm on which several current operational systems rely,is selected for comparison.Based on the hypothesis that the clutter statistics obey Gaussian distribution, the twoparameter CFAR method involves three moving windows: target window, guard window and background window. The detection criterion can be expressed by

$$
\begin{array} { r l } & { \frac { X _ { t } - \mu _ { c } } { \sigma _ { c } } \bigg \{ > T _ { \mathrm { C F A R } } \mathrm { ~ \quad ~ T a r g e t ~ } } \\ & { \frac { \mu _ { t } - \mu _ { c } } { \sigma _ { c } } \bigg \{ > T _ { \mathrm { C F A R } } \mathrm { ~ \quad ~ C l u s t e r ~ } } \end{array} \mathrm { o r ~ }
$$

where $X _ { t }$ is the intensity of the test cell, $\mu _ { t }$ is the intensity mean in the target window, $T _ { C F A R }$ is a constant that controls the false alarm rate. $\mu _ { c }$ and $\sigma _ { c }$ represent the background mean and the background standard deviation,respectively,which can be computed by the following equations

$$
\begin{array} { l } { \displaystyle \mu _ { c } = \frac { 1 } { N _ { c } } \sum _ { i , j \in \Omega _ { c } } x \left( i , j \right) , } \\ { \displaystyle \sigma _ { c } = \sqrt { \frac { 1 } { N _ { c } } \sum _ { i , j \in \Omega _ { c } } \left( x \left( i , j \right) - \overline { { X _ { c } } } \right) ^ { 2 } } , } \end{array}
$$

where, $x ( i , j )$ is the intensity of cell at $( i , j ) . \Omega _ { c }$ describes the statistical region (background region) of $\mu _ { c }$ and $\sigma _ { c }$ ,and $N _ { c }$ is the number of cells in the region.

Given that the background window size for clutter statistics is $N _ { B }$ for an $N$ by $N$ cells image, the minimal number of cells for clutter statistics is $4 ( N _ { B } - 1 )$ for the CFAR method and $N _ { B }$ for our S-LGGD method. Then the corresponding complexitiescanbe computed aslisted in Tables1and2,3. In Table2,all the theoretical maximums are computed under the assumption that there are at most half of cells in the background window in correlation with the test cell (in practice, therelevant cells are farless than the assumed number in general).

Table1 Computational complexity of the two-parameter CFAR method   

<html><body><table><tr><td></td><td colspan="3">For each cell</td><td>Total for whole image</td></tr><tr><td></td><td>μi</td><td></td><td>Comparison</td><td></td></tr><tr><td>Addition</td><td>4(NB -1)-1</td><td>4(NB - 1)+4(NB -1)-1</td><td>1</td><td>N²(12NB -13)</td></tr><tr><td>Multiplication</td><td>1</td><td>4(NB-1)+2</td><td>1</td><td>4NBN2</td></tr></table></body></html>

Table 2 Computational complexity of the S-LGGD method: LGGD detection step   

<html><body><table><tr><td rowspan="2"></td><td colspan="5">LGGD detection for each cell</td><td rowspan="2">Total for whole image</td></tr><tr><td>Comparison</td><td>△i</td><td>exp(△i)</td><td>G</td><td>G1</td></tr><tr><td>Addition</td><td>NB-1</td><td>0~ NB/2</td><td>0</td><td>0</td><td>0~NB/2</td><td>(NB - 1)N² ~ (2NB - 1)N2</td></tr><tr><td>Multiplication</td><td>0</td><td>0</td><td>0 ~ NB(NB +2)/8</td><td>1</td><td>0</td><td>N² ~ (N²+2NB +8)N²/8</td></tr></table></body></html>

Table 3 Computational complexity of the S-LGGD method: discrimination and confirmation steps   

<html><body><table><tr><td></td><td colspan="3">Gray-level discrimination for each line</td><td>Targets confirmation for each line</td><td>Total for whole image</td></tr><tr><td></td><td>ITotal</td><td>lavg</td><td>Comparison</td><td>Comparison</td><td></td></tr><tr><td>Addition</td><td>N</td><td>0</td><td>N</td><td>N</td><td>3N2</td></tr><tr><td>Multiplication</td><td>0</td><td>1</td><td>0</td><td>0</td><td>N</td></tr></table></body></html>

Therefore,the numbers of addition and multiplication operations are $( 1 2 N _ { B } - 1 3 ) N ^ { 2 }$ and $4 N _ { B } N ^ { 2 }$ ,respectively, for the CFAR method, while the numbers are $( N _ { B } + 2 ) N ^ { 2 } \sim$ $2 ( N _ { B } + 1 ) N ^ { 2 }$ and $N ( N + 1 ) \sim 1 / 8 ( N _ { B } ^ { 2 } + 2 N _ { B } + 8 ) N ^ { 2 } + N$ respectively, for the S-LGGD method.Thus,the ratios of them areas follows:

$$
\begin{array} { l c l } { { { \cal R } _ { \mathrm { A d d } } } } & { { = \displaystyle \frac { N ^ { 2 } ( 1 2 N _ { B } - 1 3 ) } { N ^ { 2 } ( N _ { B } - 1 ) } ~ \sim ~ \frac { N ^ { 2 } ( 1 2 N _ { B } - 1 3 ) } { N ^ { 2 } ( 2 N _ { B } - 1 ) } } } \\ { { } } & { { } } \\ { { \displaystyle \approx 1 2 \sim 6 . } } \\ { { { \cal R } _ { \mathrm { M u l } } ~ = \frac { 4 N _ { B } N ^ { 2 } } { N ( N + 1 ) } ~ \sim } } & { { \displaystyle \frac { 4 N _ { B } N ^ { 2 } } { N ^ { 2 } \left( \frac { 1 } { B } N _ { B } ^ { 2 } + \frac { 1 } { 4 } N _ { B } + 1 \right) + N } } } \\ { { } } & { { } } \\ { { \displaystyle \approx ( N _ { B } + 4 ) \sim \frac { 3 2 N _ { B } } { N _ { B } ^ { 2 } + 2 N _ { B } + 8 } \approx ( N _ { B } + 4 ) } } \\ { { } } & { { } } \\ { { \displaystyle \sim \frac { 3 2 } { N _ { B } + 2 } . } } \end{array}
$$

It is easy to see that the computational complexity of the CFAR method is obviously higher than that of the S-LGGD method when $N _ { B } = 3 0$ is taken into account,even if there are always half of cells in background window in correlation with the test cell for the latter.For any size larger than 30 pixels (corresponding to 4O pixels window size due to $N _ { B } = 2 N = 3 0$ and $2 L = 1 0$ ),furthercomparison ismeaningless,because the performance improvement is insignifcant, but the computational costis significant for the S-LGGD method as described in Sect.2.2.In fact, the computational complexity of the S-LGGD method may be always lower than that of the CFAR method,since the relevant cells are always far less than half of cells in background window, which decreases the complexity greatly.

# 3Experimental and results

Toverify the effectiveness of the method described, the SLGGD detector(4O pixels sliding window） has been tested overa series of real SAR images,including air-and spaceborne SAR images.Due to the lack of ground truth data,a precise cross-check could not be performed.The validation of the detection results was based on the visual inspection. For comparison, the two-parameter CFAR method is used, and the corresponding results at a false alarm rate of $0 . 0 5 \%$ arepresented.

# 3.1 Capability test

A situation of multiple targets in slightly heterogeneous background,as shown in Fig.2a,is firstly used for the capability investigation. The C-band ERS-2 SAR image（ $4 0 0 \times 3 4 4$ pixels, $1 2 . 5 \mathrm { m }$ pixel size） shows a busy port containing 49 ships (bright features) in heterogeneous regions.It should be a difficult task since different scales of ships are included in the image,even some small, faint and hidden ships Figure 2b-f presents the detection results by the CFAR method and the S-LGGD method respectively.

![](images/489b4077b512226eef1f91b44abf83988c9a6cb4f3e719fdb782404e08997695.jpg)  
Fig.2 Ship detection for multiple targets situation.a Original SAR window: $1 9 \times 1 9$ pixels); d CFAR result (target window: $5 \times 5$ pixels, mage; b CFAR result (target window: $3 \times 3$ pixels,guard window: guard window: $2 5 \times 2 5$ pixels);e CFAR result (target window: $5 \times 5$ （20 $1 9 \times 1 9$ pixels);c CFAR result (target window: $5 \times 5$ pixels,guard pixels,guard window: $3 1 \times 3 1$ pixels); f S-LGGD result

Due to different scales of ships in the image (from about 3 cellsto over2O cells), the choices of detection windows are difficult for the CFAR method.For objectivity's sake,various CFAR windows have been tested on the image for obtaining an optimal detection result.Figure 2b-e shows the four better results.As can be seen, the small target windowis helpful for detection of small ships,while the large window is helpful for detection of large ships (Fig.2b,c). In addition,with the increasing guard window size(from 19 to 31) that is closer to the two times the most ship sizes,the detected false alarms graduallydecrease.

To sum up, despite some faint ships hiding in the sea clutter background, the proposed detector highlights all the 49 ships except for the only one false alarm (as encircled by white circle in Fig.2f).In contrast, the CFAR method causes more false alarms even for the optimal result (Fig.2e).It not only causes fourfalse alarms(as encircled bywhite circle in Fig.2e) but also misses two faint ships numbered as 1 and 2 in Fig.2a.Moreover, it is worth noting that a nearly perfect shape detection is achieved in comparison with the CFAR method,which is vital to the further estimations of the ship parameters,including length,width and orientation.

Some closely separated ship situations often result in a recurring detection loss to some detectors,such as CFARlike detectors, due to one or more interfering targets occupy some of the reference window cells [13].To test the situation,an ERS-2 SAR image of Suez Bay in north of the Red Sea (Fig.3a, $7 2 0 \times 7 2 0$ pixels) is adopted. Two white rectangleboxesindicatetwonoticeableareasAandBinwhich many ships jammed. The corresponding detection results by the CFAR method and the S-LGGD method are shown in Fig.3b-e.As can be seen, the CFAR method with the optimal window misses two ships in the jamming area A and one ship in the jamming area B,whereas, the S-LGGD method finds allshipssuccessfully in both test areas of concern,which means that the proposed detector has an adequate level of immunity to adjacent-target interference.

Strong noise background situation is always a challenge formost detectors,since ships will be mixed with the ocean clutters due to strong backscattering echo of them.To test this situation,an ALOSHH polarizedL-band SAR image(307 $\times 3 1 7$ pixels, $1 0 \mathrm { m }$ pixel size) is adopted in this paper. Figure 4 shows the detection results.As can be seen, the hidden shipcanbe detected perfectlybybothof the CFARmethod and the S-LGGD method except for one false alarm caused bythe latter.However,it shouldbe acceptable fora detector in pursuit of speed and automation,since false alarms arealways inevitable for all the existing detectorsin such situation.

![](images/91b3a8bde267a127fc4a46d4492a7d43eb005b907748d871fc54d74149f215d5.jpg)  
Fig.3Shipdeteconforoselyseparatedtargetsitation.aOriginalSARimage;CARresultofareaA;S-LGGresultofareaA;dCFAR result of area B;e S-LGGD result of area B.

The statistical resultsofFigs.2and3obtained by the two methods are separately listed in Tables 4 and 5.Four statistical parameters are used to analyze the detection results,and figure-of-merit (FoM) [14]is used to assess the detection rate.The higher values of FoM mean higher detection rate and lowerfalsealarmrate.Itcanbedefinedas follows:

$$
F _ { o M } = \frac { N _ { n } } { \left( N _ { f a } + N _ { g t } \right) } ,
$$

![](images/2d6f5cc301a0e1d4275031bcde5d445f379876293ac4be084b1366b9355d3bff.jpg)  
Fig.4 Ship detection for strong noise situation.a Original SAR image; b CFAR result; c S-LGGD result

Table 4 Statistical result of SAR imagery 1   

<html><body><table><tr><td></td><td>Missed number</td><td>Detected number</td><td>False alarm number</td><td>FoM</td></tr><tr><td>Two-parameter CFAR method</td><td>2</td><td>47</td><td>4</td><td>0.922</td></tr><tr><td>The proposed S-LGGD method</td><td>0</td><td>49</td><td>1</td><td>0.980</td></tr></table></body></html>

Table 5 Statistical result of SAR imagery 2   

<html><body><table><tr><td></td><td></td><td>Missed number</td><td>Detected number</td><td>False alarm number</td><td>FoM</td></tr><tr><td rowspan="2">Area A</td><td>Two-parameter CFAR method</td><td>2</td><td>22</td><td>0</td><td>0.916</td></tr><tr><td>The proposed S-LGGD method</td><td>0</td><td>24</td><td>0</td><td>1.00</td></tr><tr><td rowspan="2">Area B</td><td>Two-parameter CFAR method</td><td>1</td><td>15</td><td>0</td><td>0.938</td></tr><tr><td>The proposed S-LGGD method</td><td>0</td><td>16</td><td>0</td><td>1.00</td></tr></table></body></html>

where $N _ { t t }$ counts the accurate detected ship number, and $N _ { f a }$ counts the false alarm number, $N _ { g t }$ counts the real ship target number.

# 3.2 Speed test

The speed testwas performed on an SAR strip image acquired byaKu-bandairborne SARsystem,whichhasaswath width of 8,192 pixels and a resolution of $1 . 5 \mathrm { m } \times 1 . 5 \mathrm { m }$ for both range and azimuth direction.The computer on which the detection is implemented,configured with an Intel Core 2 Quad CPU running at $2 . 5 3 \mathrm { G H z }$ ,is a general purpose computer. The tested data processing rate is near 15.6Mbps for the CFAR method, but reaches approximately 38 Mbps for our S-LGGD method. Compared with some well-known spaceborne SAR missions,itis roughly four times faster than the designed data downlink rate（1OMbps） for high-resolution radarimaging ofNASA's planetary imaging radarmissions [15] and near the real-time data processing rate of 45 Mbps for the SIR-C/X-SAR mission[16].

In fact,a lower data downlink rate,compared with spaceborne SAR systems,is universal forairborne SAR systems. In addition,down-sampling of the downlink image is also the universal preprocessing for real-time full-screen monitoring in practical engineering application. Taking four to one sampling ratio into account,the equivalent processing rate for the S-LGGD detector can be improved to 150 Mbps,which is enough to meet the needs of the real-time ship detection for mostairborne SAR systems,even for some space-borne SAR systems if some special purpose processors are available.

# 4 Conclusions

A linear LGGD algorithm for ship detection from SAR imagery is proposed in this paper, and the algorithm uses the local gray-level gathering characteristics of SAR imagery to characterize its spatial intensity distribution,independent of anypriorknowledge about ships and background observation hence is able to execute automatic ship detection.Based on this,a fast and effective detector for ship targets,S-LGGD for short, has been developed. The scheme is easy to implement and particularly well suited for a fast stream processing of SAR images,which suggests that it has the ability to support the real-time ship detection applications.

The S-LGGD detector has been tested on both air- and space-borne SAR images.Due to its sensitiveness to the intensity difference,the S-LGGD method has strong differentiation ability for the target edge.When the detection window size is larger than 3O pixels,its detection performance is robust for the most situations and has little dependence on the sliding window size,since the result is always stable.The performance test has shown that the detector can highlight the cells with unusual gray-level in sliding window and hence is sensitive to ship targets,even to some faint targets.Also, the detectoris immune to the adjacent-target interference in SAR imagery thus is particularly suitable for the multiple targets situation.The speed test demonstrates that the detectionrate of the S-LGGD detector can meet the needs of any real-time SAR systems with a data downlink rate under 38Mbps (or 150 Mbps for 4-1 sampling ratio processing mode).However,the detection performance of the proposed detector is decreased with the increasing image noise and heterogeneity thus the detector still needs a further improvement for wide applications,especially for some strong noise or heterogeneous situations.

AcknowledgmentsThis work was supported by a grant from the National High Technology Research and Development Program of China (No.2008AA121805-1) and the National Science Foundation of China (No. 61101201).

# References

1．Yeremy,M.,Campbell, J.W.M.,Mattar,K.,Potter, T.: Ocean surveillance with polarimetric SAR.Can.J.Remote Sens.27(4),328- 344(2001)   
2.Eldhuset,K.:An automatic ship and ship wake detection system for spaceborne SAR images in coastal regions.IEEE Trans.Geosci. Remote Sens.34(4),1010-1019 (1996)   
3．Cusano,M.,Lichtenegger,J.,Lombardo,P.,Petrocchi,A., Zanovello,D.: A real time operational scheme for ship trafic monitoring using quick look ERS SAR images.In: Proceedings of the IGARSS, Sapienza,Italy 24-28 July,2000,pp.2918-2920 4.Lemoine,G.,Chesworth,J.,Schwartz-Juste,G.,Kourti,N., Shepherd,I.: Near real time vessel detection using spaceborne SAR imagery in support of fisheries monitoring and control operations. In: Proceedings of the IGARSS,Anchorage, USA, 20-24 Sept, 2004,pp.4825-4828   
5.Liu T.,Lampropoulos G.: A new polarimetric CFAR ship detection system.In: Proceedings of the IGARSS,Denver, USA,July 31- Aug.4,2006,pp.137-140   
6.Huang, S.Q.,Liu,D.Z., Gao, G.Q., Guo,X.J.: A novel method for speckle noise reduction and ship target detection in SAR images. Pattern Recognit. 42(7),1533-1542 (2009)   
7.Gao,G.,Liu,L.,Zhao,L.J.,Kuang,G.,Shi,G.: An adaptive and fast CFAR algorithm based on automatic censoring for target detection in high-resolution SAR images.IEEE Trans.Geosci.Remote Sens. 47(6),1685-1697 (2009)   
8．Yu,Y.,Ding,Z.H.,Wang,B.,Zhang,L.M.: Visual attention-based ship detection in SAR images.Adv. Neural Netw.Res. Appl. 67(4), 283-292 (2010)   
9.Greenspan,M.,Pham L.,Tardella,N.: Development and evaluation ofa real time SAR ATR system.In:Proceedingsof the IEEERadar Conference,Dallas,Texas,USA,11-14 May,1998,pp.31-43   
10．Novak,L.M.,Halversen, S.D., Owirka, G.J.,Hiett,M.: Effect of polarization and resolution on SAR ATR. IEEE Trans. Aerosp. Elecron. Syst.33(1),102-116 (1997)   
11.Duman,K.,Eryildirim,A., Cetin,A.E.: Target detection and classification in SAR images using region covariance and co-difference. Proceedings of the SPIE DSS Conference,vol.7337,Orlando, Florida,USA,13-17 April,2009   
12.Duman,K.,Cetin,A.E.: Target detection in SAR images using codifference and directional filters.Proceedings of the SPIE DSS Conference,vol.7699,Orlando,Florida,USA,5-9 April,2010   
13.Zoheir,H.,Faouzi, S.: Distributed IVI-CFAR detection in nonhomogeneous environments. Signal Process.84(7),1231-1237 (2004)   
14. Ji,Y.G.,Zhang,J.,Meng, J.M.,Zhang,X.: A new CFAR ship target detection method in SAR imagery. Acta Oceanol. Sin.29(1),12-16 (2010)   
15.Lou,Y.,Hensley,S.,Le,C.,Moller,D.: On-board processor for direct distribution of change detection data products.In:Proceedings of theIEEERadar Conference,Philadelphia,PA,USA,26-29April, 2004,pp.33-37   
16.Guo,H.: Spaceborne and airborne SAR for target detection and flood monitoring.Photogramm.Eng Remote Sens.66(5),611-617 (2000)