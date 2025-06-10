# 光纤式IFU检测系统自动化功能的设计

王亮喆1,2，王咸奇，钟悦1，常亮1,2,4

（1．中国科学院云南天文台，云南 昆明650216；2．中国科学院大学，北京100049;3．艾伯哈特-卡尔斯-图宾根大学，图宾根 72076；4.云南省应用天文技术工程实验室，云南 昆明 650216)

摘要：对中国科学院云南天文台现有的光纤式IFU集成化检测系统进行改进，实现了该系统的可视化和自动化检测功能。根据检测流程,通过一键式操作完成光学元件自动切换、成像系统连续离焦控制、自动化数据采集及数据处理等，可一次性检测出光纤阵列排布精度、微透镜阵列排布精度、光纤焦比退化、光纤透过率等基本参数，增加了计算广狭缝端每根光纤沿光轴方向排布精度的功能，并在实验室验证了自动化系统的性能。该系统实现全自动化后，可将原来需要数周的检测时间缩短至一天之内，极大地提高了工作效率，有利于促进国内光纤积分视场单元制作和测试工艺的发展。

关键词：检测系统；光纤阵列；光纤检测；自动化中图分类号：TP273 文献标识码：A 文章编号:

# 1引言

积分视场光谱仪IFS（Integral Field Spectroscopy）可以同时获取面源天体的空间和光谱信息而被广泛应用于天文观测，并且已经成为国际上大中型口径光学望远镜配备的常规观测设备[]。积分视场单元IFU（Integral Field Unit）是 IFS 的核心部件，其主要功能是对面源进行视场切割。光纤阵列切割是IFU中最主要且应用最广泛的视场切割方式。根据科学目标不同，IFS 所要求的空间分辨率和光谱分辨率也不同，因此对于IFU 的工艺要求及性能要求也不同。对于光纤式IFU，光纤阵列排布精度会影响面源天体的视场切割精度；微透镜阵列与光纤阵列的共轴精度会影响光纤出射光斑质量和光纤透过率；广狭缝端光纤排布精度会影响谱线位置及光谱覆盖范围；广狭缝端光纤沿光轴方向排布精度会影响谱线宽度；每根光纤的透过率直接对面源天体各空间位置的光度产生影响，测量每根光纤透过率有利于获得准确的光度信息；焦比退化会直接影响光谱分辨率和谱线宽度。因此通过实验手段客观评价光纤阵列排布精度以及阵列中每根光纤的性能是IFS 研制过程中的重要环节。

目前光纤式IFU的检测方法主要有两种，其一是光纤数比较少的IFU进行逐根光纤检测；其二是光纤数较多的情况下进行逐根光纤抽样检测。2003年J.Schmoll等人对 PMAS(Potsdam Multi-Aperture Spectrophotometer）上的 $3 2 \ 3 2$ 光纤式IFU 进行了光纤焦比退化检测，采用的方法是利用激光器作为光源，在测试光路中利用CCD 通过离焦方式进行光纤逐根检测，不具备排布精度和透过率等相关参数的检测功能[2]。2006 年Frank Grupp 等人研究了基于 VIRUS(Visible Integral Field Replicable Unit Spectrographs ）/HETEDEX(Hobby-EberlyTelescope Dark Energy Experiment）项目的自动化/半自动化IFU 试验平台并对光纤焦比退化和光纤透过率进行检测。利用 $4 { \times } 4$ 的光纤阵列进行了实验原理验证，其自动化/半自动化方法是采用高精度位移平台及检测光路逐根检测所有光纤的焦比退化及透过率，检测过程中需要手动光纤对准[3]。2008 年 Jeremy D.Murphy等人对 VIRUS-P的光纤式IFU 的透过率和焦比退化进行了检测，其检测方法是利用白光光源通过检测系统检测光纤透过率，分别利用$6 0 0 \mathrm { n m }$ 、 $4 0 0 \mathrm { n m }$ 和 $3 6 5 \mathrm { n m }$ 的单色光源对光纤焦比退化进行逐根检测，不同单色光焦比退化测量结果差异仅为 $\mathrm { F } / 0 . 0 2 \$ ，证明可以用白光进行焦比退化检测[4]。2016年F Sayede 和 YounesY 等人研究检测了WHT（William Herschel Telescope)望远镜的大视场光谱仪WEAVE（WHTEnhanced Area Velocity Explorer）中的光纤式 IFU 以及 MOS(Multi Object Spectrograph)中光纤的焦比退化，他们利用自动化软件控制光源以及利用小型相机移动来逐根检测光纤出射焦比退化，并利用白光和赝狭缝端光纤出射焦比计算出赝狭缝端光纤沿光轴方向的位置精度，其位置精度取决于光纤焦比退化的检测精度[5]。云南天文台丽江2.4米望远镜上的 CHiLI（CHinaLijiangIFU）由美国德克萨斯大学奥斯汀分校为上海天文台研制，出厂时并未提供IFU 的检测报告，而是利用实际观测数据验证了该 IFS 的性能[6.7]。云南天文台FASOT(FiberArray Solar Telescope)项目第一台原理样机由云南天文台与英国杜伦大学共同研制，其中英国杜伦大学 Jeremy Allington-Smith 等人为该系统研制了IFU,该样机于 2013年11月在非洲加蓬共和国观测日全食，获得了日冕绿线的闪耀偏振光谱[8。2012年样机在实验室调试时，为了实现两个光纤阵列偏振态的共空间调节，云南天文台常亮设计了一台装调监视系统，该系统是云南天文台光纤阵列检测系统的雏形。为了实现IFS 的国产化，云南天文台先后联系了哈尔滨工程大学、北京星源奥特科技有限公司和上海昊量光电设备有限公司加工光纤式IFU,这三家单位在研制 IFU 的过程中没有检测手段,不能在加工过程和研制完成后检验 IFU的相关性能，为此从2013开始云南天文台常亮设计研制了用于光纤阵列 IFU 性能检测的实验系统，对哈尔滨工程大学、北京星源奥特科技有限公司和上海昊量光电设备有限公司加工的 IFU 进行性能检测。通过检测过程和结果，这三家公司分别提高了加工工艺，制作了几套满足观测要求的光纤式 IFU用于多台FASOT原理样机的科学观测。到2016年，云南天文台的检测系统可以检测光纤阵列排布精度、赝狭缝端光纤排布精度、微透镜阵列与光纤阵列共轴精度、光纤焦比退化和光纤透过率等参数，但是并没有考虑广狭缝端光纤沿光轴方向排布精度的检测，且光路比较复杂，成像检测和激光检测采用了两套不同的光学系统[9]。基于云南天文台的检测方法，2019 年哈尔滨工程大学蒋航重新设计了检测系统[10]。同年，云南天文台王咸奇和钟悦等人改进了检测装置光路，把成像检测和激光检测进行了集成设计，但是检测过程与数据处理过程完全分离，没有实现自动化[1,11]。

本文对云南天文台光纤式IFU集成化检测系统进行进一步优化，利用Python 实现了该系统的可视化和自动化检测功能，并改进了光纤透过率检测方法，增加了赝狭缝端光纤沿光轴方向排布精度的检测功能，将原来需要数周的检测时间缩短至一天之内。

# 2检测系统自动化设计与实现

# 2.1光纤式IFU集成化检测系统简介

光纤式IFU集成化检测系统主要由光源、平行光管、分束器、成像系统和CCD等5部分组成，实物图如图1所示。图中M1和M2为平面反射镜，B1和B2为遮光板，BS 为分束器，M2、B1、B2、待测光纤阵列端和待测光纤赝狭缝端安装在高精度电动位移平台上。该系统的光源采用卤素灯加积分球的形式，并用稳压电源保证光源辐射强度的稳定性。根据设计要求，针对无微透镜阵列耦合的 ${ 5 0 } \mu \mathrm { m }$ 芯径光纤（光纤中心间距 $1 2 5 \mu \mathrm { m }$ ），在CCD上的成像大于等于5个像素；根据探测器参数（采用 PikeF-505BCCD作为探测器，像素尺寸为 $3 . 4 5 \mu \mathrm { m } \times 3 . 4 5 \mu \mathrm { m }$ ，靶面大小为 $2 4 5 2 \times 2 0 5 4$ ）进行设计，其成像系统主要参数如表1所示。该系统可一次性检测 $1 6 0 \times 1 6 0$ 光纤阵列端光纤排布精度，160 根光纤赝狭缝端排布精度及光纤性能基本参数。

![](images/8cd4e104ced4f3d76be8807adbdc383ca74d683ff22180bd93069a48aa7e6ad5.jpg)  
图1光纤式IFU集成化检测系统实物图  
Fig.1PictureoffiberIFUIntegratedTestSyste

# 表1光学系统设计参数

Tab.1 The parameters of optical system   

<html><body><table><tr><td>F/#</td><td>FOV（object height）</td><td>Wave length</td><td>Magnification</td><td>Effective focal length</td><td>Back focal length</td></tr><tr><td>3.45</td><td>20mm</td><td>380-700nm</td><td>0.345</td><td>207.32mm</td><td>102.62mm</td></tr></table></body></html>

# 2.2自动化系统设计

自动化控制需要根据检测流程及检测方法进行设计，图2为检测步骤光路图。第一步，把B1和B2移进光路拍摄系统背景光场；移出B1拍摄广狭缝端背景光场；移入B1移出B2 拍摄阵列端背景光场。第二步，移出B1和B2，这时在CCD上会同时获得光纤阵列端和赝狭缝端光纤图像，这时需要扣除背景，保存扣除背景后的图像。第三步，把M2 移入光路，拍摄含有赝狭缝端背景光场的入射光场，并扣除赝狭缝端背景光场，得到入射光纤阵列之前的光强分布。第四步，移出M2，控制广狭缝端使其沿光轴方向移动，拍摄多幅不同离焦位置图像（焦面前后离焦），由于赝狭缝端的移动会造成赝狭缝端背景光场变化，因此每拍摄一幅离焦像后需要再次移入B2，拍摄当时的應狭缝端背景光场并扣除，多次重复B2的移入移出操作。通过前四步，可以获得所需要的全部图像，从下一步开始进行数据处理。

![](images/a2b1bb2f7ed57a11ec6c91b6682f4c40113f5c85aa8e638393b9327bb4fb8f17.jpg)  
图2检测步骤光路图  
Fig.2 Sketchmap of Optical Testing System

数据处理过程分成两个部分，第一部分是排布精度和透过率的检测，排布精度包括赝狭缝端光纤位置精度和阵列端光纤位置精度。阵列端如有微透镜阵列耦合，通过调焦拍摄微透镜阵列图像，计算每个微透镜的中心位置，并与光纤阵列中每根光纤的中心位置进行比较，计算出微透镜阵列与光纤阵列耦合的共轴精度。光纤或微透镜中心位置计算采用传统的二值化图像处理方式，对中心位置进行直线拟合即可得到排布精度。每根光纤的透过率可以用公式（1）计算得到。

$$
\begin{array} { r } { T = \frac { I _ { o u t } } { I _ { i n } } \times 1 0 0 \% } \end{array}
$$

上式中 $T$ 为每根光纤透过率， $I _ { i n }$ 为光纤阵列端入射光强，可以通过上述检测步骤第二步和第三步获得。这里需要确定每根光纤在CCD上的对应像素范围，并扣出入射光强分布对应于光纤的像素范围即可得到每根光纤对应的入射光强； $I _ { o u t }$ 为赝狭缝端光纤出射光强，可以通过上述检测步骤第二步获得。

第二部分是广狭缝端光纤出射焦比和广狭缝端光纤沿光轴方向排布精度的检测。光纤具有焦比退化的特性，光纤的出射焦比会小于入射焦比，图3上下分别为赝狭缝端光纤像及其离焦像。

![](images/7ae7358172fb891c4f0677cb64e063b39262e61f65999b3b49fdd3a2e102d5ad.jpg)  
图3光纤赝狭缝端图像  
Fig.3 Image of Pseudo slit

赝狭缝端光纤出射焦比可以通过公式（2）得到[5]，

$$
\begin{array} { r } { F / \# = \frac { \Delta l ^ { \dot { \prime } } } { \Delta D ^ { \dot { \prime } } } } \end{array}
$$

上式中 $F _ { \prime }$ /#为出射焦比， $\Delta l$ 为像端位移变化量， $\Delta D$ 为光纤像斑直径变化量。我们检测出射焦比的方法是采用固定CCD位置，移动赝狭缝端位置（成像系统物端）获得，需要通过轴向放大率公式推导出物端位移变化量 $\varDelta l$ 与 $\varDelta l$ 之间的关系@并带入公式（2）中得到 $F ,$ /#与 $\varDelta$ l的关系式：

$$
\begin{array} { r } { F / \# = \frac { \Delta l \cdot \beta _ { 1 } \beta _ { 2 } } { \Delta D ^ { ' } } } \end{array}
$$

上式中 $\beta _ { I }$ 是物端位移4I时的垂轴放大率， $\beta _ { 2 }$ 是在物面时的垂轴放大率，即成像系统放大率。根据高斯公式和放大率公式[6]可以获得 $\boldsymbol { \beta } _ { I }$ 与 $\boldsymbol { \beta } _ { 2 }$ 的关系式：

$$
\begin{array} { r } { \beta _ { 1 } = \beta _ { 2 } + \frac { \Delta l \cdot { \beta _ { 2 } } ^ { 2 } } { f ^ { \prime } } } \end{array}
$$

上式中 $f$ 为成像系统焦距。把公式（4）代入公式（3）中可以得到出射焦比公式，如下：

$$
\begin{array} { r } { F / \# = \frac { \Delta l { \beta _ { 2 } } ^ { 2 } } { \Delta D } + \frac { \Delta l ^ { 2 } { \beta _ { 2 } } ^ { 3 } } { f ^ { \prime } \Delta D ^ { ' } } } \end{array}
$$

赝狭缝端光纤沿光轴方向排布精度的检测放到第二部分的原因是可以利用公式（5）的拟合结果得到每根光纤光斑的半值全宽轮廓，可计算最小半宽对应的位置信息，从而得到赝狭缝端光纤沿光轴方向排布精度。

根据上述的操作步骤和检测方法，设计了该系统的自动化控制软件，控制系统流程图如图4所示。

# 2.3程序可视化实现

为了操作方便，设计了程序可视化界面，分为自动操作和手动操作界面。在手动操作界面中可以根据实际情况设定位移平台位置参数、位移步数参数、相机控制参数和数据保存路径参数等，设定完相关参数后。通过自动操作界面可一键式实现全自动化检测功能。图5为软件控制界面，点击"输出参数"按钮可列出检测的主要参数项，点击相应的参数项可在软件界面右侧显示最终检测结果。

![](images/0a81f418feb476ad6965efbfbbdb8ed6508c3219c8b0cd01beb0237453409ecf.jpg)  
图4控制系统流程图  
Fig.4Flow ChartofControlSystem

![](images/d13780a22312d28273ce792d1b9e1ab4b7acf0264671ea345cc9eb22184109bd.jpg)  
图5软件控制界面

# 3.自动化系统性能评估

为了确保检测结果的可靠性，在检测之前需要做相应的系统定标工作，主要包括系统放大率检测、位移平台移动精度定标和光源强度稳定性定标。其中，系统放大率检测结果和位移平台移动精度影响焦比退化的计算精度，光源强度稳定性影响光纤透过率的计算精度。

我们利用目前实验室现有的某单位最早加工的一个不合格产品进行了自动化系统的性能评估（其他合格产品已经安装到望远镜上进行科学观测）。该产品为 $2 0 \times 2 0$ 微透镜耦合的光纤阵列，每根光纤芯径为 ${ 5 0 } \mu \mathrm { m }$ ，数值孔径0.22，每个微透镜边长为 $3 0 0 \mu \mathrm { m }$ ，光纤入射焦比为5.473。微透镜在胶合时部分损坏，部分光纤损坏，光纤排布精度和透过率均不满足观测要求，但是不影响自动化系统的性能评估，图6为该产品阵列端成像，图中左边为 IFU示意图，为一个光纤阵列两个赝狭缝系统，中间为微透镜阵列像，右边为光纤阵列像。

![](images/22e6e685b2269f00f485c6ae2cb58bd5b2a251261cecc040c1ed23a80250aac1.jpg)  
Fig.5 Interface of Software control   
图6阵列端成像  
Fig. 6 Image of Fiber Array

# 3.1系统定标

在安装调试控制系统后需要重新对成像系统放大率定标。系统放大率的检测方法是通过沿垂轴方向移动應狭缝端光纤，分别获得物像的位置信息计算成像系统放大率。图7展示了广狭缝端单根光纤不同步长移动不同步数时获得的系统放大率。在放大率检测过程中统计了广狭缝端所有光纤移动不同步数和不同的位置信息，计算出系统放大率的RMS值为0.326，与参考文献[1]中利用分辨率板计算放大率的结果一致。

电动位移平台位移精度的定标方法与检测放大率方法类似，是利用光纤中心位置在相同移动步数下距离变化计算得到。图9为應狭缝端单根光纤不同步长移动不同步数时获得的平台位移精度。在位移精度定标程中统计了赝狭缝端视场内的所有光纤移动不同步数和不同位置信息，计算出位移精度的RMS 值为 $1 . 3 5 \mu \mathrm { m }$ ，与厂家提供的 $2 \mu \mathrm { m }$ 最小分辨率吻合。

![](images/a44095c75f664fca53cabc354316fe301456950b5099f75d05007ae3e3f8fe27.jpg)  
图7单根光纤移动不同位置时的系统放大率

![](images/fec1f5f52d61457329d912a63046b4f29f1267eab3f251d5dfdedfb20554739b.jpg)  
  
图8单根光纤移动不同位置时的位移精度  
Fig.8Displacement of Image System byMoving Single Fiber

光源强度稳定性的定标方法是先将光源打开稳定2小时后再持续1.6小时做光强稳定性分析，光纤透过率计算可以在3分钟内完成，1.6小时光强监测满足光纤透过率要求。图9为光强度稳定性测试结果，其RMS 值为 $0 . 4 \%$ 。

![](images/464520bb85ac0b9df09f81ce761761d27d71ca35d38d8cbd3a6d258fd9844b40.jpg)  
Fig.7Magnification of Image System by Moving Single Fiber   
图9光源光强稳定性  
Fig.9Light Source Stability

# 3.2 算法应用

本文只介绍微透镜阵列与光纤阵列耦合的共轴精度和广狭缝端光纤沿光轴方向排布精度的检测结果，该产品的这两个参数之前没有做过检测。图10为阵列端微透镜和光纤在CCD上中心位置坐标，其中红色圆点为光纤位置，黑色圆点为微透镜位置。图11所示为微透镜阵列与光纤阵列每根光纤对应耦合的共轴精度偏差，上图为X方向偏差，下图为Y方向偏差。按照共轴精度 $\pm 1 0 \mu \mathrm { m }$ 光纤数量合格率为 $90 \%$ 的工艺要求加上损坏的光纤，检测的共轴精度合格率为 $7 5 \%$

![](images/2e9c1bdb0c7e7cbbb5a84409216305b2295e2d8873a4d335af422a666602a9c5.jpg)  
CoordinatesofLensletsandFibers   
图10 微透镜阵列与光纤阵列坐标

![](images/ba98f98be666a87807f0ed82de0b673fc35289ef12d2d4c5314711bfc72d02c0.jpg)  
Fig.10 Coordinates of Lens and Fibers   
图11微透镜阵列与光纤阵列耦合的共轴精度

广狭缝端光纤沿光轴方向排布精度检测是本次改进新增的功能，其位置结果对于光纤焦比退化产生的原因起到辅助分析作用。图12为两个應狭缝中一个的数据分析结果，上图为每根光纤成清晰像时的实际位置，蓝色直线为数据拟合直线；下图为赝狭缝端光纤沿光轴方向的排布精度。

![](images/73a6c503db1240f19edfefba7e7d1327c2bae7fc7475ec28bbc3bc26e082c37f.jpg)  
Fig.11 Accuracy of Optical Axis between Fiber Array and Lenslet Array   
图12广狭缝端光纤沿光轴方向排布精度  
Fig.12Accuracy ofFiberPositionalong Optical Axis

# 4.总结与展望

完成云南天文台光纤式IFU集成化检测装置自动化控制系统的设计与实现工作，这里只讨论算法与控制方面的不足，包括：1）对于位移平台的离焦控制及图像拍摄过程所花费的时间最多，需要进一步优化。目前拍摄不同位置离焦像次数进行焦比退化计算过程中，离焦像位置图像拍摄数量较多，不是最优化图像数量，需要进一步优化提高工作效率；2）目前程序中只考虑了常见的圆形/正方形/六边形微透镜阵列在计算光纤效率时的算法（与清晰度有关），其他形状的微透镜在计算光纤效率时并未考虑。目前对于透过率的检测仅适用于阵列端有微透镜且为六边形密堆积排布或者方形的光纤阵列等，主要原因在于非密堆积排列阵列之间会出现缝隙，这对于模板的制作存在困难，难以准确确定入射光范围，且此部分误差难以衡量，因此透过率检测结果与之前利用激光的检测结果相差较大，还需要在算法与操作流程方面进一步分析原因；3）在确定焦面位置时需要人工干预，目前该系统不具备自动调焦功能；4）光纤阵列与微透镜阵列耦合后的涂胶均匀性并没有利用算法进行评价，涂胶均匀性会影响光纤透过率。目前国际上没有标准评价方法，但是可以利用成像的办法计算像斑的真实轮廓，对于评估引起光纤透过率的变化起到辅助分析的作用；5）目前算法只适用于视场范围内的光纤阵列，对于更大的光纤阵列的检测需要自动控制位移平台进行扫描并定位，软件中没有扫描定位功能，目前对于较大光纤阵列的检测需要进行手动干预。

对于上面提到的问题，未来工作重点应放在检测结果的准确性、检测设备的通用性，并进一步增加检测功能，为研制精度更高的IFS 提供技术支持与保证。

# 参考文献

[1]王咸奇.积分视场单元(IFU)光纤阵列排布及光纤性能集成化检测系统研制[D].中国科学院大学,2019. WANGXQ.DevelopmentofIntegratedTest System forFiber ArryandFiber Performanceof IFU[D]. Universityof Chinese   
Academy of Sciences,2019   
[2]J.Schmol,M.M.Roth,U.Laux.Statistical TestofOptical Fibers for Use inPMAS,thePotsdam Multi-Aperture   
Spectrophotometer[J].Publications of the Astronomical Society of the Pacific,20o3,115(809):854-868.   
[3]GruppF.Measuring theproperties ofopticalfibers:Firstresults fromtheAIPfiber testbench forfiberbundle IFUs[J].New   
Astronomy Reviews,2006,50(4/5):323-325.   
[4]MurpyJD,MacqueenPJ,HilGJetal.FocalratiodegradationandtransmissioninVUS-opticalfibers[J].Procedingsof   
SPIE - The International Society for Optical Engineering,2Oo8,7018.   
[5]FSayede,Younes Y,FasolaG,etal.Firstresultsof testsontheWEAVEfibres[C].//SPIEAstronomicalTelescopes $^ +$   
Instrumentation.Advances inOpticaland Mechanical Technologies forTelescopes and Instrumentation II,2016.   
[6]郁道银，谈恒英．工程光学[M].北京:机械工业出版社,2015:21-35. YUDY,TANHY.Engineering Optics[M].Beijing: China Machine PRESS,2015:21-35.   
[7]刘辰旭，郝蕾．中国丽江积分视场光谱仪[J].科学,2016(68):4-7. LIU C X,HAO L. China Lijiang IFU[J]. Science,2016(68):4-7.   
[8]李欢,郝蕾．中国丽江积分视场光纤光谱仪分辨能力实验室测试结果[J].天文学进展,2017,02(v.35):109-120. LIH,HAOL.The TestResultsofSpectral ResolutionofChinaLijiang IntegralFieldUnit[J].Progress in Astronomy.2017,   
02(v.35):109-120.   
[9]QuZQ,DunGChangL,etalpectro-ImagingPolarimetryoftheLocalCoronaDurigSolarEclipse[J].SolarPysics,7,   
292(2):37.   
[10] 常亮,敦广涛,程向明．积分视场光纤光谱仪光纤排布检测系统及其检测方法.ZL201610824209.9[P].2016-09-14. CHANGL,DUNGT,CHENGXM.Test Systemand Methods forFiber Arryof IFS.ZL201610824209.9[P].2016-09-14.   
[11]蒋航.阵列光纤定位方法及检测[D].哈尔滨工程大学,2019. JIANGH.Research onArrayOptical FiberLocalization and Detection Methods[D].Harbin Engineering University,2019.   
[12] 王咸奇,许良,常亮．一种用于积分视场光纤光谱仪光纤性能的集成化检测装置.ZL201821344181.X[P].2018-08-20. WANG X Q,XUL,CHANG L,An Integrated Test System for IFS. ZL201821344181.X[P].2018-08-20.

# Automated Design of Test System for Fiber Array IFU

Wang Liangzhe1.2, Wang Xianqi³, Zhong Yuel, Chang Liang1.2.4 .Yunnan Observatories,Chinese Academyof Science,Kunming 650216,China,Email: changliang@ynao.ac.(

2. University of Chinese Academy of Sciences,Beijing 10oo49, China

3.Eberhard Karls University of Tübingen,Tübingen 72076,Germany

4.Astronomical Technology & Engineering Laboratory of Yunnan, Kunming 650216,China

Abstract: To improve the test system for fiber array IFU of Yunnan Observatories,a visualized and automated function base on Python was developed. According to testing process, it can accomplish optical components switching，continuous defocus control of imaging system, automated acquiring and processing data and so on by one-touch operation，and it can test accuracy for position of fiber array, position of lenslet array,FRD of fiber and transmittance of fiber.A function has been added for testing accuracy of fiber position along optical axis at pseudo slit,and was verified the automated function in the lab.After update,it can shorten the testing time from several weeks to one day, which greatly improves the working efficiency and it also can promote the development of fiber array processing technology in China.

Keywords: Test System; Fiber Array; Fiber testing; Automation