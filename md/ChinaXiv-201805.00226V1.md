# 基于PDR反馈的Wi-Fi室内定位算法研究

赵建国，王杰贵(电子工程学院，合肥 230037)

摘要：Wi-Fi指纹定位易受周围环境的影响，稳定性差；行人航迹推算定位（pedestrian dead reckoning，PDR）定位需要待定位目标的初始位置，且容易产生累计误差。针对上述问题,提出了一种基于PDR反馈的Wi-Fi室内定位算法。该算法主要分为三个阶段：基于相关向量回归（relevance vectorregression，RVR）的初始位置定位阶段、基于PDR定位的反馈阶段、基于K近邻（K-nearestneighbor，KNN）的指纹定位阶段。实验结果表明，提出的算法在定位精度和稳定性方面较其他的定位算法有明显的提高，并且该算法相对于Wi-Fi定位减小了时间复杂度，实时性较好。

关键词：指纹定位；行人航迹推算；相关向量回归 中图分类号：TN911.7 doi:10.3969/j.issn.1001-3695.2017.07.0666

# Research on Wi-Fi indoor positioning algorithm based on PDR feedback

Zhao Jianguo, Wang Jiegui (Electronic&EngineeringInstitute,Hefei23o037,China)

Abstract:Due tothe impactofthe surrounding environment,thestabilityofWi-Fifingerprintpositioning is verypoor.Andthe PDR can't independently give positioningresult Withoutthe initial positionofthetargetandhas serious cumulativeerror.To addressthis issue,thepaperpresentsaWi-FiindoorpositioningalgorithmbasedonPDRfedback.Theschemeconsistsofthree processes.Thefirstistogettheinitial positionbasedonRelevance VectorRegression (RVR)methods,andthesecond is the fedback correctionprocess whichbasedonPDR.The thirdis thefingerprint positioning processbasedonK-NearestNeighbor (KNN)algorithm.Experimental results show that the proposedalgorithm can well improve the accuracyand stabilityof the final positioning result.And the method in this paper can greatly reduce the time complexity which improves real time performance.

Key Words: fingerprint positioning; pedestrian dead reckoning; relevance vector regression

# 0 引言

近年来，人们对室内位置信息服务的需求越来越强烈[1]。目前室内定位的主要方式有基于无线局域网的定位、视觉定位、基于惯性传感器的定位[2]。随着智能手机的不断发展，其内置传感器的性能越来越好，测量精度越来越高[3]。因此，基于智能手机的室内定位技术成为研究的主流[4]。考虑到Wi-Fi和惯性传感器是智能手机的典型的配置，因此，基于智能手机的定位技术以Wi-Fi指纹定位和行人航迹推算定位（PDR）为主要手段[5]。Wi-Fi指纹定位可以独立定位，但另一方面由于在实际Wi-Fi室内定位环境中，接收信号强度（received signal strength,RSS)具有较高的随机性，因此，Wi-Fi指纹定位的稳定性较差。而PDR定位需要待定位目标的初始位置，而且容易产生累计误差。但是PDR定位只是依靠惯性传感器，可以提供比较稳定的定位结果，在一定程度上克服了Wi-Fi指纹定位的稳定性问题。

因此，将Wi-Fi指纹定位和PDR定位结合起来可以有效的解决单项定位的误差问题。

针对Wi-Fi指纹定位和PDR定位的结合问题，很多研究者已经提出了不同的解决方案。文献提出了一种基于Android系统融合PDR定位技术和Wi-Fi指纹定位技术的融合定位方案，该方案主要是针对步伐检测和航向角估算两个方面进行研究，得到了相对较优的定位结果。但是文中提出的步伐识别算法只是粗略地归纳了行人步伐的生物学特性，同时步伐起止时间点也是粗略地估计，对后期的估算精度造成了不良的影响；文献[7]提出了一种基于指纹和PDR 的融合定位系统，该系统分为客户端和服务端，融合后的算法定位精度有所提高并降低了复杂环境的影响。但是该系统需要将PDR定位的结果作为指纹定位的参数，两个算法不是同步进行的，实时性较差；文献[提出使用卡尔曼滤波融合Wi-Fi定位算法和PDR定位算法。但是在Wi-Fi定位中，该算法采用支持向量机（support vector machines,

SVM)的分类和回归分析来对初始位置进行定位。由于SVM算法需要设定惩罚因子，且核函数的选择受到Mercer定理的限制，使得初始位置不能得到精确的定位，从而对以后的定位精度产生了一定的影响。

针对Wi-Fi和PDR定位结合的问题，上述文献都是将两种定位结果直接进行融合。这种融合方式并没有较好的解决Wi-Fi定位稳定性差的问题，在Wi-Fi定位结果跳动性大的情况下，系统的稳定性问题仍然存在。而且忽视了待定位目标初始位置的定位精度对后续定位过程的影响，若误差一开始就存在于初始位置的定位结果中，那么将直接影响到PDR定位的有效性。同时，上述文献中的方法并没有减小算法时间复杂度，实时性较差。针对上述问题，本文提出了一种基于反馈的结合方法，在该方法中考虑了待定位目标初始位置的定位精度问题而设计了基于相关向量回归的初始位置定位算法，该回归算法较SVM算法不需要设置惩罚因子，且核函数的选择不受Mercer定理的限制，回归效果较好；在已知初始位置坐标后，PDR算法将定位结果反馈到Wi-Fi指纹定位中，作为指纹定位的输入，在指纹定位算法的在线阶段中，只需要将在线采集的指纹信息与PDR估算坐标物理空间相邻坐标的指纹信息进行匹配，大大减小了指纹识别时间，同时降低了复杂室内环境的影响，使得定位精度得到提高；最后，将指纹定位的结果输入到PDR定位中，对步长模型的参数进行修正，进一步提高局部定位的准确性。

# 1 融合定位的结构设计与实现

通过介绍Wi-Fi指纹定位和PDR定位的基本原理，以及其各自独立定位的优势与局限性，从而分析融合定位的必要性；在此基础上提出融合定位的方案与结构。

# 1.1Wi-Fi指纹定位与PDR定位

在复杂的室内传播环境中，为了有效对抗信号的多径传播，Wi-Fi定位通常采用位置指纹匹配的方法，建立物理坐标与信号强度的对应关系，实现目标的定位。指纹定位分为离线建库和在线定位两个阶段。离线阶段，采集来自参考点处的各个接入点(access point，AP)的RSS值，建立位置指纹库；在线阶段，将实时采集的RSS信号与位置指纹库进行匹配，得出用户位置。

PDR定位是一种轨迹推算式的定位方法，其基本思想是：在获取目标初始位置后，利用加速度传感器等算法得到用户的步长，然后利用方向传感器计算行人的移动方向，最后估算出行人的下一步位置坐标。若已知待定位目标在 $k$ 时刻的坐标为(x,y），步长为d，方向角为θ，则下一时刻目标的位置坐标(x+,yk+）的计算公式为

$$
\left\{ \begin{array} { l l } { x _ { k + 1 } = x _ { k } + d _ { _ k } \cdot \cos ( \theta _ { k } ) } \\ { y _ { k + 1 } = y _ { _ k } + d _ { _ k } \cdot \sin ( \theta _ { k } ) } \end{array} \right.
$$

从以上两种定位算法分析，都存在各自的局限性。在Wi-Fi指纹定位中，由于RSS信号具有时变性，RSS即使在同一位置上，不同时间的表现力也是不一样的，从而导致定位结果的稳定性较差，误差的方差比较大；在PDR定位中，由于对目标每次定位的过程中都需要使用上一步定位的结果，因此较长时间的定位容易产生累积误差。而且PDR定位需要已知待定位目标的初始位置坐标，不能单独进行定位。另一方面，两种定位方法也有各自的优势。Wi-Fi指纹定位可以提供比较精确的绝对定位结果，且不存在累积误差，可以对目标单独进行定位；而PDR定位的稳定性较好，可以有效的利用智能手机的内置传感器来提供方向信息。因此，将两种定位手段融合起来进行定位是非常必要的。

# 1.2基于PDR反馈的融合定位结构

在传统的融合结构（如图1所示）中，Wi-Fi定位和PDR定位只是简单的被一种滤波算法结合起来，没有较好的利用各自的反馈信息。综合上述问题，提出了一种基于PDR反馈的融合定位结构，如图2所示。该定位结构主要分为三个阶段：基于相关向量回归的初始位置定位阶段；基于PDR定位的反馈阶段；基于K近邻的指纹定位阶段。

![](images/4086341151b5259b8f8123048eb64673f4a7c6cacc20189c39f446e8e273f336.jpg)  
图1传统的Wi-Fi定位和PDR定位融合结构

![](images/b024f91d9c1deee628eaab48808146e9158f84d6f49314e1ee73bf5dfb30477d.jpg)  
图2基于PDR反馈的融合定位结构

对于阶段1，本文考虑了待定位目标初始位置的定位精度重要性以及RSS信号时变性的问题，提出了一种基于RVR的初始位置定位算法。与传统的机器学习算法不同的是，RVR算法不需要设定惩罚因子，而且核函数的选择不受Mercer定理的限制，因此可以得到更优的回归效果，得到更加精确的初始位置坐标。经过此阶段，可以大大减小由RSS信号时变性引入的误差，提高初始位置的定位精度，因此可以为阶段2提供更加准确的输入信息。对于阶段2，本文针对Wi-Fi定位结果的跳动性以及误差方差较大的问题，提出了一种基于PDR反馈的定位算法，此阶段主要是将PDR定位的结果反馈到最终的Wi-Fi定位中去。采用PDR反馈的定位结构，不仅可以有效的抵抗复杂的室内环境对定位结果的影响，而且可以大大缩小定位的范围，满足了用户的实时性需求。对于阶段3，主要是利用PDR定位的结果和实时采集的RSS 信号得出最终的定位结果(x,y)，同时根据 $\left( x , y \right)$ 对 PDR定位中的步长参数进行修正，减小PDR定位的累积误差。

整个系统的定位流程为：首先采用RVR算法解算出待定位目标初始位置的坐标；然后通过PDR定位，估算出目标下一步的位置坐标，将PDR定位结果输入到最终的Wi-Fi定位中；最后在线采集RSSI指纹向量，利用KNN算法将实时采集的RSSI向量与PDR估算坐标物理空间相邻坐标的指纹信息进行匹配，得到系统最终的定位结果，同时根据最终的定位坐标对PDR定位中的步长参数进行修正，输出最终的校正参数。

# 2 融合定位系统算法

# 2.1基于RVR 的初始位置定位算法

相关向量机是在贝叶斯框架的基础上提出的，它与SVM有着一样的函数形式，与 SVM一样基于核函数映射将低维空间非线性问题转换为高维空间的线性问题。在Wi-Fi指纹定位中，建立定位特征与物理位置的映射关系非常困难，同时为了减少复杂的室内环境对Wi-Fi指纹定位的影响，因此本文采用基于RVR的初始位置定位算法。

SVM回归算法是基于结构风险最小化原则构建学习机，与SVM相比，RVR算法这种基于贝叶斯框架构建学习机的预测结果更加精确。同时，RVM算法具有无须设定惩罚因子，核函数不受梅西定理限制这两大优势，且其为概率式预测，使算法的学习能力进一步提高。

本文采用RVR算法建立定位特征与物理位置的映射关系，在离线阶段采集信号指纹并通过RVR进行训练，在线阶段将实时采集的信号指纹通过RVR算法进行回归分析，得出具体的坐标位置。给定训练数据 $\left( x _ { i } , z _ { i } \right)$ ， $i = 1 . . . L$ ， $x _ { i } \in R ^ { M }$ ， $x _ { i }$ 为第 $i$ 个输入定位特征样本， $z _ { i }$ 为对应的输出位置坐标。将输入定位特征通过核函数的方法映射到一个高维非线性空间，然后构造所需要的回归函数：

$$
\begin{array} { r } { \left\{ \begin{array} { l l } { \displaystyle y \big ( \boldsymbol { x } ; \boldsymbol { w } \big ) = \sum _ { i = 1 } ^ { N } w _ { i } k \big ( \boldsymbol { x } , \boldsymbol { x } _ { i } \big ) + w _ { \mathrm { o } } } \\ { \displaystyle p \big ( \boldsymbol { z } _ { i } \big ) = N \big ( \boldsymbol { z } _ { i } \big | \boldsymbol { y } \big ( \boldsymbol { x } _ { i } ; \boldsymbol { w } \big ) ; \boldsymbol { \sigma } ^ { 2 } \big ) } \end{array} \right. } \end{array}
$$

其中： $\begin{array} { r } { N \big ( . \big ) } \end{array}$ 为正态分布密度函数， $k \left( x , x _ { i } \right)$ 为核函数，它可以是单一函数也可以是多个函数的组合形式。 $w _ { i }$ 为核函数的权重，$w$ 为由 $w _ { i }$ 组成的向量， $\boldsymbol { w } = \left[ w _ { \mathrm { 0 } } , w _ { \mathrm { 1 } } , . . . , w _ { \scriptscriptstyle N } \right] ^ { T }$ ， $y \big ( x ; w \big )$ 为训练得到的位置坐标， $p \big ( z _ { i } \big )$ 为第 $i$ 个目标值的概率密度函数， $\sigma ^ { 2 }$ 为噪声方差。

训练时，设 $z _ { i }$ 相互独立，且来自模型：

$$
z _ { i } = y \big ( x _ { i } ; w \big ) + \varepsilon _ { i }
$$

其中： $\boldsymbol { \varepsilon } _ { i }$ 为高斯噪声。则位置坐标的概率密度函数可改写为

$$
p \left( z / w , \sigma ^ { 2 } \right) = \left( 2 \pi \sigma ^ { 2 } \right) ^ { - \gamma _ { 2 } } \exp \left\{ - \frac { 1 } { 2 \sigma ^ { 2 } } \big \| z - \varphi w \big \| ^ { 2 } \right\} ( 4 \sigma ^ { 2 } )
$$

其中： $N$ 为样本规模， $\varphi$ 为所有特征向量组成的矩阵，且$\varphi = \left[ 1 , k \left( x _ { \mathfrak { n } } , x _ { \mathfrak { n } } \right) , k \left( x _ { \mathfrak { n } } , x _ { \mathfrak { 2 } } \right) , . . . , k \left( x _ { \mathfrak { n } } , x _ { \mathfrak { n } } \right) \right] ^ { T } , \quad n = 1 , 2 , . . . , N \circ$ 为了避免过拟合的问题，这里为 $w$ 附加一个落在0周围的正态分布，则所求概率为

$$
p \left( z _ { i } / z \right) = \int p \left( z _ { i } / z , \alpha , \sigma ^ { 2 } \right) p \left( w , \alpha , \sigma ^ { 2 } / z \right) d w d \alpha d \sigma ^ { 2 }
$$

其中， $p { \left( { z } _ { i } / z , \alpha , \sigma ^ { 2 } \right) }$ 可由马尔可夫性质求得， $p { \big ( } w , \alpha , \sigma ^ { 2 } / z { \big ) }$ 可据稀疏贝叶斯学习理论拆分后化简，由于积分项为高斯函数的乘积，可得到积分后的近似解：

$$
\left\{ \begin{array} { l l } { p \displaystyle \big ( z _ { i } / z \big ) = N \big ( z _ { i } / y _ { i } , \sigma ^ { 2 } \big ) } \\ { y _ { i } = \mu ^ { T } \varphi \big ( x _ { i } \big ) } \\ { \sigma ^ { 2 } = \sigma _ { _ { M P } } ^ { 2 } + \varphi ^ { T } \big ( x _ { i } \big ) \sum \varphi \big ( x _ { i } \big ) } \\ { \varphi \big ( x _ { i } \big ) = \big [ 1 , k \big ( x _ { i } , x _ { 1 } \big ) , k \big ( x _ { i } , x _ { 2 } \big ) , . . . , k \big ( x _ { i } , x _ { N } \big ) \big ] ^ { T } } \end{array} \right.
$$

其中： $\mu = \sigma ^ { - 2 } \Sigma \varphi ^ { \scriptscriptstyle T } T$ ，协方差 $\Sigma = \left( \sigma - 2 \varphi ^ { r } \varphi + \mathbf { A } \right) ^ { - 1 }$ ’${ \bf A } = d i a g \left( \alpha _ { \scriptscriptstyle 0 } , \alpha _ { \scriptscriptstyle 1 } , . . . , \alpha _ { \scriptscriptstyle N } \right) \qquad ; \qquad \quad \sigma _ { \scriptscriptstyle M P } ^ { \scriptscriptstyle 2 }$ 为满足$\left( \alpha _ { _ { M P } } , \sigma _ { _ { M P } } ^ { 2 } \right) = \arg \operatorname* { m a x } p \big ( \alpha , \sigma ^ { 2 } / T \big )$ 条件下的方差。任意设定 $\alpha$ 和$\sigma ^ { 2 }$ 的一个初始解，然后进行不断的迭代，得到训练值：

$$
\alpha _ { i } ^ { n e w } = h _ { i } / \mu _ { i } ^ { 2 }
$$

$$
\sigma _ { n e w } ^ { 2 } = \lVert \boldsymbol { T } - \varphi \boldsymbol { \mu } \rVert / \big ( N - \Sigma _ { i } h _ { i } \big )
$$

式（7）中， $\mu _ { i }$ 为第 $i$ 个平均权值，式（8）中 $h _ { \scriptscriptstyle i } = 1 - \alpha _ { \scriptscriptstyle i } \Sigma _ { \scriptscriptstyle i , i }$ ，$\textstyle \sum _ { i , i }$ 为 $\Sigma$ 对角线元素。

合适的核函数的选取对于RVR学习机器的效果有很大影响。在本文中，RSS信号的分布统计特性和非线性直接决定了核函数的选取。对于RVR学习机器来说，高斯核函数学习能力较强，泛化性能较弱；而样条核函数恰好相反。因此本文采用径向基核(Radial Basis Function,RBF)与样条核(Spline Function)构造组合的多核核函数：

$$
k \big ( x , y \big ) = \big | L _ { \eta } \big ( x , y \big ) + S \big ( x , y \big ) \big | \cdot G _ { \delta } \big ( x , y \big )
$$

其中： $S \left( x , y \right)$ 作为一种全局性较强的样条核函数，满足：

$$
S { \big ( } x , y { \big ) } = 1 + x y + x y \operatorname* { m i n } { \big ( } x , y { \big ) } - \left[ { \big ( } x + y { \big ) } / 2 \right]
$$

$$
\cdot \operatorname* { m i n } \left( x , y \right) ^ { 2 } + \left( 1 / 3 \right) \operatorname* { m i n } \left( x , y \right) ^ { 3 }
$$

式（11）中， $G _ { _ \delta } ( x , y ) , L _ { _ { \eta } } ( x , y )$ 分别为高斯(Gauss)和拉普拉斯(Laplace)核函数，为两种径向基核函数，分别满足：

$$
G _ { \delta } \left( x , y \right) = \exp \left( - \delta \left\| x - y \right\| ^ { 2 } \right)
$$

$$
L _ { \eta } \left( x , y \right) = \exp { \left( - \sqrt { \eta \left. x - y \right. ^ { 2 } } \right) }
$$

该组合核函数不仅最大限度地保留了学习能力，而且提高了其泛化性能，有效的解决了高斯核泛化能力弱的问题。同时，拉普拉斯核函数作为一种调和函数，使核函数的学习能力得到了进一步的提高。经验证，该组合核函数满足组合核函数构建的异构条件。RVR算法核函数的选择不受Mercer定理的限制，降低了核函数选择的复杂程度。这样就可以通过RVR算法建立回归函数，得到更优的回归效果，达到对待定位目标初始位置进行精确定位的需求。

# 2.2 改进的PDR定位算法

在已知目标的初始位置后，PDR定位算法将根据行人的步长和行人移动的方向来估算出行人移动后的位置。PDR算法的关键是：行人的步态检测、行人的步长计算、运动方向的确定。其中，行人的步态检测和运动方向可以通过智能手机内置传感器来获取，如：加速度传感器、陀螺仪、电子罗盘等。而步长的估算结果是影响PDR定位精度的关键因素。

PDR 算法的第一步就是步态检测。人的行走状态是一个周期性的过程，不同的个体之间差异性很小[9]。由于人的行走状态是周期性的，所以加速度传感器测出的数据也呈现周期性。因此，可以通过分析加速度的周期性变化来实现计步。本文通过智能手机每隔 $2 0 0 \mathrm { { m s } }$ 采集一次加速度的值，绘制出加

速度的变化曲线，如图3所示。

![](images/9d6d14dd051a4363f2f0361f236bcf6036e329b377cf928372e761fbebad073d.jpg)  
图3滤波前后加速度传感器信号对比

从图3中可以看出，在行走的过程中加速度传感器的信号值成周期性变化。由于原始信号在采集过程中存在噪声，需要采用窗口为 $\mathrm { \Delta N }$ （ $\mathrm { \Delta N = } 1 0$ ）的高斯平滑滤波对其进行处理：

$$
a _ { _ i } = \sum _ { k = i } ^ { i - N } a _ { _ k }
$$

从图3可以看出，滤波后信号的波峰非常明显。根据行人的行走状态，每一个波峰相当于走的一步。因此，当检测到波峰时，则计步一次。

PDR定位算法的关键是步长的估算，步长估算结果的准确性将直接影响到PDR定位的精度。本文主要是对已有步长模型的改进，并通过实验证明了改进步长模型的有效性。目前，传统的步长模型[10]有：人工智能步长模型、运动机械模型、线性模型、非线性模型和常数/伪常数模型。其中，非线性模型相比其他四种模型较为简单，可以在智能手机上实现。但是该模型在行走速度比较慢的时候有较好的准确性，不太适用于快速行走的情况。考虑到要适应各种不同的行走状态，本文主要对非线性步长估算模型进行了改进，提高了算法的有效性。

非线性步长估计模型根据步长与加速度的非线性关系，采用统计分析的思想，建立数学模型。若已知行人一步内的最大和最小加速度，则根据该模型步长的计算可表示成[I]

$$
L = H \cdot \sqrt [ 4 ] { a _ { _ \mathrm { m a x } } - a _ { _ \mathrm { m i n } } }
$$

其中： $\mathbf { \Omega } _ { L }$ 为步长， $H$ 为模型系数。

本文使用华为Nova2手机分别实现了传统的非线性步长模型和改进步长模型，实验发现，传统的非线性模型在行人快速行走时准确性较差，原因是该模型忽略了行走时间这个关键性因素。针对该问题，本文改进了传统的步长估算模型，采用以下公式：

$$
L = H _ { \mathrm { { } _ { 1 } } } \cdot a _ { \mathrm { { } _ { a v g } } } \cdot T _ { s t e p } + H _ { \mathrm { { } _ { 2 } } } \cdot \sqrt [ 4 ] { a _ { \mathrm { { m a x } } } - a _ { \mathrm { { m i n } } } }
$$

其中： $H _ { \mathfrak u }$ 和 $H _ { _ 2 }$ 为模型参数，其初始值可以先进行预设，之后根据融合定位的结果进行修正。下面主要进行了两组实验对传统非线性模型和改进步长模型作出比较。首先选取科大学科实验楼前作为实验地点，行人将手机固定在腰上，分别对1.42步/秒和2.20步/秒的行人速度进行加速度数据采集。在进行实验之前，根据行人的实际步长和加速度的测量数值求出模型参数$H$ 的值，其中 $H = 0 . 3 4 2 6$ ， $H _ { \scriptscriptstyle 1 } = 0 . 1 1 2 4 , H _ { \scriptscriptstyle 2 } = 0 . 2 2 4 3$ 。下面的实验都是在模型参数值不变的情况下进行的。

# 1）1.42步/s的行走速度

模型参数保持不变，以1.42步/s的平均速度行走 $4 8 \mathrm { m }$ ，分别运行传统非线性步长模型算法和本文算法，运行8次。从图4中可以看出，除了第2次，改进模型的效果都比传统模型好很多。

![](images/12ae6e60c1d2cb6cc060a0dcac894c661b21dae91677479195263308f6f45598.jpg)  
图4行走速度为1.42步/秒的模型误差对比

# 2）2.20步/s的行走速度

模型参数保持不变，以1.42步/s的平均速度行走 $7 8 \mathrm { m }$ ，分别运行传统非线性步长模型算法和本文算法，运行8次。从图5中可以看出，每一次改进模型的效果都比传统模型好很多。在行走速度较快的情况下，相比第一次实验，改进模型的效果更加突出，误差更小。因此，改进的模型更能适应各种行走速度的状态，鲁棒性更好。

![](images/add974d91e4876e26d574c6c70bd286c9761cd5b11d087a8271e21911db2d3fb.jpg)  
图5行走速度为2.20步/秒的模型误差对比

# 2.3基于KNN 的指纹定位算法

在此定位算法的最后阶段，主要是采用KNN 算法进行指纹匹配。匹配过程如下：在得到 PDR 定位的位置坐标(x,y)后，找出指纹库中与 $\left( x _ { \mathrm { 0 } } , y _ { \mathrm { 0 } } \right)$ 物理空间相邻坐标的指纹信息；实时采集待定位目标 RSSI 指纹向量，计算在线指纹与 $\left( x _ { \mathrm { 0 } } , y _ { \mathrm { 0 } } \right)$ 相邻坐标指纹信息间的欧式距离 $D _ { _ i }$ ，如式（16)，然后找出K个$D _ { _ i }$ 最小的点，根据 KNN 算法得到最终位置 $\left( x , y \right)$ ，如式（17），其中 $w _ { i }$ 为第 $i$ 个参考点的权值。

$$
D _ { i } = \sqrt { \sum _ { j = 1 } ^ { n } \left( R S S _ { i j } - R S S _ { j } \right) ^ { 2 } }
$$

$$
\left( x , y \right) = \sum _ { i = 1 } ^ { K } w _ { i } \left( x _ { i } , y _ { i } \right)
$$

在KNN算法中,K的取值取决于 $\left( x _ { \mathrm { 0 } } , y _ { \mathrm { 0 } } \right)$ 相邻坐标的个数。而相邻坐标的选取直接影响到定位的精度，设离线阶段采集的参考点间距 $\mathrm { 1 m }$ ，每个参考点都在 $1 m \times 1 m$ 的正方形网格的中心，这样在定位区域平面内,本文以PDR估算坐标 $\left( x _ { \mathrm { 0 } } , y _ { \mathrm { 0 } } \right)$ 为圆心，以 $r = 2 m$ 为半径作圆，则在圆内（包括在圆上）的参考点被选作相邻坐标，如图6所示。

![](images/6a40ca248aec86a598385df0f012507cc8f920d17c34aa4b759175b5ee7aa2ac.jpg)  
图6 $\left( x _ { \mathrm { 0 } } , y _ { \mathrm { 0 } } \right)$ 相邻位置坐标

# 3 算法验证及分析

本文的实验场景在科大图书2楼，大小为 $3 0 \mathrm { m } \times 4 0 \mathrm { m }$ ，使用测量的手机为基于Android系统的华为nova2。

# 3.1基于RVR的Wi-Fi定位实验分析

为了验证RVR算法在回归模型构建方面的有效性，本文在进行融合定位实验之前，首先对RVR算法的回归效果进行了仿真分析。在同一组指纹样本数据下，本文分别对单核RVR算法、组合核RVR算法以及SVR算法进行了回归模型训练仿真对比实验。为了模拟室内环境，本文参与模型训练的指纹样本由传播损耗经验模型生成，该模型公式为

$$
P \big ( d \big ) = P \big ( d _ { \circ } \big ) + 1 0 n \log \big ( d / d _ { \circ } \big ) + X _ { \sigma }
$$

其中： $d$ 为AP热点与参考点的实际物理距离， $d _ { \mathrm { o } }$ 为预设参考距离， $P \big ( d _ { \mathrm { 0 } } \big )$ 为预设距离处的 RSSI 值， $n$ 为路径损耗因子，$X _ { \sigma }$ 为环境因子， $P ( d )$ 为距离 $d$ 处的RSSI值。设距离为 $2 \mathrm { m }$ 时的信号强度值为-35dB， $\mathrm { n } { = } 3 . 5$ ，环境因子 $X _ { \sigma }$ 设为强度为4dB的高斯白噪声。在生成的对数传播损耗模型上选取200个样本点，分别进行回归模型训练仿真实验，仿真结果如图7\~9所示。

![](images/5162b8dc0b75d7b547284363978a0af9fe67d310c450d10f119e9c00bab453dd.jpg)  
图7SVR模型训练效果

![](images/e5394877f888c32367b79e6581ea4a16543738d7757c7d0d0636229b6f91e294.jpg)  
图8高斯核RVR损耗模型训练效果图

![](images/eba9f0155fb91f20ae4921e9e2c3bcb5e9b4df4337df7284238f2a7877d07b6c.jpg)  
图9组合核RVR损耗模型

图7和8表明，与RVR算法相比，SVR算法经过回归训练得到的传播损耗模型在 $2 . 5 { \sim } 8 \mathrm { ~ m }$ $3 0 { \sim } 4 0 \mathrm { m }$ 等多处拟合效果较差，训练结果并不理想。对比图9的偏差曲线可知，在RVR回归训练中，本文所采用的组合核函数综合了单核核函数的优势，使得误差基本可以控制在7dB以内，平均误差在1.5dB左右，得到的回归曲线更加平滑，可以更好的提高定位的精度。

为了验证RVR算法在室内定位中的可行性，在主频为2.30GHz的Inteli5双核CPU及3.8GB内存的PC机上利用Matlab 软件进行定位仿真实验。仿真环境模拟长 $1 6 . 1 5 \mathrm { m }$ 、宽$3 . 7 7 \mathrm { m }$ 的实验室走廊室内定位场景，在走廊的两侧布有8个无线 AP 热点，每个无线热点之间相隔 $4 \mathrm m$ ，它们的坐标可以很容易得出。离线采集阶段，设置采样距离为 $\mathrm { 1 m }$ 的48个RSS信号采样点；在线定位阶段，对待定位目标进行随机选取。采用式(18)的经验对数传播损耗模型,令d=2,p(d)=-15,n=2模拟实验室环境建立传播损耗模型。本文分别实现了RVR 算法、SVR 算法[I2]、KNN 算法。其中 SVR 算法采用高斯核函数，RVR算法采用组合核函数，KNN算法中K的值取5。仿真结果如图10所示。

![](images/bad6e302c1be31cbb935a58c4e46586966e6976479f03d75e545dd2b8a8d9306.jpg)  
图10不同定位误差下各个算法的累积概率分布

从图10中可以看出，基于RVR的定位算法在定位误差为1.5米时概率为 $89 . 6 \%$ ，大于SVR 算法的 $73 . 5 \%$ ；而基于KNN的定位算法在定位误差为3米时的概率才达到 $8 6 . 7 \%$ 。因此，本文所提出的基于RVR的室内定位算法平均误差距离为1.42米，相对于对比算法可以极大的缩小定位误差范围，可以满足对初始位置的精确定位的需求，对于融合定位算法具有关键性的作用。

# 3.2基于PDR反馈的融合定位实验分析

本文分别对基于PDR反馈的融合定位、基于RVR的WiFi定位和PDR定位在图书馆2楼的走廊内进行了定位实验。

图11是对三种算法的定位结果，其中最左侧是起点，最右侧为终点。行走路线为先从科大图书馆 $1 0 \mathrm { m } \times 1 0 \mathrm { m }$ 的方形走廊左侧进入，然后从右侧走出停止。整个过程共行走46步，全程以匀速行走为主。

![](images/48705d9543a38ac511c6c112e8d46427cecbf8af48c6d0a124618467250d636b.jpg)  
图11 Wi-Fi-PDR、PDR和Wi-Fi的行走轨迹对比

![](images/6157cd3600341d7ab4ff695d55d0bceaf4deeb4f5b29f29cf9e86f7dca565d08.jpg)  
图12不同定位误差下各个算法的累积概率分布

从图11中可以看出，Wi-Fi定位由于受环境的影响，定位结果不够稳定，出现跳变的现象。而且由于Wi-Fi定位没有利用方向信息，定位误差较大，与真实轨迹的重合度不高。而在PDR定位的前半段与真实轨迹大体吻合，但由于PDR定位存在累计误差的缺陷，因此在后半段的重合度并不是很好。其中，基于PDR反馈的融合定位与真实轨迹的重合度最高，在单独定位误差比较大的区域，融合定位仍然精度很高。

图12显示了各个算法不同定位误差的累积概率分布。其中，融合定位的平均误差为 $1 . 2 4 \mathrm { { m } }$ 。而PDR定位和Wi-Fi定位的平均误差分别为 $1 . 8 2 \mathrm { m }$ 和 $2 . 6 4 \mathrm { { m } }$ 。从图12中可以看出，融合定位的误差已经较为稳定，虽然部分位置受PDR定位误差累积的影响，但可以及时通过Wi-Fi定位进行修正，定位精度最高。同时在融合定位中，在每一步的定位过程中其指纹匹配个数相对于Wi-Fi定位大大的减少，提高了算法的实时性。

# 4 结束语

本文针对Wi-Fi定位易受周围环境影响以及PDR定位需要初始目标位置且存在累积误差等问题，提出了一种基于PDR反馈的融合定位算法。通过在Wi-Fi定位系统中加入PDR的定位信息，取得了较好的定位效果。在融合定位中针对已有融合定位算法对目标初始位置定位精度普遍不高的问题，提出了基于RVR算法的初始位置定位阶段，使得定位误差降到 $1 . 4 2 \mathrm { m }$ ；在基于KNN的指纹定位算法中，利用PDR定位信息不仅克服了Wi-Fi定位稳定性差的问题，而且缩小了定位区域的范围，大大较少了指纹匹配的时间。通过以上算法的改进，在融合定位系统的精度和实时性方面都得到了提高，平均定位误差由 $2 . 6 4 \mathrm { { m } }$ 降到了 $1 . 2 4 \mathrm { { m } }$ 。通过实验验证，本文提出的算法有效的抵抗了复杂室内环境的影响，定位精度和实时性同时得到了提高，具有良好的定位效果。

# 参考文献：

[1]吴冲，苏兵，焦筱悛，等．基于改进动态 RSSI 算法的 WI-FI室内定位研究[J]．常州大学学报：自然科学版,2014,26(1):32-36.  
[2]姚团结，魏东岩，袁洪，等．基于反馈校正的 WLAN与PDR融合定位方法研究[J].仪器仪表学报,2016,37(2):446-447.  
[3]Vervisch-Picois S A,Samama N.Design of new codes for reducinginterference between-like signals transmitted indoors [C]//ProcofInternational Conference on Indoor Positioning and Indoor Navigation.2013:1-9.  
[4]丁琳，管小卫．基于RSSI的集群实时定位系统设计[J]．国外电子测量技术,2014,33 (12):69-73.  
[5]Cho HH,Kim MI, Kim S H.A study on PDR heading angle error correctionalgorithmusing WLAN based localization information [M]//Embedded andMultimedia Computing Technology and Service.2012: 63-72.  
[6]周礼争．基于Android的PDR和Wi-Fi指纹融合室内定位技术研究 [D].南昌：江西师范大学,2016.  
[7]田 丰．基于指纹和PDR的室内定位研究[D].重庆：重庆大学,2015.  
[8]周瑞，袁兴中，黄一鸣．基于卡尔曼滤波的 Wi-Fi-PDR 融合室内定位[J]．计算机工程与应用,2016,45(3):399-404.  
[9]Stirling R,Colin J,Fyfe K,et al. An innovative shoe-mounted pedestriannavigation system [C]// Proc of European Navigation Conference.2003:110-115.  
[10]陈伟．基于GPS和自包含传感器的行人室内外无缝定位算法研究[D].合肥：中国科学技术大学,2010.  
[11]Weinberg H.Using the ADXL202 in pedometer and personal navigationapplications [R]//Analog Devices AN-602 Application Note.2002.  
[12]陈丽娜.基于WLAN的位置指纹室内定位技术[M].北京：科学出版社,2015.