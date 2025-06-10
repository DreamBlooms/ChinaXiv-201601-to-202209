# 技术方法

# 面向B超图像分割的动态权重因子水平集方法

杨 谊1,喻德旷²,申 洪³,刘民锋4  
南方医科大学'生物医学工程学院信息技术系，生物医学工程学院信息技术系电子技术系，基础医学院病理  
系，南方医院乳腺外科，广东广州510515

摘要：目的 研究和改进水平集方法，实现B超图像中病灶区域的准确快速分割。方法 分析已有水平集方法在B超图像处理中的局限,基于区域水平集的优点,将信息论中的熵引人图像处理，定义动态权重因子，准确反映局部灰度阶梯变化状况，定量度量轮廓线像素点分别受到趋向目标、背景区域的两种作用力的动态权重，将其融合到区域水平集中,迭代引导曲线形变和位移。由于B超图像病灶分割属于指定区域的局部分割，所以将计算约束到局部范围，从而明显降低运算代价。结果动态权重因子水平集方法能够较好分割B超图像中的病灶区域，与几种主流水平集方法相比，本文方法精度更高,时间复杂度更小。结论动态权重因子方法能够更合理准确地判断病灶边界像素点，局部计算策略有效地提高了分割效率。

关键词：水平集方法；动态权重因子；图像熵；B超图像边界提取

# Level set method reconciled with a dynamic weighting factor for B-mode ultrasound image segmentation

YANGYi’,YUDekuang,SHENHong,LIUMinfeng4   
Departmentoffaiopmntofeoololoeicalnertet ScholofBsicicie，othdicaletagoin;parentftgeryf Southern Medical University, Guangzhou 510515,China

Abstract: Objective To modifythelevel set method for precise and fast segmentation of B-type ultrasound image lesions. Methods Based on the bestof region level set method,entropy in the information theory was introduced into image procesing todefineadynamic weighting factor that responded tothe gradientchange ofthelocal graylevels toevaluate the dynamic degree of driven force on each pixelon the contour to the target and background areas.The dynamic weighting factors were reconciled intotheregional level setmodel andledthecontour todeformandmoveduring the iterations.As lesionsegmentation wasclasifiedaslocal segmentationofaspecificarea,thecalculation wasrestrained tothelocal sphere abide by thecontour, which greatly reduced the calculation complex. Results Experiments on B-type ultrasound images showed improved results of the proposed method with a beter accracy and less time consumption compared with several current levelset methods.ConclusionLevelset method reconciled with dynamic weighting factorallowsabeter evaluationof the lesion contour pixels, and the local calculation strategy results in an enhanced segmentation efficiency.

Key words: level set method; dynamic weighting factor;image entropy; B-modeultrasound image extraction

B型超声对液体与实质性组织表现出显著的图像差别，在发现肿物、畸形、结石等引致局部结构明显形态改变的疾病方面有着明显优势，无创方便廉价实时等优点使得它在体检和医疗诊治中的应用十分广泛[。由于成像原理和过程中的多种因素影响，B超图像常表现出对比度较低、噪声干扰严重、边界模糊等缺点，自动分割在B超中的应用具有较大局限性。人们从多种角度采用多种方法进行B超图像的自动分割探索，如区域增长法、动态阈值分割法、模糊聚类法、分水岭法、HMM融合法、EM算法和高斯混合分布模型、小波变换法等，现有解决方案尚存在较大的改进空间。基于变分的水平集方法是近年来发展迅速的一个分支，它将图像分割问题表达为能量函数的最小化问题，由变分原理将其转化为偏微分方程的求解[1-2]。相比于传统的区域分割方法，水平集方法允许在能量函数中加人与图像内容有关的约束条件等综合信息，获得更加准确和合理的分割效果。

水平集方法的主要思想是将移动的界面作为零水平集嵌入高一维的水平集函数中，由封闭超曲面零水平集的演化方程得到水平集函数的演化方程，通过水平集函数曲面的演化来隐含地求解轮廓曲线。水平集方法可分为全局水平集、边界水平集和区域水平集三类。

以CV模型3为代表的全局水平集模型利用图像的全局灰度信息驱动曲线形变和移动，主要优点是当两种区域的灰度差别较大时具有较强的抗噪能力，能够有效分割出模糊边缘；对初始轮廓线位置不敏感；经理论证明能够收敛到全局最优。但是，它以图像灰度分布均匀、前景背景有明显差异为前提条件，不能直接用于B超图像的病灶分割。以GAC模型为代表的边界模型利用目标边界的梯度变化信息引导曲线运行，优点是曲线在平滑区域演化很快，而在目标边界处停正运动，在低噪图像中分割准确且运算代价小，但在高噪情况下容易受到噪声干扰而使曲线停顿在错误的位置上。以RSF模型4为代表的区域水平集模型利用曲线内外部局部区域的拟合能量信息促使曲线形变，能够较好地处理灰度不匀的情况，但运算代价比全局和局部模型显著增加，使用的核函数的方差为定值，容易陷入局部极值解。近年来围绕RSF模型的改进主要分为两个方向：核函数的选择，如用其他函数(均值、方差)来代替高斯分布函数5；融合其他方法，如文献[6-7向RSF模型中加入了模糊聚类方法，在一定程度上提高了像素点的判断精度，文献[7还提出了快速计算方案，但对复杂图像仍存在模糊度选取问题，可能造成过分割或欠分割。文献[8-10]融合了CV和RSF模型，可利用两者的优点,但双模型的计算量显著增加。

本文针对B超图像特点，利用区域水平集模型的优点，定义反映曲线像素点受到目标和背景两个区域动态权重的因子，通过概率分布估计模型计算像素点被动态权重的程度，以此为依据对像素点进行区域划分，以提高水平集曲线抗干扰能力和定位模糊边界能力；同时本文将B超图像目标分割看作对感兴趣目标区域的局部分割，将水平集的计算求解约束到局部分割范围，减少计算量，实现特定目标区域的高效提取。

# 1动态权重因子的定义和融入区域水平集模型

设 ${ \mathrm { C } } = \{ \ C _ { i n }$ ， $C _ { o u t } \mathrm { . }$ 是图像I关于轮廓线 $C$ 的两个划分， $C _ { i n }$ 代表轮廓线内部即目标区域， $C _ { o u t }$ 代表轮廓线外部即背景区域，RSF模型的能量函数定义为：

$$
E _ { _ { R S F } } ( C , f _ { 1 } ( x ) , f _ { 2 } ( x ) ) = \sum _ { i = 1 } ^ { 2 } \lambda _ { i } \int _ { \Omega _ { i } } K ( x - y ) \big | I ( y ) - f _ { i } ( x ) \big | ^ { 2 } d y , i = 1 , 2
$$

其中， $\Omega _ { 1 }$ 和 $\vert \Omega _ { 2 }$ 分别为轮廓线内部和外部区域， $K$ 为核函数，一般选择为高斯函数， $f _ { 1 } ( x )$ 和 $f _ { 2 } ( x )$ 为像素点 $\boldsymbol { x }$ 处的拟合值， $\lambda _ { 1 }$ 和λ为常系数。

分析图像，在目标内部和背景内部，局部灰度分布一般是均匀的，而在目标与背景的交界处，局部灰度分布的差异性较为显著。因此，某个区域内部的灰度分布越均衡，则越应当作为一个整体被划分，即对曲线像素点的权重作用越大，曲线最后应当包绕在该区域的边界上；反之，如果某个区域内部的灰度分布不均衡即差异较大，则表明它很可能既包含了目标部分又包含了背景部分，或者带有强噪声点，曲线不应当收拢到该区域的边界上，也就是该区域对像素点的权重作用应当较小。RSF模型中轮廓线内部和外部区域的作用力的权重由常系数λ和λ来规定，一则需要手工指定，依赖经验值，二则不利于动态调整。图像区域灰度分布均衡度常用的度量指标有均值、方差、熵等,其中熵(entropy)作为概率系统的不确定程度指标，当系统越确定时，熵值越小，反之，系统越不确定，熵值越大。在统计学中，熵的玻尔兹曼函数S定义为

$$
S { = } { \boldsymbol { \kappa } } \cdot L n \Omega
$$

其中， $\kappa$ 为(玻尔兹曼)常数， $L n$ 为对数运算符， $\varOmega$ 为系统分子的状态数。

熵的概念同样可以映射到图像灰度分布的均衡性上。图像中一个区域的灰度分布越均匀，则熵值越小，反之，熵值越大。但是，熵是信息论中信息量的度量，直接引入它到图像处理中还有一些不足，因为熵不能反映图像中的几何形状、像素的空间分布等重要的处理信息[912]。本文利用熵的基本含义，对它在图像处理中的定义做了修改：图像的熵表示为图像灰度级集合的比特平均数，描述了图像信源的平均信息量，即图像的信息丰富程度。设 $x ( i , j )$ 为图像的像素点，图像熵对应着图像分布的直方图，近似于采样均值。全局采样均值不能准确反映图像各个部分的像素分布情况和变化情况，所以，本文设计了局部熵，即局部区域采样均值，局部熵的定义为

$$
H ( p ) = - \sum _ { z \in B ( x , \varepsilon ) } p _ { x } ( z ) \cdot \ln p _ { x } ( z ) , p _ { x } ( z ) = { \frac { { \big | } \{ z \in B ( x , \varepsilon ; I ( x ) = z \} { \big | } } { { \big | } B ( x , \varepsilon ) { \big | } } }
$$

其中, $p _ { x } ( z )$ 表示以像素点 $x$ 为中心的半径为的窗口中的灰度级概率密度。局部熵比均值和方差能更有效地反映灰度阶梯变化状况。轮廓线上的像素点 $x$ 受到局部熵的作用，用一个新的因子：动态权重因子来表示。动态权重因子定义为半径为ε的区域的局部熵 $\dot { \boldsymbol A } _ { \varepsilon } ( \boldsymbol I ( \boldsymbol x ) )$

$$
A _ { \varepsilon } ( I ( x ) ) = - \sum _ { i , j \in \Omega _ { \varepsilon } } p ( i , j ) \mathrm { l n } p ( i , j )
$$

其中 $\Omega _ { \iota }$ 为关于像素点 $x$ 的半径为ε的区域 $, i , j$ 为像素点 $x$ 的坐标。

RSF模型的水平集表示为

$$
\mathrm { E } _ { R S F } ( \varphi , f _ { 1 } ( x ) , f _ { 2 } ( x ) ) = \sum _ { i = 1 } ^ { 2 } \int _ { \Omega _ { i } } K ( x - y ) \Big | I ( y ) - f _ { i } ( x ) \Big | ^ { 2 } M _ { i } ( \varphi ( y ) ) d y , i = 1 , 2
$$

其中 ${ } ^ { ! } M _ { 1 } ( \varphi ) = H ( \varphi ) , M _ { 2 } ( \varphi ) = 1 - H ( \varphi ) , H _ { \varepsilon } ( x ) .$ 为Heaviside函数 $H _ { \varepsilon } ( x ) = \frac { 1 } { 2 } \biggl [ 1 + \frac { 2 } { \pi } \mathrm { a r c t a n } ( \frac { x } { \varepsilon } ) \biggr ] ,$

$$
f _ { i } ( x ) { = } \frac { K ( x ) { * } [ M _ { i } ( \varphi ( x ) ) I ( x ) ] } { K ( x ) { * } M _ { i } ( \varphi ( x ) ) } { } _ { \circ }
$$

将(3)式代入RSF模型能量函数，用高斯函数表示核函数，得到动态权重因子区域水平集模型公式：

$$
\begin{array} { l } { { \displaystyle E _ { A } ( C , f _ { 1 } ( x ) , f _ { 2 } ( x ) ) = \sum _ { k = 1 } ^ { 2 } ( - 1 ) ^ { k + 1 } \int _ { \Omega _ { k } } G _ { \varepsilon } ( x - y ) A _ { \varepsilon } ( I ( x ) ) \big | I ( y ) - f _ { i } ( x ) \big | ^ { 2 } d y } \ ~ } \\ { { \displaystyle ~ = \sum _ { k = 1 } ^ { 2 } ( - 1 ) ^ { k } \int _ { \Omega _ { k } } G _ { \varepsilon } ( x - y ) ( \sum _ { i , j \in \Omega _ { \varepsilon } } p ( i , j ) \ln p ( i , j ) ) \big | I ( y ) - f _ { i } ( x ) \big | ^ { 2 } d y } } \end{array}
$$

其中， ${ \cal G } _ { \varepsilon } ( I ( x ) )$ 为以像素点 $x$ 为中心半径为ε的区域内的高斯分布， $\Omega _ { 1 }$ 和 ${ \mathfrak { Q } } _ { 2 }$ 分别为轮廓线内部和外部的区域。

可以看到，(6式中的两项分别为像素点受到曲线内部和外部区域的动态权重力，方向相反，当二力相等时(6)式能量函数 $E _ { \scriptscriptstyle A }$ 达到最小值，此时水平集停止在目标和背景的边界上，得到分割轮廓线。动态权重因子的作用相当于一个变化的系数，随着轮廓线形变和位移到图像的不同区域，动态调节两项力的大小，促使轮廓线较快地向目标边界移动和形变。

引入水平集表示法，得到动态权重因子水平集演化方程：

$$
\frac { \widehat { \cal O } \varphi } { \widehat { \cal O } t } = \delta ( \varphi ) \Biggl [ \sum _ { k = 1 } ^ { 2 } ( - 1 ) ^ { k } \int _ { \Omega _ { 1 } } G _ { \varepsilon } ( x - y ) ( \intop _ { \Omega _ { \varepsilon } } p ( i , j ) \ln p ( i , j ) ) \big | I ( y ) - f _ { i } ( x ) \big | ^ { 2 } d y \Biggr ]
$$

其中 $\delta _ { \varepsilon } ( \varphi ) = \boldsymbol { H } _ { \varepsilon } ^ { ' } ( x ) = \frac { 1 } { \pi } \frac { \varepsilon } { \varepsilon ^ { 2 } + x ^ { 2 } } \nonumber$ 这样就把图像目标分割问题转化为极小化能量函数(7)的计算。

# 2 计算方法

区域水平集模型将图像中的所有目标分割出来，计算量很大。本文根据B超图像病灶的分割要求，将初始轮廓设为一个接近并包绕B超图像目标的闭合曲线，为简便起见，统一采用手工勾勒包围目标规则图形(矩形、椭圆形或圆形)。为提高计算效率，本文采用局部计算方案，定义基于局部近似符号距离函数，放宽对初始水平集函数的要求，不再要求初始水平集必须是符号距离函数。如果直接对轮廓线上的每个像素点都做对数及求和运算，求解水平集式需要离散化迭代实现求解偏微分方程，计算量很大，因此采用局部计算思路以减少运算量和运算时间。本文采用改进的FTC(Fasttwo-cycle)算法[10-1],在不用求解偏微分方程的基础上近似实现水平集函数的进化，定义局部近似符号距离函数(LASDF)为

$$
\varphi ( x , y ) = \left\{ \begin{array} { c } { d , \frac { \operatorname { E } \hat { \mathbf { \pi } } } { \mathrm { i n } } x \mathcal { H } \hat { y } \vert \sqrt { \frac { 3 \hat { \pi } } { \mathrm { i n } } } \vert \sum _ { m = 1 } ^ { \mathrm { E } \hat { \mathbf { \pi } } } } \\ { \vert , \frac { \operatorname { E } \hat { \mathbf { \pi } } } { \mathrm { i n } } x \mathcal { H } \hat { \mathbf { z } } \vert \hat { \mathbf { z } } \vert \sqrt { \frac { 3 \hat { \pi } } { \mathrm { i n } } } \xi \vert \sqrt { \frac { 5 } { 4 } } \hat { \mathbf { z } } \vert \sqrt { \frac { 5 } { 4 } } \hat { \mathbf { z } } \vert \sqrt { \frac { 5 } { 4 } } \hat { \mathbf { z } } \vert } \\ { 0 , \ \frac { \operatorname { E } \hat { \mathbf { \pi } } } { \mathrm { i n } } x \hat { z } \vert \pm \hat { \mathbf { z } } \vert \hat { \mathbf { z } } \vert \hat { \mathbf { z } } \vert \pm \hat { \mathbf { z } } \vert } \\ { - 1 , x \mathcal { H } \hat { \mathbf { z } } \vert \hat { \mathbf { z } } \vert \sqrt { \frac { 3 } { 4 } } \hat { \mathbf { z } } \vert \sqrt { \frac { 5 } { 4 } } \hat { \mathbf { z } } \vert \sqrt { 3 } \hat { \mathbf { z } } \vert \sqrt { \frac { 5 } { 4 } } \hat { \mathbf { z } } \vert } \\ { - d , \frac { \operatorname { E } \hat { \mathbf { \pi } } } { \mathrm { i n } } x \mathcal { H } \vert \hat { \mathbf { z } } \vert \sqrt { \frac { 3 } { 4 } } \hat { \mathbf { z } } \vert \sqrt { \frac { 5 } { 4 } } \hat { \mathbf { z } } \vert } \end{array} \right.
$$

LASDF确定当前像素点到水平集曲线的最短距离和该距离的符号(曲线内为负，曲线外为正)，计算过程只关注包绕水平集曲线的一条半径为d(宽度为2d)的狭窄带区，由于 $\scriptstyle { d < < n }$ ，所以可将计算复杂度由 $O ( n ^ { 2 } \ln S )$ 减少为 $O ( n d \ln S ) , n$ 为图像中的像素点数，S为计算每一个像素点到水平集曲线的最短距离的耗费。水平集迭代过程伪代码如下：

function phiy=activecontourCV(uO, center,d,   
side,d_it, m_it, m_name) $\%$ 输入图像为double型,灰度为0—255 $\%$ 水平集初始化为椭圆形,center为轮廓线原点,d   
为窄带半径,side $^ { = 1 }$ 表示目标在起始轮廓线内， $\scriptstyle = 0$ 表示   
在外 （204号 $\%$ 初始化参数 ITERATIONS $\scriptstyle \operatorname { \dot { \rho } } = 2 0 0 0$ ， $\%$ 迭代次数 delta $\scriptstyle \mathrm { t = 0 . 1 }$ ， $\%$ 时间步长 $\%$ 轮廓内外能量参数 lambda1 $^ { = 1 }$ ; lambda2 $_ { = 1 }$ $\mathrm { \ n u { = } 0 }$ $\mathrm { d } { = } 3$ ：， $\%$ 曲率项参数 （204号 $\scriptstyle \mathrm { h = 1 }$ $\mathrm { h } \_ { \mathrm { s q } } = \mathrm { h } \wedge 2$ ; epsilon $_ { 1 = 1 }$ ; mu=0.01 \* 255^2; （204号 $\%$ 初始化LASDF phi=initLASDF(size(uO), center,d, side); for i $\mathrm { i } { = } 1$ : ITERATIONS; $\%$ 显示并保存图像 if(mod(ii-1, d_it) $\scriptstyle 1 = = 0$ ） segim $\vDash$ createim(uO, phi); imshow(segim); segim $\vDash$ createim(uO, phi); filename $\ c =$ strcat(m_name,sprintf('%d',i,'.jpg' ); imwrite(segim, filename); end; dirac_delta_t=delta_t \* diracfunction(phi, epsilon); $\%$ 计算轮廓线内外能量 [inside,outside]=calcenergyf(uO,phi, epsilon); energy_term $\scriptstyle { \frac { } { } } =$ -nu -lambdal .\*inside $^ +$ lambda2.\*   
outside; dx_central $\lfloor =$ (circshift(phi, [O,-1])-circshift(phi,[0,   
$1 ] ) / 2$ ， dy_central=(circshift(phi,[-1,O])-circshift(phi,[1,   
$0 ] ) ) / 2$ ：， abs_grad_phi $\ c =$ (sqrt(dx_central.^2 + dy_central.^2)   
$+ 0 . 0 0 0 0 1$ ） $\mathbf { \delta X = }$ dx_central./abs_grad_phi; y=dy_central ./abs_grad_phi; grad_term $\ c =$ (mu /h_sq) .\* divergence(x, y); phi=phi $^ +$ dirac_delta_t.\* (grad_term $^ +$   
energy_term ); p $\scriptstyle \mathrm { { h i y } } ( : , : , { \mathrm { i i } } ) = \mathrm { { p h i } }$ ： end; $\%$ 检测零水平集的位置

function front=isfro(phi) [n,m]=size(phi); front=zeros(size( phi)); for i=2: n-1; for $\mathrm { j } { = } 2 { : } \mathrm { m - } 1$ ， max Val $\Rightarrow$ max(max(phi(i:i+1, j:j+1))); minVal=min(min(phi( i:i+1, j:j+1))); front(i, j) $\scriptstyle = ($ (maxVal>O) & (minVal ${ < } 0 \dot { }$ ) $\mid \mathrm { { p h i } ( i , j ) = }$ $\scriptstyle = 0$ ： end end （204号 $\%$ 初始化水平集函数,局部近似符号距离函数 function phi=initLASDF (imsize,center, d, side) m=imsize(1); $\mathrm { \ n = }$ imsize(2); phi=zeros(imsize); for $\mathrm { i } { = } 1 { : } \mathrm { m }$ for $\mathrm { j } { = } 1 { : } \mathrm { n }$ ，， distance $\vDash$ sqrt(sum(center-[i,j]).^2)); phi(i, j)=distance-d; if(side $\scriptstyle = = 0$ ） （204号 $\mathrm { \ p h i ( \ i , j \Omega ) { = } { \ - p h i ( \ i , j \Omega ) } }$ end end end $\%$ dirac function y=diracfunction(x, epsilon) $\scriptstyle \mathbf { y } = \left( 1 . { \big / } \operatorname { p i } \right)$ .\*(epsilon./(epsilon. ${ \sim } 2 \mathrm { + x . } ^ { \sim } 2 )$ ） （204号 $\%$ 求轮廓内外能量 function value $\ c =$ heavisidef(z, epsilon) value $_ { = 0 . 5 }$ .\* $\mathrm { 1 + ( 2 . / p i ) }$ .\* atan(z./epsilon)); function[inside,outside] $\ c =$ calcenergyf(uO,ph:

epsilon) H_phi=heavisidef(phi, epsilon); H_phi_minus $\mathrel { \mathop : } 1$ -heavisidef(phi,epsilon); A=calcuProb(d); c1=A.\*sum(sum(uO.\* H_phi))/ sum(sum(H_phi)); $\mathrm { c } 2 \mathrm { = } \mathrm { A }$ .\*sum(sum(uO.\*H_phi_minus))/sum(sum   
(H_phi_minus)); inside $\ c =$ (u0-c1).^2; outside $\circeq$ (u0-c2).^2;

# 3结果

分割实验待测图像来自南方医科大学附属医院影像库，通过对相同B超图像样本进行分割来检验本文模型的效果，并与几种水平集模型进行比较。编程平台为Matlab7,计算机配置为Intel?CoreTM(2)Duo CPU.3.0GHz,2GBRAM,WindowsXP操作系统。所有实验采用相同的终止阈值 $\Delta E = 1 0 ^ { - 4 }$ 或最大迭代次数2000（考虑到用户等待时间)。图1\~3为实验结果举例，比较CV模型[]、RSF模型[4]、SLGS模型[9]LGF模型[1]、本文模型和专业医师手工分割结果。所有模型均按原文献方法进行相应参数设置，其中公共参数：时间步长 $\Delta t = 0 . 1$ ，空间步长 $\Delta h = 1$ ，长度惩罚项参数$\mu { = } 0 . 0 1 * 2 5 5 ^ { \wedge } 2 { \sim } 0 . 1 * 2 5 5 ^ { \wedge } 2 .$ 邻域半径&根据图像内容调整为最合适值(为5或7)，尽可能达到每种模型最优的分割效果。本文方法中的窄带半径d取3,即计算水平集曲线内外各3个像素的LASDF。

图1A子图为待测样本 $3 9 0 ^ { * } 2 9 0$ 像素的前列腺增生B超图像，分割目标为中下部团块暗区。图2A子图为待测样本 $4 8 8 ^ { * } 4 1 5$ 像素的盆腔(卵巢)B超图像，分割目标为中下部的卵黄囊部分。图3A子图为待测样本$6 1 5 ^ { * } 3 6 9$ 像素的盆腔(子宫肌瘤)B超图像，分割目标为中部偏右的子宫肌瘤体。图4A子图为待测样本 $3 6 1 ^ { * }$ 252像素的胆囊B超图像，分割目标为中部横向暗色团块区域。待分割图像均存在明显的灰度分布不匀，存在不同数量的多处伪影，存在散布的不同强度的噪声杂质，病灶部分边界比较模糊。

![](images/8de33e4351dcc506dbaa172e57c629580da1d9a2926e0e5d92495cc77100e81e.jpg)  
图1分割测试1  
Fig.1 Segmentation test1.A: Sample image to be segmented; B: Initial contour by manual; C: Segmentation result by CV model; D: Segmentation result by RSF model; E: Segmentation result by SLGS model; F: Segmentation result by LGF model; G: Segmentation result by the proposed model; H: Result of manual segmentation.

![](images/4cb28eadb098f14014c37b4ad2de9eebb2d171d1e3b79868f8945dc2da4d5b12.jpg)

![](images/fb0960d274ef9ce7e143285d9b7c2ef1c51f957037152fde3b7c1040133a7de4.jpg)  
图2分割测试2 Fig.2 Segmentation test 2.A: Sample image to be segmented; B: initial contour by manual; C: Segmentation result by CV model; D: Segmentation result by RSF model; E: Segmentation result by SLGS model; F: Segmentation result by LGF model; $G$ : Segmentation result by the proposed model; H: Result of manual segmentation.   
图3分割测试3  
Fig.3 Segmentation test 3.A:Sample image to be segmented; B:initial contour by manual; C: Segmentation resultby CV model; D: Segmentation result by RSF model; E: Segmentation result by SLGS model; F: Segmentation result by LGF model; G: Segmentation result by the proposed model; $H$ ：Result of manual segmentation.

根据医学诊断特异性的标准采用4个精度指示器：真阳性率(TP)，假阳性率(FP)，假阴性率(FN)，真阴性率(TN),结合临床诊断要求定义4个分割精度指标：

可接受率acceptrate：由专业医师判断自动分割结果是否可接受(含经过后续处理)，是否有参考价值。

测准度 $\cdot A c c u r a c y = { \frac { T P + T N } { T P + T N + F P + F N } }$ ，反映检验阳性和阴性与按该筛检实验的标准值的比值。

灵敏度 $\mathit { S e n s i t i v i t y } = \frac { \mathit { T P } } { \mathit { T P } + \mathit { F N } }$ ,又称真阳性率,反映筛检实验发现病灶的能力。

特异度Specificity $= { \frac { T N } { T N + F P } }$ ，又称真阴性率,反映筛检实验确定非病灶的能力。

表1为5种模型处理图1\~4的迭代次数、耗时和分割精度指标。对于分割结果存在多个连续区域的，取最大的区域或医师手工指定的区域。分割失败案例的指标无法计算，用“-"表示。

从南方医院临床医学影像图像库中随机抽取20幅B超图像，用5种模型分别进行处理，以获得处理精度的统计结果(只取全部分割成功的结果)。由于各幅图像大小、内容和质量不一致，所以不进行迭代次数和耗时的比较，只进行处理结果精度的统计比较,结果见表2。

# 4讨论

从以上实验及统计数据可以得出结论：在分割精度方面，本文模型不同程度地优于其它模型，各次实验的可接受率与CV、PSF模型相当，基本上可全部被人工接受，而平均测准度、平均灵敏度和平均特异度几乎都高于其他模型，其他模型的总体分割精度排序依次是：RSF模型、CV模型、SLGS模型和LGF模型，后两种模型效果受B超图像内容或质量的影响较大，均有分割不成功的样本。表明本文模型较为适合分割B超病变组织，同时筛检非病灶的能力较强。分析原因，CV模型借助全局信息提高了抗噪能力，但未考虑局部区域信息，水平集曲线粗略逼近目标边界，无法准确分割灰度不匀、伪影干扰和目标背景差别小的目标，且需要对所有图像点进行迭代计算，耗时较多；RSF模型运用局部拟合信息能够较好反映区域图像属性，在初始轮廓接近目标时分割较为准确，但依靠常数权重确定形变作用的比例关系，不能准确反映曲线位于不同区域时的动态变化，对模糊边界和噪声点容易出现错误;SLGS模型能够较好地提取弱边界，又有一定的抗噪性，但由于采用了全局分割策略，所以无法剔除背景中与病灶相似的成分，导致较多的碎片结果和误判断;LGF模型通过小邻域高斯函数能够较准确地表现局部的不规则变化，但容易产生大量冗余轮廓碎片而无法连成完整区域;本文方法在RSF模型的基础上引入图像熵的作用，计算动态权重因子，能够根据曲线不同时刻的变化位置实时调节作用力的权重，更为合理地判断弱边界上像素点的归属，并且具有一定的抗噪能力，分割结果最接近专业医师的手工分割结果，效果最好。

![](images/bdc27060a410b7f82641040d87e5abdf8843e4f7376a1cf547745e5a20e2d6e4.jpg)  
图4分割测试4  
Fig.4 Segmentation test 4.A:Sample image to be segmented; B:initial contour by manual; C: Segmentation result by CV model; D: Segmentation result by RSF model; E: Segmentation result by SLGS model;F: Segmentation result by LGF model; G: Segmentation result by the proposed model; H: Result of manual segmentation.

表15种模型的迭代次数、耗时(秒)和分割精度比较 Tab.1 Comparison of 5 models in iteration times,time consumption (seconds)and segmentation precision   

<html><body><table><tr><td>Model</td><td>Iteration times</td><td>Time consumption</td><td>Accuracy</td><td>Sensitivity</td><td>Specificity</td></tr><tr><td>Test 1</td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>CV</td><td>2000</td><td>132.785</td><td>0.892</td><td>0.865</td><td>0.918</td></tr><tr><td>RSF</td><td>640</td><td>54.207</td><td>0.921</td><td>0.942</td><td>0.901</td></tr><tr><td>SLGS</td><td>80</td><td>42.431</td><td>0.915</td><td>0.929</td><td>0.901</td></tr><tr><td>LGF</td><td>50</td><td>21.854</td><td>0.718</td><td>0.944</td><td>0.547</td></tr><tr><td>The proposed model</td><td>230</td><td>32.866</td><td>0.944</td><td>0.949</td><td>0.925</td></tr><tr><td>Test 2</td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>CV</td><td>390</td><td>58.695</td><td>0.915</td><td>0.898</td><td>0.933</td></tr><tr><td>RSF</td><td>80</td><td>18.958</td><td>0.911</td><td>0.913</td><td>0.910</td></tr><tr><td>SLGS</td><td>40</td><td>61.624</td><td>0.915</td><td>0.929</td><td>0.901</td></tr><tr><td>LGF</td><td>15</td><td>19.890</td><td>0.779</td><td>0.879</td><td>0.715</td></tr><tr><td>The proposed model</td><td>90</td><td>14.594</td><td>0.927</td><td>0.948</td><td>0.907</td></tr><tr><td>Test 3</td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>CV</td><td>160</td><td>25.736</td><td>0.885</td><td>0.928</td><td>0.847</td></tr><tr><td>RSF</td><td>90</td><td>23.547</td><td>0.917</td><td>0.915</td><td>0.919</td></tr><tr><td>SLGS</td><td>40</td><td>67.783</td><td></td><td>-</td><td></td></tr><tr><td>LGF</td><td>15</td><td>23.359</td><td>-</td><td></td><td></td></tr><tr><td>The proposed model</td><td>100</td><td>17.612</td><td>0.940085</td><td>0.950</td><td>0.931</td></tr><tr><td>Test 4</td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>CV</td><td>1900</td><td>107.053</td><td>0.860</td><td>0.916</td><td>0.804</td></tr><tr><td>RSF</td><td>420</td><td>37.429</td><td>0.912</td><td>0.928</td><td>0.916</td></tr><tr><td>SLGS</td><td>50</td><td>34.797</td><td>0.884</td><td>0.932</td><td>0.842</td></tr><tr><td>LGF</td><td>30</td><td>17.375</td><td>0.805</td><td>0.879</td><td>0.747</td></tr><tr><td>The proposed model</td><td>150</td><td>23.549</td><td>0.933</td><td>0.945</td><td>0.934</td></tr></table></body></html>

表25种模型对20幅随机图像的平均分割精度比较 Tab.2 Comparison of average segmentation precision of 20 random images by 5 models   

<html><body><table><tr><td>Model</td><td>Accept rate</td><td>Average accuracy</td><td>Average sensitivity</td><td>Average specificity</td></tr><tr><td>CV</td><td>100%</td><td>0.888</td><td>0.895</td><td>0.875</td></tr><tr><td>RSF</td><td>100%</td><td>0.914</td><td>0.904</td><td>0.902</td></tr><tr><td>SLGS</td><td>70%</td><td>0.878</td><td>0.902</td><td>0.890</td></tr><tr><td>LGF</td><td>75%</td><td>0.741</td><td>0.891</td><td>0.670</td></tr><tr><td>The proposed model</td><td>100%</td><td>0.937</td><td>0.949</td><td>0.926</td></tr></table></body></html>

在运算代价与分割速度方面，本文模型迭代次数多于SLGS模型和LGF模型，少于CV模型和RSF模型，实验耗时在部分情况下仅比LGF模型略多，比其他模型均有明显减少，说明本文模型的计算法则以及局部计算方案具有一定的降低计算复杂度的能力，有效地减少了总计算量。

# 5结论

本文提出一种面向B超图像病灶分割的动态权重因子区域水平集方法，利用图像熵计算动态权重因子，动态更新轮廓线内外区域对像素点的动态权重作用，决定曲线移动方向和形变趋向。在计算方法上，不采用传统的解偏微分方程方法，不需要扫描整个图像，仅对轮廓曲线内外邻域点实行转换判断处理，更新水平集演化趋势，减小了计算量。与几种水平集模型的比较，本文模型在平均测准度、平均灵敏度和平均特异度方面都表现较好，并且起伏很小，不容易受图像内容和质量的影响，较好地解决了B超图像灰度分布不匀、低对比度和模糊边界的问题。本文方法的局限性是动态权重因子是依据区域灰度分布进行计算的，而人眼视觉注意机制的研究表明，对人眼影响较大的低层视觉显著性特征还包括亮度、对比度、目标区域大小、目标位置、目标形状等，今后将根据不同内容的图像和不同需求的分割任务探索多种描述算子的表达和融合，以实现面向应用需求的更好分割。

# 参考文献：

[1] Saini K,Dewal ML,Rohit M. Ultrasound imaging and image segmentation in the area of ultrasound:a review[J].International Journal of Advanced Science and Technology,2010,24(2): 41-60.   
[2] Saini K,Lee LK, Liew SC,et al.A review of image segmentation methodologies in medical image [M].Advanced Computer and Communication Engineering Technology LectureNotesin Electrical Engineering,2015:1069-80.   
[3]Chan TF,Vese LA.Active contours without edges[J]. Image Processing,IEEE Transactions on,2001,10(2): 266-77.   
[4]Li C,Kao CY,Gore JC,et al. Minimization of region-scalable fitting energy for image segmentation [J]. IEEE Trans Image Process,2008,17(10): 1940-9.   
[5]Christos PL.A review of ultrasound common carotid artery image and video segmentation techniques［J]. Medical&Biological Engineering&Computing,2014,52(12):1073-93.   
[6] Shyu KK,Pham VT,Tran TT,et al. Globaland local fuzzy energybased active contours for image segmentation[J]. Nonlinear Dyn, 2012, 67(2): 1559-78.   
[7]Alipour S, Shanbehzadeh J.Fast automatic medical image segmentation based on spatial kernel fuzzy c-means on level set method[J]. Mach Vis Appl,2014,25(6): 1469-88.   
[8]Liu RJ,He CJ, Yuan Y.Active contours driven by local and global image fiting energy[J].计算机辅助设计与图形学学报,2012,24(3): 364-71.   
[9]Zhang KH, Zhang L, Song HH, et al. Active contours with selective local or global segmentation:A new formulation and level set method[J]. Image Vis Comput,2010,28(4): 668-76.   
[10]Wang L,He L,Mishra A,et al.Active contours driven by local Gaussian distribution fiting energy[J]. Signal Processing,2009,89 (12): 2435-47.   
[11]潘 改,高立群,赵 爽.基于局部熵的主动轮廓模型[J].中国图象图形 学报,2013,18(1):78-85.   
[12]Mitiche A,Ayed IB.Variational and level set methods in image segmentation[M]. New York: Springer,2010: 105-7.   
[13]Goldstein T,Bresson X, Osher S.Geometric applications of the split bregman method: segmentation and surface Reconstruction [J]. SIAMJ Sci Comput,2010,45(1/3): 272-93.   
[14]Estellers,V, Zosso,et al.Efficient algorithm for level set method preserving distance function[J]. UCLA CAM Report, 2011: 11-58.

(编辑：孙昌朋)