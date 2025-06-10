# 神经网络补偿算法在基于MEMS的姿态检测中的应用

孙玉杰1，贺思艳²，徐小龙1，田新诚1

(1．山东大学 控制科学与工程学院，济南 250061;2.山东电子职业技术学院 智能制造工程系，济南 250014)

摘要：针对基于微机电传感器的姿态检测领域存在的姿态测量误差问题，为进一步提高姿态检测的精度，提出了一种基于神经网络的姿态估计误差补偿方法。采用开源的微型飞行器在室内环境进行真实飞行试验采集的数据集，借助BP神经网络的非线性映射能力，建立了关于微机电传感器的输出和姿态估计误差之间的姿态误差补偿模型。根据微机电传感器的输出信息，直接预测得到横滚角、俯仰角和偏航角的误差补偿角度。实验结果表明，利用所提出的神经网络进行姿态补偿之后，姿态估计误差大大减小，表明神经网络对于提高姿态检测的精度具有一定的作用。

关键词：神经网络；姿态补偿；微机电传感器；姿态检测 中图分类号：TP183 doi:10.3969/j.ssn.1001-3695.2018.03.0200

# Application of neural network compensation algorithm in MEMS-based attitude measurement

Sun Yujiel, He Siyan², Xu Xiaolong1, Tian Xincheng1† (1.Collegeof Control Science& Engineering Shandong University，Jinan 25o061，China；2.Dept.of Intellgent Manufacturing Engineering Shandong Collge of Electronic Technology,Jinan 25oo14,China)

Abstract:Aiming at the atitude measurement error in the attude measurement fieldswhich are based on micro-electro-mechanical sensors，thispaper developedaneural-network-based compensationalgorithm to improve the atitudemeasurementaccuracy.Itutilized thepubliclyavailabledatasetsofamicro-aireraftperformingrealflightintheindoor environment.This paper establishedanatitudecompensation modelaccordingto thenonlinear mappingofBPneuralnetwork. It wasabout theoutputsof the micro-electro-mechanicalsensors and theatitudeestimation erors.Itcould predictthe compensated errorsofroll,pitchand yawangles through theoutputs of sensors.Experimentalresultsshow that the proposed neural network compensation algorithmcan greatlyreduce the atitude measurement erors.Results show that the neural network plays a certain role in improving the accuracy of the attitude measurement.

Key words: neural network;attude compensation; micro-electro-mechanical sensors; atitude measurement

# 0 引言

微机电系统（micro-electro-mechanicalsystem,MEMS）被认为是物联网（internetofthings,IoT）的核心。与传统的传感器相比，MEMS传感器具有体积小、精度高、集成度高以及成本低等优点，被广泛应用在姿态检测[1-3]、室内定位[4-6]等领域。但由于制造过程中存在的比例偏差、传感器轴不对中等误差以及温度、噪声等外部因素的影响，MEMS传感器的实际输出与理想输出之间会存在偏差。在这种情况下，依靠传感器的输出数据进行姿态检测或者室内定位等研究，所得到的结果跟预期结果的误差会大大增加。常规情况下利用MEMS传感器进行姿态测量方法是：对使用的传感器进行标定，然后将多传感器数据利用数据融合算法进行融合，得到最终的姿态测量值。但传感器的标定精度以及数据融合算法的性能都会影响最终的姿态测量结果，对于检测结果和真实姿态之间的误差，传统的姿态检测方法无法对其进行补偿。

为了获得更为准确的测量结果，通常有两种方法。第一种方式是提高传感器标定的精度，使得传感器的输出结果更加可靠。常见的传感器标定方法有转台标定法[7、6位置-24点标定法[8和26位置标定[9法。其中，利用转台进行传感器标定的方法中，所使用的转台价格昂贵、体积较大，并且在标定过程中，需要严格控制转台旋转角度，对操作的精度要求较高，只适合于在实验室等室内环境使用。6位置-24点标定法和26位置标定法虽然不需要利用转台等昂贵的高精密设备，但6位置-24点标定法在操作过程中，很难保证每个位置的四个点都正交垂直。由于计算过于复杂，26位置标定法很难应用于实际过程。寻找合适的数据融合算法是另外一种提高测量精度的方法。卡尔曼滤波(Kalman filter,KF)[1o]以及基于卡尔曼滤波衍生出的扩展卡尔曼滤波(extendedKalman filter，EKF)[l1]、无迹卡尔曼滤波(unscentedKalman filter，UKF)[l2]等方法被广泛应用于多传感器数据融合。在MEMS传感器的输出结果较为准确的前提下，这些数据融合方法尚能提供较为准确的姿态输出。其中，KF只能用于线性运动的姿态解析；EKF在目标处于较强的非线性运动时，也不能很好地追踪目标姿态；UKF的计算量较大，会较多的占用嵌入式系统的资源，使得嵌入式系统处理其他控制任务的能力降低。一旦传感器的输出结果可靠度较差或包含的噪声较大，依靠这些方法所获得的姿态结果与实际值的差距会大大增加。

因此，在传感器标定方法以及多传感器数据融合方法确定的情况下，寻找合适的方法进一步提高利用MEMS系统进行姿态检测的精度，具有一定的研究意义。针对以上问题，本文提出了一种基于神经网络的姿态补偿方法，用于补偿由传感器标定精度误差和数据融合误差导致的最终的姿态检测结果与实际值之间的误差，进一步提高基于MEMS传感器的姿态检测精度。该方法以MEMS传感器的输出值为输入，利用神经网络的非线性映射能力，获得MEMS姿态检测系统输出的欧拉角的误差补偿值，包括横滚角(roll)、俯仰角(pitch)和偏航角(yaw)。试验结果表明，使用神经网络进行姿态补偿后，基于MEMS传感器获得的姿态更加接近于实际姿态。

# 1 整体方法描述

传统的利用MEMS传感器进行姿态检测的流程如图1中虚线所示，其工作过程是单向的，检测过程中存在的误差会逐级传递。MEMS传感器标定过程中存在的误差会影响多传感器数据融合算法的性能，导致数据融合过程中的误差也会随之加大，而传统的测量方法无法对MEMS检测系统在检测过程中的误差进行补偿。

![](images/f9d2ac1ba1221c0bfc00275d804388641cd7582e1456e00747876a1d8c9c7555.jpg)  
图1含有补偿神经网络的姿态测量方法结构图

本文重点研究在MEMS传感器完成标定以及所选用的数据融合方法确定的情况下，利用神经网络的强非线性映射能力，对姿态测量过程中存在的误差进行补偿。本文提出的利用神经网络进行姿态补偿方法的整体结构如图1所示。整个方法由姿态测量和姿态补偿两部分组成。姿态测量部分由测量传感器（三轴陀螺仪，三轴加速度计和三轴磁力计）、传感器标定和多传感器数据融合算法组成。图中， ${ \bf G } _ { 0 } , { \bf A } _ { 0 } , { \bf M } _ { 0 }$ 分别表示标定前三种测量传感器的输出，αo,βo，yo分别表示数据融合算法输出的横滚角，俯仰角和偏航角。

姿态补偿部分由补偿神经网络完成，补偿后的姿态角分别为 $a _ { e } , \beta _ { e } , \gamma _ { e }$ 。为了提高MEMS检测系统在进行姿态检测时的精度，通常在MEMS检测系统用于实际应用之前，需要通过特定的参考系统获得其姿态检测误差，记参考系统的输出为αf，βf,Yf。常用的参考系统有：光学捕捉系统，如英国OxfordMetricsLimited的Vicon；激光跟踪仪系统，如美国FARO的激光跟踪仪，德国的Leica等；红外相机阵列系统，如加拿大的NDI等。

补偿神经网络由MEMS检测系统的传感器输出值，以及利用参考系统与MEMS测量系统对比获得的姿态角误差估计值αeo,βeo,yeo训练获得。将MEMS传感器的输出值进行处理后作为神经网络的输入，利用神经网络强大的非线性变换能力，补偿神经网络的输出是MEMS系统的姿态测量误差补偿值。经补偿神经网络进行姿态误差补偿后的测量值为最终的MEMS系统的姿态测量结果。

# 2 姿态补偿神经网络设计

补偿神经网络的实现过程如图2所示，包括网络的构建、网络训练和网络预测。

![](images/ae9d9f016e17fdb8d8df4dc0ef08e3f852f8f1a1c3fdbf81b1aaf1218c2c86ed.jpg)  
图2补偿神经网络实现过程

# 2.1网络构建

BP 神经网络是一个包含输入层、隐含层和输出层的前馈神经网络。Hecht-Nielsen已经证明，包含有一个隐含层的前馈神经网络能够逼近任意含有多个变量的函数[13]，因此，本文设计了一个含有一个隐含层的3层BP神经网络，用来实现姿态检测误差的预测，其结构如图3所示。

如前文所述，MEMS姿态检测系统的输出误差主要来自于传感器标定误差和数据融合算法，在所选用的数据融合算法确定的前提下，传感器的输出数据是否可靠直接决定了姿态检测系统的精度。因此，所设计的神经网络以MEMS传感器输出的三轴角速度、三轴加速度以及三轴磁场信息作为输入，输入层为 $\scriptstyle { m = 9 }$ 个神经元。输出层即为roll，pitch，yaw的误差补偿值，有 $\scriptstyle n = 3$ 个神经元。隐含层的神经元数目可以根据经验公式(1)确定，其中 $\boldsymbol { a }$ 为取值范围为[1,10]的整数。经过多次试验，本文中选择隐含层的神经元数目 $\scriptstyle { l = 1 1 }$ 。

![](images/9343a3c42763b74b38a0cc3bbf9a873a1e4bb475bcceb91af3d4f714a16a7f22.jpg)  
图3网络结构图

# 2.2训练样本

本文使用开源的微型飞行器(micro airvehicle，MAV)AscTec“Pelican”在装配有Vicon运动捕捉系统的$1 0 \mathrm { m } ^ { * } 1 0 \mathrm { m } ^ { * } 1 0 \mathrm { m }$ 的室内环境进行真实飞行试验的数据集[14]。该数据集包含“1LoopDown”、“2LoopDown”和“3LoopDown”三个子数据集，分别对应无人机在室内飞行的3次实验。在三次飞行实验中，飞行时间逐渐增加，数据集中包含的样本数也逐次增多。三个数据集中均提供了MEMS系统和Vicon系统的数据信息。Vicon系统的数据信息中包含了由地面Vicon系统捕获的MAV的空间位置、姿态以及角速度信息。MEMS系统的数据信息中包含了由无人机上搭载的 MEMS 传感器捕获的三轴加速度、三轴角速度、三轴磁场信息，以及无人机上的微处理器中嵌入的数据融合算法AscTec输出的无人机姿态信息。在两套姿态捕捉系统中，无人机的姿态均以欧拉角的形式呈现。1LoopDown数据集含有6401个样本，2LoopDown数据集含有16795个样本，3LoopDown 数据集中含有24033个样本。

本文以Vicon系统捕获的无人机姿态作为参考姿态Groundtruth，可以获得数据融合算法AscTec输出的无人机姿态信息与参考系统捕获的姿态信息之间的误差值。将此姿态误差值作为补偿神经网络的训练样本 $y { = } [ e _ { 1 } ~ e _ { 2 } ~ e _ { 3 } ] ^ { \mathrm { T } }$ ，其中 $\boldsymbol { e } _ { 1 } , \boldsymbol { e } _ { 2 } , \boldsymbol { e } _ { 3 }$ 分别为roll，pitch，yaw 的误差值。将数据集中的传感器输出信息作为神经网络输入训练样本 ${ \boldsymbol { x } } { = } [ \ g _ { x } \ g _ { y } \ g _ { z } \ a _ { x } \ a _ { y } a _ { z } m _ { x } m _ { y } m _ { z } ] ^ { \mathrm { { T } } }$ ，其中$g _ { x } , g _ { y } , g _ { z }$ 为MEMS传感器输出的三轴角速度、 $\mathbf { \Delta } a _ { x } , a _ { y } , a _ { z }$ 为三轴加速度， $m _ { x } , m _ { y } , m _ { z }$ 为三轴磁场信息。

为了训练得到更加可靠的神经网络，遵循大训练样本的原则，采用“3LoopDown”数据集中的数据样本进行网络训练，建立MEMS 传感器的输出和姿态估计误差之间的姿态误差补偿神经网络。用“1LoopDown"数据集中的样本进行预测，检验所设计的神经网络在提高MEMS传感器系统进行姿态检测精度的性能。

# 2.3网络训练

在进行神经网络训练之前，本文对输入输出样本按照式

(1) (2)(3)进行归一化处理，使得输入输出样本均落在[-1,1]。

$$
{ x _ { i } } ^ { \prime } = \frac { 2 ( x _ { i } - x _ { \operatorname* { m i n } } ) } { x _ { \operatorname* { m a x } } - x _ { \operatorname* { m i n } } } - 1
$$

$$
{ y _ { i } } ^ { \prime } = \frac { 2 ( y _ { i } - y _ { \operatorname* { m i n } } ) } { y _ { \operatorname* { m a x } } - y _ { \operatorname* { m i n } } } - 1
$$

其中： $x _ { i } { } ^ { \prime }$ ， $y _ { j } { \mathrm { ' } }$ 分别为归一化后的样本中第 $i , j$ 个参数， $x _ { i } , \ y _ { j }$ 为未进行归一化的样本中第 $i , \ j$ 个参数， $x _ { m i n }$ ， $y _ { m i n }$ 分别为未归一化的输入输出样本中的最小值， $x _ { m a x }$ ， $y _ { m a x }$ 分别为未归一化的输入输出样本中的最大值。

由于补偿神经网络输出的姿态角误差与输入的传感器输出信息之间的关系具有很强的非线性关系，因此，将神经网络权值：输入层和隐含层之间的权值 $w _ { i j }$ 以及隐含层和输出层之间的权值 $w _ { j k }$ 初始值均随机设置在[-1,1]之间，其中 $i \in [ 1 , 9 ]$ ， $j \in$ [1,11]， $k \in [ 1 , 3 ]$ 。

根据神经网络设计的一般原则以及大量试验，选用的隐含层激活函数为

$$
f ( l _ { j } ) = \frac { 1 } { 1 + e ^ { - ( l _ { j } + a _ { j } ) } }
$$

其中： $a _ { j }$ 为隐含层阈值， $l _ { j }$ 为隐含层中节点 $j$ 的输入，由输入层的输入以及输入层和隐含层之间的权值决定，具有如下形式：

$$
l _ { j } = \sum _ { i = 1 } ^ { i = 9 } w _ { i j } x _ { i }
$$

神经网络输出层的激活函数为

$$
g ( n _ { k } ) = \frac { 1 - e ^ { - 2 ( n _ { k } + b _ { k } ) } } { 1 + e ^ { - 2 ( n _ { k } + b _ { k } ) } }
$$

用于输出网络的预测结果。其中， $b _ { k }$ 为输出层阈值， $n _ { k }$ 为输出层中节点 $j$ 的输入，由隐含层各神经元的输出以及隐含层和输入层之间的权值决定：

$$
n _ { k } = \sum _ { j = 1 } ^ { j = 1 1 } w _ { j k } f ( l _ { j } )
$$

定义神经网络的总体训练误差为

$$
E = \frac { 1 } { 2 } \sum _ { k = 1 } ^ { k = 3 } ( y _ { k } - o _ { k } ) ^ { 2 }
$$

其中： $y _ { k }$ 为网络输出值， $o _ { k }$ 为期望输出值。

在本文中，采用梯度下降算法对神经网络的权值和阈值进行更新，更新后输出层的权值和阈值分别为

$$
w _ { j k , p } = w _ { j k , p - 1 } - \eta \frac { \partial E } { \partial w _ { j k , p - 1 } }
$$

$$
b _ { k , p } = b _ { k , p - 1 } - \eta \frac { \hat { \partial } E } { \hat { \partial } b _ { k , p - 1 } }
$$

更新后隐含层的权值和阈值分别为

$$
\begin{array} { l } { { w _ { i j , p } = w _ { i j , p - 1 } - \eta \frac { \hat { \partial } E } { \hat { \partial } w _ { i j , p - 1 } } } } \\ { { \displaystyle a _ { j , p } = a _ { j , p - 1 } - \eta \frac { \hat { \partial } E } { \hat { \partial } a _ { j , p - 1 } } } } \end{array}
$$

其中： $p$ 为更新次数， $\eta$ 为网络的学习速率，可以根据需要进行

调节。

# 3 神经网络姿态补偿结果及分析

为检验本文所设计的神经网络在进行姿态误差补偿方面的性能，采用“1LoopDown”数据集进行实验。利用本文设计的补偿神经网络，对无人机上搭载的MEMS系统测量的姿态信息进行误差补偿。

为了进一步对比补偿神经网络在提高MEMS姿态检测精度上的性能，本文设置了另外两组对比试验。由于在该MAV飞行实验中，传感器的标定均已完成，因此，除了MAV上搭载的处理器中嵌入的数据融合算法AscTec，本文在实验中还对比了姿态检测领域广泛使用的两种数据融合方法，分别为Madgwick等人提出的梯度下降方法[15]，Mahony等人提出的互补滤波方法[16]。

![](images/14c3df8e03ff2fe25e5aad171a490593167f710339b6c03931b705dda00c2d99.jpg)  
图4神经网络进行姿态补偿后的姿态角输出图

图4(a)\~(c)中分别展示了四种方法利用MEMS系统测量的无人机的俯仰角、横滚角和偏航角的结果。从中可以看出，在利用补偿神经网络进行姿态误差补偿前，由MEMS系统输出的MAV姿态信息与参考系统输出的姿态信息差距较大。相似的，广泛使用的Madgwick和Mahony算法在利用MEMS传感器输出值进行数据融合后，得到的MAV姿态信息与参考系统捕获的姿态信息也有一定的差距，但其整体检测性能要优于MAV中嵌入的数据融合方法。利用本文设计的补偿神经网络对AscTec数据融合方法进行补偿后，其检测结果与Madgwick和Mahony两种算法获得的姿态估计相比，更加接近于地面参考系统。由于神经网络的预测本身也存在误差，进行补偿后获得的姿态曲线中存在一定的毛刺，这可以通过均值滤波、快速傅里叶变换等方法去除，因为本文重点研究神经网络在姿态误差补偿方面的性能，因此对于去除毛刺的问题不再详细阐述。

图5为上述四种方法与参考系统之间的姿态检测误差图。从图中可以看出，与其他三种方法相比，利用补偿神经网络进行姿态补偿之后，MAV自身的数据融合算法输出的姿态角误差大大减小，基本可以实现在零附近波动。

![](images/29f1d75efc209eb710a3ebffd099e0b42d96cb43c4b7f6174d3409e488cb4ec8.jpg)  
图5四种方法的姿态检测误差图

从上面的分析中可以看出，被广泛应用于姿态检测领域的Madgwick和Mahony 算法，在进行姿态估计时也存在一定的误差。为了检验本文所设计补偿神经网络对于其他数据融合算法的兼容性，利用所设计的神经网络对 Madgwick 和Mahony 算法也进行了姿态补偿。其结果分别如图6(a)和(b)所示，图中，黑色曲线代表参考系统捕获的MAV姿态，蓝色和红色曲线分别表示这两种方法利用本文所设计的神经网络进行误差补偿前后，MEMS系统捕获的MAV姿态信息。

![](images/4d4989ab39e7ae906e85fda065ac96b98f6f3d75d5f9a6632ae91e2d5bdaee24.jpg)  
图6不同算法利用神经网络补偿前后姿态测量结果图

不难发现，两种方法经过本文设计的补偿神经网络进行输出姿态补偿之后，其检测结果更加接近于参考系统的检测值。因此，本文所设计的补偿神经网络可以方便的应用于其他数据融合算法，以提高整体姿态检测的精度。

均方根误差(root mean square error,RMSE)是评价拟合效果最常用的指标。为了更加直观的展示本文所设计的补偿神经网络在提高姿态检测精度方面的性能，本文列出了三种方法在利用所设计的神经网络进行补偿前后的姿态角均方根误差，如表1所示。

表1补偿前后姿态角的均方根误差[单位：弧度]  

<html><body><table><tr><td rowspan="2">方法</td><td colspan="3">补偿前</td><td colspan="3">补偿后</td></tr><tr><td>Pitch</td><td>Roll</td><td>Yaw</td><td>Pitch</td><td>Roll</td><td>Yaw</td></tr><tr><td>AscTec</td><td>0.0369</td><td>0.0470</td><td>0.2341</td><td>0.0101</td><td>0.0118</td><td>0.0361</td></tr><tr><td>Madgwick</td><td>0.0287</td><td>0.0273</td><td>0.0752</td><td>0.0135</td><td>0.0190</td><td>0.0473</td></tr><tr><td>Mahony</td><td>0.0282</td><td>0.0283</td><td>0.0756</td><td>0.0150</td><td>0.0186</td><td>0.0451</td></tr></table></body></html>

从表1中可以看出，利用所设计的神经网络进行姿态补偿后，三种方法通过MEMS传感器进行姿态测量的姿态估计误差大大降低，极大的提高了姿态补偿的精度，所设计的神经网络对于其他数据融合算法也具有良好的兼容性。

# 4 结束语

为提高基于MEMS传感器的姿态检测系统的检测精度，本文提出了一种基于补偿神经网络的姿态误差补偿方法。建立了MEMS传感器的输出与姿态测量误差之间的模型，利用BP神经网络卓越的学习能力，拟合出二者之间的强非线性关系。利用训练好的神经网络，通过输入处理后的MEMS传感器的数据，可以直接预测得到需要补偿的姿态误差信息。从实验结果来看，利用神经网络对检测姿态进行补偿，可以大大降低MEMS系统进行姿态检测的误差，提高姿态检测精度。并且所设计的补偿神经网络对于其他算法也具有良好的兼容性，可以方便的应用于其他算法中，以提高其他检测算法的姿态检测精度。因此可以得出结论，将神经网络应用于姿态补偿，有助于进一步提高MEMS系统的姿态检测精度。

# 参考文献：

[1] 戎海龙，彭翠云，马正华．基于惯性一地磁组合的运动体姿态测量算法 分析[J].计算机应用研究，2014，31(6):1657-1660.(Rong Hailong, Peng Cuiyun,Ma Zhenghua.Analysis of atitude determination algorithm formoving objects based on inertial-magnetic units [J].Application Research of Computers,2014,31(6): 1657-1660.)   
[2] 王绍丹，王宜怀，贾荣媛．基于加速度传感器的在途危险品行为姿态检 测方法[J/OL].计算机应用研究，2018，35 (8）．(2017-07-21) [2018-04-20]. http://www.arocmag.com/article/02-2018-08-003.html. (Wang Shaodan，Wang Yihuai,Jia Rongyuan.Atitude detection of dangerous goods in transit based on accelerometer [J/OL].Application Research of Computers，2018，35(8）．(2017-07-21）[2018-04-20]. http://www.arocmag.com/article/02-2018-08-003.html.)   
[3]Zizzo G,Ren L. Position Tracking During Human Walking Using an Integrated Wearable Sensing System [J]. Sensors，2017，17(12): 2866-2882.   
[4] 苏菲，金志刚，王柄鉴．基于惯性传感器的便携式消防员搜救系统[J]. 计算机应用研究,2015,32(12):3677-3681.(Su Fei,Jin Zhigang,Wang Bingjian.Portable fireman search and rescue system based on inertial sensors[J]. Application Research of Computers,2015,32(12): 3677-3681)   
[5] 谢光强，黄向龙，李杨，等．基于MEMS 加速度传感器的步数检测算法 研究综述[J/OL].计算机应用研究，2018，35(12）．(2018-01-12) [2018-04-20]. http://www.arocmag.com/article/02-2018-12-071.html. (Xie Guangqiang,Huang Xianglong,Li Yang,et al. Review of research on step detection algorithm with MEMS-based acceleration sensor[J/OL]. Application Research of Computers，2018，35 (12）．(2018-10-12) [2018-04-20]. htp://www. arocmag.com/article/02-2018-12-071. html.)   
[6]Tian Zengshan,Jin Yue,Zhou Mu,et al.Wi-Fi//MARG Integration for Indoor PedestrianLocalization [J]. Sensors,2016,16 (12): 2100-2123.   
[7]刘百奇，房建成．一种改进的IMU无定向动静混合高精度标定方法[J]. 仪器仪表学报，2008，29(6):1250-1254.(Liu Baiqi，Fang Jiancheng. Modified hybrid calibration method for IMU without orientation [J]. Chinese Journal of Scientific Instrument,2008,29 (6):1250-1524.)   
[8] 陈北鸥，孙文胜，张桂宏，等.捷联组合（设备无定向）六位置测试标 定[J].导弹与航天运载技术，2001，3(3):23-27.(Chen Beiou，Sun Wensheng,Zhang Guihong,et al. Strapdown unit (without orientation) six-position test calibration [J].Missiles and Space Vehicles,2001,3 (3): 23-27. )   
[9]Syed Z F,Aggarwal P,Goodall C,Niu X,Elsheimy N.A new multi-positioncalibration method for MEMS inertial navigation systems [J].Measurement Science and Technology,2007,18 (7):1897-1907.

[10]KalmanRE.ANew Approach to Linear Filtering and Prediction Problems [J].Journal of Basic Engineering Transactions,196o,82:35-45.

[11]邹波，张华，姜军．多传感器信息融合的改进扩展卡尔曼滤波定姿[J]. 计算机应用研究，2014,31(4):1035-1042.(Zou Bo,Zhang Hua,Jiang Jun.Multi-sensor information fusion’s improved extended Kalman filter attitude determination [J].Chinese Journal of Scientific Instrument,2014, 31 (4): 1035-1042.)

[12]王华剑，景占荣，羊彦．基于改进扩展卡尔曼粒子滤波的目标跟踪算法 [J].计算机应用研究,2011,28(5):1634-1636,1643.(Wang Huajian,Jing Zhanrong,Yang Yan.Target tracking algorithm based on improved extend Kalman particle filter [J].Application Research of Computers,2O11,28 (5): 1634-1636,1643.)

[13]Hecht-Nielsen R.Applications of counterpropagation networks [J].Neural

Networks,1988,1(2):131-139.

[14]Lee G H. MAV Dataset [EB/OL].[2018-04-20].https://ites.google com/site/gimheelee/home/mavdataset.   
[15]Madgwick S OH,Harrison AJL,Vaidyanathan A.Estimation of IMU and MARG orientation using a gradient descent algorithm [C]// Proc of IEEE International Conference on Rehabilitation Robotic.Zurich,Switzerland: IEEE Press,2011: 1-7.   
[16] Mahony R,Hamel T,Pflimlin JM.Nonlinear Complementary Filters on the Special Orthogonal Group [J].IEEE Trans on Automation Control, 2008,53 (5):1203-1218.