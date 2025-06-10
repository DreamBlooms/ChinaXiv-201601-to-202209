ChinaXiv合作期刊

# 非线性滤波在SINS中的应用

鱼少少，裴军，胡超(中国科学院大学 国家天文台北京)

摘要：针对载体的姿态和角速度估计问题，分别给出了基于卡尔曼滤波和粒子滤波的估计算法。对于欧拉角带来的奇异问题，采用四元数描述载体的姿态角。通过对 mpu9250 模块（陀螺仪、加速度计和磁力计)进行数据采集，并运用实验数据和仿真运算，验证了四元数卡尔曼滤波和粒子滤波算法的可行性。静态实验和动态仿真的计算结果表明，在使用MEMS 器件测量载体姿态时，粒子滤波和卡尔曼滤波算法得到的误差均值相当，但粒子滤波的标准差相对较小。

关键字：四元数；卡尔曼滤波；粒子滤波；姿态估计中图分类号：TN927文献标识码：A文章编号：1672-7673

随着微小型飞行器和机器人等的姿态估计常常采用滤波器对来自微机械（MEMS）惯性测量单元（IMU）的多传感器数据进行融合得到，常用的MEMS器件测量器件包括三轴陀螺仪、三轴加速度计和三轴磁力计本文采用四元数进行姿态解算。文[1]进行了四元数卡尔曼滤波方程的建立和方程，文[2]对文[1]提出的四元数卡尔曼滤波进行性能分析。同时很多人也进行了粒子滤波在姿态估计中的研究[。文[4]和文[5]通过对四元数的分析，设计了四元数粒子滤波算法求取姿态。本文通过对微机械器件数据采集和处理，设计非线性四元数卡尔曼滤波和粒子滤波，并对其姿态解算结果进行进一步分析。

# 1 四元数简介

载体上的微机械惯性测量器件的输出转换成载体的姿态，即载体自身坐标系 $( x _ { b } , y _ { b } , z _ { b } )$ 相对于导航坐标系（ $x _ { n }$ $y _ { n } , \ z _ { n } .$ ）的角位置，写成矩阵形式如下：

$$
{ \binom { x _ { b } } { y _ { b } } } = A _ { z - y - x } * { \binom { x _ { n } } { y _ { n } } } ,
$$

欧拉角是载体的3个姿态角，即俯仰角（pitch）、横滚角（roll）和偏航角（yaw)。根据欧拉旋转定律，可以通过3次旋转使得载体坐标系与导航坐标系重合，每一次旋转都以导航坐标系的一个坐标轴来转动，转过的角度就是欧拉角，每次旋转后坐标关系可由一旋转矩阵表示，即方向余弦矩阵，（1）式采用 $Z ^ { - } J ^ { - } X$ 的旋转顺序依次旋转：

$$
\begin{array} { r l } { A _ { z - y - x } \left( \Psi , \textbf { \theta } , \textbf { \phi } \right) = A _ { z } \left( \Phi \right) A _ { y } \left( \textbf { \theta } \right) A _ { x } \left( \Psi \right) = } & { } \\ { c o s \theta * c o s \varphi } & { \quad - s i n \theta } \\ { \left[ s i n { \emptyset } * s i n \theta * c o s \varphi - c o s { \emptyset } * s i n { \varphi } } & { s i n { \emptyset } * s i n \theta * s i n \varphi + c o s { \emptyset } * c o s { \varphi } \quad s i n { \emptyset } * c o s \theta \right] , } \\ { c o s { \emptyset } * s i n \theta * c o s \varphi + s i n { \emptyset } * s i n { \varphi } } & { c o s { \emptyset } * s i n \theta * s i n \varphi - s i n { \emptyset } * c o s { \varphi } \quad c o s { \emptyset } * c o s \theta } \end{array}
$$

其中， $\psi , \phi ,$ ： $\theta$ 分别代表偏航角、横滚角、俯仰角。为了避免欧拉角在表示姿态时可能出现

ChinaXiv合作期刊

的奇异问题，四元数在载体的姿态表示方面有广泛的应用。设计载体姿态四元数为

$$
\mathbf { q } = ( q _ { 0 } , q _ { 1 } , q _ { 2 } , q _ { 3 } ) = q _ { 0 } + q _ { 1 } * i + q _ { 2 } * j + q _ { 3 } * k ,
$$

导航坐标系与载体坐标系之间的坐标变换可以用方向余弦矩阵表示，其四元数形式为

$$
A ( q ) _ { n } ^ { b } = \left[ \begin{array} { c c c c } { q _ { 0 } ^ { 2 } + q _ { 1 } ^ { 2 } - q _ { 2 } ^ { 2 } - q _ { 3 } ^ { 2 } } & { 2 ( q _ { 1 } q _ { 2 } + q _ { 0 } q _ { 3 } ) } & { 2 ( q _ { 1 } q _ { 3 } - q _ { 0 } q _ { 2 } ) } \\ { 2 ( q _ { 1 } q _ { 2 } - q _ { 0 } q _ { 3 } ) } & { q _ { 0 } ^ { 2 } - q _ { 1 } ^ { 2 } + q _ { 2 } ^ { 2 } - q _ { 3 } ^ { 2 } } & { 2 ( q _ { 2 } q _ { 3 } + q _ { 0 } q _ { 1 } ) } \\ { 2 ( q _ { 1 } q _ { 3 } + q _ { 0 } q _ { 2 } ) } & { 2 ( q _ { 2 } q _ { 3 } - q _ { 0 } q _ { 1 } ) } & { q _ { 0 } ^ { 2 } - q _ { 1 } ^ { 2 } - q _ { 2 } ^ { 2 } + q _ { 3 } ^ { 2 } } \end{array} \right] ,
$$

简记为：

$$
A ( q ) _ { n } ^ { b } = { \binom { T _ { 1 1 } } { T _ { 2 1 } } } \quad T _ { 1 2 } \quad T _ { 1 3 } \nonumber
$$

导航坐标系到载体坐标系的旋转变换过程中坐标系始终保持直角坐标系，所以 $A ( q ) _ { n } ^ { b }$ 为正交坐标系，即 $A ( q ) _ { n } ^ { b } \ d { = } ( A ( q ) _ { n } ^ { b } ) ^ { - 1 } = ( A ( q ) _ { b } ^ { n } ) ^ { T }$ 。从而载体的姿态角为

$$
\left\{ \begin{array} { l } { \theta = - a r c s i n T _ { 1 3 } } \\ { \emptyset = \arctan \frac { T _ { 2 3 } } { T _ { 3 3 } } } \\ { \varphi = a r c t a n \frac { T _ { 1 2 } } { T _ { 1 1 } } } \end{array} \right. .
$$

四元数的微分方程如下：

$$
\begin{array} { r } { \dot { q } = \frac { 1 } { 2 } q \cdot \omega , } \end{array}
$$

其中，q为描述载体转动的四元数； $\omega$ 为载体相对导航参考坐标系的角速度，也表示为四元数的形式：

$$
\omega = 0 + \omega _ { x } \cdot i + \omega _ { y } \cdot j + \omega _ { z } \cdot k ,
$$

$$
\begin{array}{c} \begin{array} { r } { \left[ \dot { q _ { 0 } } \\ { \dot { q _ { 1 } } } \\ { \dot { q _ { 2 } } } \\ { \dot { q _ { 3 } } } \end{array} \right] = \frac { 1 } { 2 } \left[ \begin{array} { c c c c } { 0 } & { - \omega _ { x } } & { - \omega _ { y } } & { - \omega _ { z } } \\ { \omega _ { x } } & { 0 } & { \omega _ { z } } & { - \omega _ { y } } \\ { \omega _ { y } } & { - \omega _ { z } } & { 0 } & { \omega _ { x } } \\ { \omega _ { z } } & { \omega _ { y } } & { - \omega _ { x } } & { 0 } \end{array} \right] \left[ \begin{array} { c c c c } { q _ { 0 } } \\ { q _ { 1 } } \\ { q _ { 2 } } \\ { q _ { 3 } } \end{array} \right] , } \end{array}
$$

$$
\begin{array} { r } { \dot { q } = \frac { 1 } { 2 } * \emptyset _ { w } * q . } \end{array}
$$

通过三轴陀螺仪测量的3个轴的角速度就可以实现实时更新四元数的值，进而更新姿态角获得姿态信息。

# 2四元数卡尔曼滤波（EKF）

在四元数和非线性滤波算法的结合中，最常用的算法就是基于四元数卡尔曼滤波，本文中使用文[1]的四元数卡尔曼滤波，滤波过程简介如下：

(1)滤波器初始化

为 $Q$ 和 $R$ 选取初始值，可以通过对静态下三轴陀螺仪、三轴加速度计和三轴磁力计进行测量，计算出各个轴的方差作为滤波器数据误差；并通过初始加速度计测量出俯仰角和横滚

C hinaXiv合作期刊

角，并用磁力计测量出方位角作为初始姿态，并把初始姿态角转变为初始四元数 $q _ { 0 / 0 }$ ，选择Po/o =I4作为系统初始噪声。

(2)状态方程传播

$$
\Omega _ { k } ^ { b } = \overline { { H } } \big ( \omega _ { k q } ^ { b } \big ) ,
$$

$$
\begin{array} { r } { \phi _ { k + 1 / k } = \exp { \left( \frac { 1 } { 2 } \ast \varOmega _ { k } ^ { b } \ast \Delta t \right) } , } \end{array}
$$

$$
q _ { k + 1 / k } = \Phi _ { k + 1 / k } * q _ { k / k } ,
$$

$$
M _ { k / k } = q _ { k / k } q _ { k / k } ^ { T } + P _ { k / k } ^ { q } ,
$$

$$
\begin{array} { r } { P _ { k + 1 / k } ^ { q } = \phi _ { k + 1 / k } P _ { k / k } ^ { q } \phi _ { k + 1 / k } ^ { T } + \frac { 1 } { 4 } \big [ t r \big ( M _ { k / k } \big ) I _ { 4 } - M _ { k / k } \big ] Q _ { k } . } \end{array}
$$

(3)量测方程更新

首先通过预测得到的 $q _ { k + 1 / k }$ 应用（4）式计算出观测方程中的系数矩阵 $\mathrm { H } { \left( q _ { k + 1 / k } \right) }$

$$
\boldsymbol { M } _ { k + 1 / k } = \boldsymbol { q } _ { k + 1 / k } \boldsymbol { q } _ { k + 1 / k } ^ { T } + \boldsymbol { P } _ { k + 1 / k } ^ { q } ,
$$

$$
\begin{array} { r } { P _ { k + 1 / k } ^ { v } = \frac { 1 } { 4 } R _ { k + 1 } \big [ t r \big ( M _ { k + 1 / k } \big ) I _ { 4 } - M _ { k + 1 / k } - B _ { k + 1 } M _ { k + 1 / k } B _ { k + 1 } ^ { T } \big ] , } \end{array}
$$

$$
S _ { k + 1 / k } = H { \left( q _ { k + 1 / k } \right) } * P _ { k + 1 / k } ^ { q } * H { \left( q _ { k + 1 / k } \right) } ^ { T } + P _ { k + 1 / k } ^ { v } ,
$$

$$
K _ { k + 1 } = P _ { k + 1 / k } ^ { q } * H \bigl ( q _ { k + 1 / k } \bigr ) ^ { T } * S _ { k + 1 / k } ^ { - 1 } ,
$$

$$
q _ { k + 1 / k + 1 } = q _ { k + 1 / k } + K _ { k + 1 } \bigl [ b _ { k + 1 } - H \bigl ( q _ { k + 1 / k } \bigr ) * n _ { k + 1 } \bigr ] ,
$$

$$
\begin{array} { r } { P _ { k + 1 / k + 1 } ^ { q } = \left( I _ { 4 } - K _ { k + 1 } H \big ( q _ { k + 1 / k } \big ) \right) P _ { k + 1 / k } ^ { q } . } \end{array}
$$

# 3粒子滤波

粒子滤波是通过寻找一组在状态空间中传播的随机样本近似表示状态变量，用样本均值代替积分运算，进而获得系统最小方差的过程，这些样本被称为粒子。采用数学语言描述如下：对于平稳的随机过程，假设 $k { - } 1$ 时刻系统的后验概率为 $p ( x _ { k } { - } 1 | z _ { k } { - } 1 )$ ，依据一定原则选取 $\mathbf { \Omega } _ { n }$ 个随机样本， $k$ 时刻获得测量更新后，经过状态和时间过程， $\boldsymbol { \mathbf { \mathit { \Pi } } } _ { n }$ 个粒子的后验概率密度可近似为 $p ( \boldsymbol { x } _ { k } | \boldsymbol { z } _ { k } )$ ，随着粒子数目的增加，粒子的概率密度函数逐渐逼近状态的概率密度函数，从而粒子滤波达到最优贝叶斯估计的效果‘。

假设非线性动态离散系统为

$$
\left\{ \begin{array} { l l } { x _ { k + 1 } = f _ { k } { \big ( } x _ { k } , ~ w _ { k } { \big ) } } \\ { z _ { k } = h _ { k } { \big ( } x _ { k } , ~ v _ { k } { \big ) } } \end{array} \right.
$$

其中， $x _ { k } \in R ^ { n }$ 为k时刻的 $\mathbf { \Omega } _ { n }$ 维状态向量； $z _ { k } \in R ^ { m }$ 为 $\boldsymbol { \mathit { m } }$ 维观测向量； $w _ { k }$ 和 $v _ { k }$ 分别为过程噪声

C hinaXiv合作期刊

和量测噪声。

粒子滤波算法步骤如下：

(1) 初始化： $k = 0$ 时，产生服从初始概率密度 $p ( x _ { 0 } )$ 的 $N$ 个粒子点 $x _ { 0 } ^ { ( i ) } , i = 1 \cdots n$ (2) 通过重要性采样更新样本粒子状态，

$$
\begin{array} { l } { { \overline { { { x } } } _ { k } ^ { \left( i \right) } { \sim } { \sf q } \left( x _ { k } \middle \vert x _ { 0 : k - 1 } ^ { \left( i \right) } , z _ { 1 : k } \right) \quad \mathrm { ~ , ~ } } } \\ { { \overline { { { x } } } _ { 0 : k } ^ { \left( i \right) } = \left( x _ { 0 : k - 1 } ^ { \left( i \right) } ; \overline { { { x } } } _ { k } ^ { \left( i \right) } \right) , i = 1 \cdots N \quad \mathrm { ~ . ~ } } } \end{array}
$$

(3） 计算更新后粒子的权值

$$
w _ { k } ^ { ( i ) } = w _ { k - 1 } ^ { ( i ) } \frac { p \Big ( z _ { k } \Big | x _ { k } ^ { ( i ) } \Big ) p \Big ( x _ { k } ^ { ( i ) } \Big | x _ { k - 1 } ^ { ( i ) } \Big ) } { q \Big ( x _ { k } ^ { ( i ) } | x _ { 0 : k - 1 } ^ { ( i ) } , z _ { 1 : k } \Big ) } .
$$

(4） 归一化粒子权值

$$
w _ { k } ^ { ( i ) } = w _ { k } ^ { ( i ) } / \sum w _ { k } ^ { ( i ) } .
$$

(5） 重采样：根据各自归一化权值 $w _ { k } ^ { ( i ) }$ 的大小复制/舍弃样本，得到 $N$ 个近似服从（204号 $\mathfrak { p } \left. \left( x _ { 0 : k } ^ { ( i ) } \right) \Big | z _ { 1 : k } \right.$ 分布的样本 $\boldsymbol { \cdot } \boldsymbol { x } _ { 0 : k } ^ { ( i ) }$ ， $\begin{array} { r } { \tilde { { \mathbf { \rho } } } _ { k } ^ { \left( i \right) } = \frac { 1 } { N } , i = 1 \cdots N } \end{array}$ （204

(6） 输出结果：算法的输出是粒子集 $\left\{ x _ { 0 : k } ^ { ( i ) } , i = 1 \cdots N \right\}$ ，用它可以表示后验概率和函数$\mathbf { g } ( x _ { 0 : k } )$ 的期望：

$$
\begin{array} { r } { \mathrm { p } ( x _ { 0 : k } | z _ { 1 : k } ) = \frac { 1 } { N } \sum \delta x _ { 0 : k } ^ { ( i ) } ( d x _ { 0 : k } ) , } \end{array}
$$

$$
\begin{array} { r } { \mathrm { E } \big ( \mathrm { g } ( x _ { 0 : k } ) \big ) = \frac { 1 } { N } \sum g _ { k } ( x _ { 0 : k } ^ { ( i ) } ) . } \end{array}
$$

(7） 令 $k = k + 1$ ，重复以上步骤。

# 4数据实验

实验通过选择传感器模块 $\mathrm { \ m p u 9 2 5 0 }$ 模块，它包含三轴陀螺仪、三轴加速度计和三轴磁力计，能够通过自身所有的低通滤波器和 $\mathrm { A / D }$ 变换模块直接输出九轴传感器数据。实验通过将mpu6050 固定在转台上测量，在安装过程中远离环境磁场的干扰。采用单片机读取 mpu9250测量数据后通过I2C串口传输给电脑进行 matlab 处理，以检验算法的可用性和精度。

(1)首先将传感器模块mpu9250 在静止状态下测量输出数据数据，采样速率为 $1 0 0 \mathrm { H z }$ ，采样1分钟，分析静态情况下的九轴输出数据。陀螺仪三轴静态数据如图1。

C hinaXiv合作期刊

![](images/116536900ed2e832f32ccfe5ea3733a262b1d7c6ca42a1f49f7a64ae0c846ac0.jpg)  
图1陀螺仪三轴静态输出数据

Fig.1Three-axis gyroscope static output data

图1是1分钟采集的陀螺仪三轴数据，自上而下依次是下 $\boldsymbol { \mathscr { X } }$ 轴 $\setminus { \boldsymbol { y } }$ 轴和 $z$ 轴，运用MATLAB软件分析其 $\boldsymbol { \mathscr { X } }$ 轴均值和方差分别为：0.0205（°）/s和 $1 . 2 3 8 \mathrm { e } ( - 4 )$ （°）/s； $y$ 轴均值和方差分别为:-0.0048（°）/s和 $1 . 5 7 \mathrm { e } ( - 4 )$ (）/s; $z$ 轴的均值和方差为:0.0154（°)/s 和2.3699e(-4)（°） /s;

用同样的方法处理三轴加速度计和三轴陀螺仪的原始数据，结果见表1。

表1加速度计和陀螺仪输出数据的均值和方差  
Table 1.mean and variance of accelerometer and gyro output data   

<html><body><table><tr><td rowspan="2"></td><td colspan="3">三轴加速度计（g)</td><td colspan="3">三轴磁力计（uT)</td></tr><tr><td>X轴</td><td>Y轴</td><td>Z轴</td><td>X轴</td><td>Y轴</td><td>Z轴</td></tr><tr><td>均值</td><td>0.4</td><td>-0.5</td><td>9.4</td><td>3.6</td><td>4.5</td><td>2.1</td></tr><tr><td>方差</td><td>0.0027</td><td>0.0033</td><td>0.0031</td><td>0.02</td><td>0.096</td><td>0.01</td></tr></table></body></html>

通过以上测量，加速度计在水平位置 $\boldsymbol { \mathscr { X } }$ 轴和 $y$ 轴均值不为零，所以在做姿态解算时引入均值误差提高测量精度。

（2） 通过上面静态数据的读取，将各个传感器的方差作为四元数卡尔曼滤波和粒子滤波程序的方差参考，静止状态下四元数卡尔曼滤波和粒子滤波的姿态角结算误差如图2、图3。

C hinaXiv合作期刊

0.5 0   
-0.5 0 10 20 30 40 50 60   
0.4 0   
-0.4 0 10 20 30 40 50 60   
-0.2 0 10 20 30 40 50 60

![](images/930ec305c091d8ceba7d4a7f73fce016dd9a8ee456f2b725bcc3c06e453f8f6a.jpg)  
图2四元数卡尔曼滤波静态三轴姿态角误差   
Fig2. QuaternionKalman filterstatic triaxialatitudeangle error   
图3粒子滤波静态三轴姿态角误差

Fig3.particle filterstatic triaxialattitudeangle error 静止状态下四元数卡尔曼滤波和粒子滤波三轴姿态角均值和误差如表2。

表2静止状态两种算法的均值和方差  
Table 2.Mean and variance of the two algorithms for the quiescent state   

<html><body><table><tr><td rowspan="2"></td><td colspan="3">四元数卡尔曼</td><td colspan="3">粒子滤波</td></tr><tr><td>X轴</td><td>Y轴</td><td>Z轴</td><td>X轴</td><td>Y轴</td><td>Z轴</td></tr><tr><td>均值</td><td>0.002</td><td>0.0036</td><td>0.0027</td><td>-0. 0337</td><td>0.0369</td><td>0.0016</td></tr><tr><td>方差</td><td>0.0106</td><td>0.0087</td><td>0.0101</td><td>0. 0143</td><td>0.0024</td><td>0.0045</td></tr></table></body></html>

通过对静态数据的分析可以看出，两种算法在均值改善上基本差不多，但是粒子滤波比四元数卡尔曼滤波在方差上有所改善，即粒子滤波在静态测量相对稳定。

（3）由于没有转台等实验设备，通过对静态数据上添加一个稳定的姿态仿真轨迹计算四元数卡尔曼滤波和粒子滤波在动态情况下的结算结果。通过对三轴姿态角分别添加

ChinaXiv合作期刊

角速率为2，3，5（）/s，和幅度为5仿真，得到如图4的仿真结果。

0.5   
-0.5 0 10 20 30 40 50 60   
0.5   
-0.5 0 10 20 30 40 50 60   
0.5   
-0.5 0 10 20 30 40 50 60

表3仿真状态两种算法的均值和方差  
Table 3 The mean and variance of the two algorithms for Simulation states   

<html><body><table><tr><td rowspan="2"></td><td colspan="3">四元数卡尔曼</td><td colspan="3">粒子滤波</td></tr><tr><td>X轴</td><td>Y轴</td><td>Z轴</td><td>X轴</td><td>Y轴</td><td>Z轴</td></tr><tr><td>均值</td><td>0.0301</td><td>0.0201</td><td>0.0254</td><td>-0.0347</td><td>0.0180</td><td>0.0204</td></tr><tr><td>方差</td><td>0.014</td><td>0.0095</td><td>0.0134</td><td>0.0161</td><td>0.0050</td><td>0.0085</td></tr></table></body></html>

通过对动态的仿真实验分析可以看出，两种算法在均值改善上和静态数据基本相同，但是粒子滤波比四元数卡尔曼滤波在方差上有所改善，即动态情况下粒子滤波相对四元数稳定。

# 5结论

本文通过对四元数卡尔曼滤波和粒子滤波进行简单介绍，并通过对mpu9250进行数据采集和仿真实验，验证粒子滤波和四元数卡尔曼滤波的可行性，通过以误差均值和标准差为检验标准，验证了粒子滤波相对于四元数卡尔曼滤波提高了标准差。

# 参考文献

[1]ChoukrounD,Bar-Itzhack I Y,Oshman Y.Novel quaternion Kalman filter [J]．IEEETransactions on Aerospace and Electronics Systems,2006，42(1):174-190.[2] 高显忠,侯中喜，王波，等.四元数卡尔曼滤波组合导航算法性能分析[J].控制理论与应用，2013,30(2):171-177.

Gao Xianzhong,HouZhongxi,Wang Bo,et al.Quaternion-based Kalman filter and its performance analysis in integrated navigation[J].Control Theory & Applications,2013,30(2):171-177.

[3] 梁军.粒子滤波算法及其应用研究[D].哈尔滨：哈尔滨工业大学,2009.[4] 乔相伟,周卫东,吉宇人.基于四元数粒子滤波的飞行器姿态估计算法研究[J].兵工学

ChinaXiv合作期刊报,2012,33(9):1070-1075.

QiaoXiangwei,Zhou Weidong,Ji Yuren.Study on aerial vehicle atitude estimation based on quaternion particle filter algorithm[J].ActaArmamentarii,2012,33(9):107O-1075. [5] 吴海亮,王惠南,陈志明，等.基于粒子滤波的微小卫星姿态确定算法[J].中国惯性技术学报， 2007， 15(4):427-430. WuHailiang，Wang Huinan，Chen Zhiming，etal.Particlefiltering-based algorithmfor micro-satellteattude determination[J].Journal of Chinese Inertial Technology，2007，15（4)：427-430.

# Application of nonlinearfiltering in SINS

YU Shao-shao,PEI Jun，HU Chao

(University of Chinese Academy of Science，National Astronomical Observatory,Beijing)

Abstract: Two algorithms are presented to solve the carrier attitude and rate estimation problem. One is based on Kalman filter and the otheris based on Particle filter.In order to avoid the singular problem from Euler angle,we chooses quaternion to describe the attitude angle. We carried out the data acquisition of gyroscope, accelerometer and magnetometer of mpu9250 module.By compared with the experimental data and simulation, we dicusse the feasibility of quaternion Kalman filter and particle filter algorithm. The results of static and dynamic simulation show that the error of the particle filter and the Kalman filter is similar when the carrier atitude is measured by the MEMS device,and the standard deviation of the particle filter is relatively small.

Key words： Quaternion；Kalman filter；Particle filter；Atitude estimation

基金项目：  
国家自然科学基金资助项目（11603041）资助【The National Natural Science  
Foundation of China （11603041)】  
项目编号：11603041  
Fund Code: 11603041

作者介绍：鱼少少，（1992一）男，硕士，研究方向为卫星通信与导航;

联系方式：  
电话：18810981716  
北京朝阳区大屯路甲20号国家天文台B130 室鱼少少收  
邮政编码：100012  
E-mail: 1024636930@qq.com