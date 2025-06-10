# 一种改进的电动汽车用异步电机参数离线辨识方法研究

史文凡」贾洪平} 颜建虎²于杏²（1.江苏大学电气信息工程学院镇江 212000 )（2.南京理工大学自动化学院南京210094）

![](images/4abf63fb208bfb2aa9a5b269162841f23f89c6c522c4aa3539e9e6a00a8f33b9.jpg)

史文凡男 1989年生，硕士研究生，研究方向为异步电机控制技术研究。

摘要：本文提出了一种异步电机参数离线辨识的改进算法。对传统直流实验进行改进，得到等效的控制电路来完成定子电阻的辨识。然后利用单相交流堵转实验来辨识定子漏感和转子电阻。在Vf空载实验中，采用计算无功功率来辨识电机互感的方法，避免了传统空载实验中复杂的FFT计算过程。最后，在一台额定功率为 $3 . 5 \mathrm { k W }$ 的异步电机上进行了参数辨识的仿真与实验研究。结果表明，本文所提出的方法在工程应用中简易可行，辨识得到的电机参数具有较高的准确性。

关键词：异步电机参数离线辨识矢量控制无功功率中图分类号：TM921

# AnImproved Off-Line Identification Method of Asynchronous Motor Parameters for Electric Vehicles

![](images/f0e480935359521fe8bc1d71a41cf772b691cf05cba3d15f7539455e76d7757f.jpg)

Shi Wenfan'Jia Hongpingl Yan Jianhu² Yu Xing² （1.Jiangsu UniversityZhenjiang212000 China ） ( 2. Nanjing University of Science and TechnologyNanjing 210094 China）

贾洪平男1972年生，副教授，研究方向为异步电机驱动控制。

Abstract: This paper presents an improved algorithm for off-line identification of asynchronous motor parameters. The traditional DC experiment is improved to obtain the equivalent control circuit to realize the stator resistance identification.And then the singlephase AC locked rotor experiment is used to identify the stator leakage inductance and rotor resistance.In the $\mathrm { V / f }$ no load experiment, the motor mutual inductance is identified by calculating the reactive power to avoid the complex FFT calculation in the traditional no-load experiments.Finally the simulation and experiment of parameter identification areimplementedfor a $3 . 5 \mathrm { k W }$ asynchronous motor respectively. The results show that this presented method is simple and feasible in engineering control application and has higher precision.

Keywords: Asynchronous motor, parameter offline identification, vector control, reactive power

# 1 引言

异步电机具有结构简单、制造方便、成本低廉，且坚固耐用、运行可靠、可用于恶劣环境等优点，被广泛应用于电动汽车驱动系统中[1]。异步电机控制系统中具有代表性的方法有：开环Vf控制、转差频率控制、矢量控制和直接转矩控制等，其中矢量控制技术应用最为广泛，它使异步电机可以实现较宽的转速范围、较大的输出瞬时功率和较快的转矩响应速度。但在矢量控制中，转子磁链角的估算、速度环和电流环中PI调节器的参数自整定对电机参数的精度均有较高要求[2]。

异步电机的主要参数包括定子电阻、转子电阻、定子漏感、转子漏感和定转子之间互感。目前，异步电机的参数辨识主要分为离线和在线辨识[3]。在线辨识的算法主要有神经网络算法、遗传算法等。以上方法能对电机参数进行实时整定，提高控制系统的精度，但同时存在一定的缺点。如扩展卡尔曼滤波法需要给定系统噪声且算法较为复杂；遗传算法难以处理非线性约束，稳定性较差，所以在线辨识在实际应用中非常困难[4-8]。离线辨识的传统方法是空载实验和堵转实验[9]，它能准确地测量电机参数，但由于受到现场条件的限制，不适合变频调速系统。基于此，学者们提出了许多离线自动辨识方法[1-15]，文献[11]采用脉冲电压法和脉冲电流法,但数据处理方法略显复杂。文献[12]基于间接矢量控制系统进行参数辨识，对直流实验做了一些改进，但总漏感通过估算得到，因此会引入积累误差。文献[13]在空载实验时提出转差频率控制，能消除开环时可能出现的电流振荡，但需要加入定子电压传感器。文献[14]采用阶跃电压试验来消除漏感，可以消除总漏感的积累误差，但增加了测试的复杂度。文献[15]在电压重构时根据电流极性来补偿逆变器死区引起的电压误差，但计算量大。

本文在现有方法的基础上，提出了一种基于无功功率计算的异步电机定转子互感参数离线辨识方法，避免了传统互感辨识方法复杂的FFT计算过程。最后，对一台 $3 . 5 \mathrm { k W }$ 的异步电机进行仿真和实验研究，结果证明该方法具有较高的准确性和有效性。

# 2 参数离线辨识

图1为异步电机驱动系统主电路，其中逆变器的三对桥臂A、B、C分别与异步电机M的三相定

子绕组相连。

c↓K本νK本本B MC=νK本νK本K本

# 2.1 直流实验

定子电阻 $R _ { \mathrm { s } }$ 辨识一般通过直流实验来完成。通常采用图2a所示结构，本文在此方法上加以改进，将图1中 $\mathrm { V T } _ { 1 }$ ， $\mathrm { V T } _ { 5 }$ 导通，其余关断来得到图2b所示结构。

![](images/79257d0c4fa44072373b329f47cd90941bc818a4f6a7578134a65246cbeb409c.jpg)  
图1异步电机变频调速主电路  
Fig.1Main circuit of variable frequency control system of asynchronous motor   
图2直流实验等效电路  
Fig.2Equivalent circuit of DC test

由于本文采用逆变器供电，不能直接在电机上施加直流电压，所以采用PWM斩波的方式来调节施加在电机上的电压值。通过控制6个功率管$\mathrm { V T } _ { 1 } \sim \mathrm { V T } _ { 6 }$ 的开关状态来实现定子电阻辨识。PWM斩波的占空比是A相上桥与B相下桥的占空比之差$N _ { \ast }$ 。根据设定允许通过的最大电流来相应地改变B相的占空比，使回路电流达到设定值。

为了使计算精确，待电流稳定一段时间后，对电机的线电压和线电流进行累加，分别记为 $U _ { \mathrm { a b } }$ 和$I _ { \mathrm { a } }$ ，最后根据式（1）计算定子电阻。

$$
R _ { \mathrm { s } } = { \frac { N U _ { \mathrm { { a b } } } } { 2 I _ { \mathrm { { a } } } } }
$$

# 2.2单相实验

转子电阻 $R _ { \mathrm { r } }$ 和定、转子漏感 $L _ { \mathrm { l s } }$ 辨识可以通过对电机施加单相交流激励来完成。等效电路如图3a所示。通常异步电机定、转子漏感相对于互感而言很小，并且近似相等，因此当给定电流频率较高时，可以将电路等效为如图3b所示。

![](images/43e50104df7b9d87f0c60d937f33f8ef2a13d929e65dc37c35d8f35870b3f6e9.jpg)  
图3单相实验等效电路

在两相静止坐标系上，令 $U _ { \beta } = 0$ ，可以保证图1中B、C两相的控制信号相同，即使B、C两相短接，此时电机相当于堵转状态。并将给定电流 $\boldsymbol { I } _ { \mathrm { a } } ^ { * }$ 与反馈得到的相电流 $I _ { \mathrm { a } }$ 经过比例调节 $K _ { \mathfrak { p } }$ 后得到 $U _ { \mathrm { { a } } }$ VSI为电压源逆变器。其控制框图如图4所示。

![](images/42cd720bdabebbe74afab2876b9dc030195eaa17c58605c080d9f506940955e0.jpg)  
Fig.3Equivalent circuit of single-phase test

其中电流给定为

$$
\boldsymbol { I } _ { \mathrm { a } } ^ { * } = \sqrt { 2 } \boldsymbol { I } \cos { ( \omega _ { \mathrm { e } } ^ { * } t ) }
$$

式中， $\omega _ { \mathrm { ~ e ~ } } ^ { * }$ 为给定定子电流角频率； $I$ 为电机额定线电流的有效值。

待电流稳定后，对A相和B相之间的线电压和A 相的相电流进行傅里叶变换 (FFT)，分别得到其基波幅值 $U _ { \mathrm { a b } }$ 和 $I _ { \mathrm { a } }$ ，同时得出基波电压和电流之间的相位差 $\theta$ 。

计算得等效阻抗为

$$
Z _ { \mathrm { e q } } = { \frac { U _ { \mathrm { a b } } } { I _ { \mathrm { a } } } }
$$

等效电阻为

$$
R _ { \mathrm { e q } } = Z _ { \mathrm { e q } } \cos \theta
$$

等效电抗为

$$
X _ { \mathrm { e q } } = Z _ { \mathrm { e q } } \sin { \theta }
$$

转子电阻为

$$
R _ { \mathrm { r } } = { \frac { 2 } { 3 } } R _ { \mathrm { e q } } - R _ { \mathrm { s } }
$$

定、转子漏感为

$$
L _ { \mathrm { l s } } = L _ { \mathrm { l r } } = { \frac { X _ { \mathrm { e q } } } { 3 \omega _ { \mathrm { e } } ^ { * } } }
$$

# 2.3空载试验

互感 $L _ { \mathrm { m } }$ 辨识可以通过空载实验来完成。空载实验采用恒Vf方式实现，此时电机转速接近于同步转速，转差率 $s \approx 0$ ，定子电流基本上等于励磁电流，电机的转子回路相当于开路。等效电路如图5所示，控制框图如图6所示，其中， $\boldsymbol { f } ^ { * }$ 为给定频率；ramp 为平滑变频模块。

![](images/4c384b1da11ea588067705e9895cdf4ca26553dde8a0c1af8da13aaee1fcee45.jpg)  
Fig.4Control diagram of single-phase test   
图5空载实验等效电路

![](images/612923da70a963a221ba89227c757210fad4dd165f12114ea856f2a8be72d932.jpg)  
图4单相实验控制框图  
Fig.5Equivalent circuit of no-load test   
图6空载实验控制框图  
Fig.6Control diagram of no-load test

待转速稳定后，通过测得的相电压和相电流经过Clarke变换来计算出 $U _ { \mathrm { a } }$ ， $U _ { \beta }$ ， $I _ { \mathrm { { a } } }$ ， $I _ { \beta }$ 的值，从而可以求出此时电路的无功功率 $\varrho$ 。由于定子漏感相对于互感而言很小，计算时可以忽略，所以可以通过式（9）来计算出互感的值。

$$
Q = I _ { \mathrm { s } } ^ { 2 } \omega L _ { \mathrm { m } }
$$

$$
L _ { \mathrm { m } } = \frac { \mathcal { Q } } { I _ { \mathrm { s } } ^ { 2 } \omega }
$$

式中， ${ \cal I } _ { \mathrm { s } } ^ { 2 } = { \cal I } _ { \mathrm { a } } ^ { 2 } + { \cal I } _ { \mathrm { \beta } } ^ { 2 }$ $\omega$ 为电压、电流的同步角频率。

# 3 仿真研究

为了验证本文电机参数离线辨识方法的准确性，首先采用了Matlab/Simulink对该系统进行了仿真研究。仿真模型中所选电机为额定电压 $7 2 \mathrm { V }$ 、额定频率 $1 0 0 \mathrm { H z }$ 、额定功率 $3 . 5 \mathrm { k W }$ 的异步电机。

# 3.1直流实验仿真

图7为直流实验仿真波形图，由图7a得出 $U _ { \mathrm { a b } }$ 累加值为 $4 5 \mathrm { V }$ ，图7b中 $I _ { \mathrm { a } }$ 由于定子漏感的存在而延迟一段时间才能达到稳态值，累加值最终稳定在710A，最后仿真计算得到定子电阻为 $0 . 0 3 0 \ 2 \Omega$ 。

# 3.2单相实验仿真

图8为单相实验仿真波形图，可以看出经过FFT计算后， $U _ { \mathrm { a b } }$ 的幅值为 $5 . 8 \mathrm { V }$ ， $I _ { \mathrm { a } }$ 的幅值为47A,最后仿真得到的转子电阻为 $0 . 0 4 7 \ 3 \Omega$ ，漏感为$0 . 0 4 9 \mathrm { m H }$ 。

![](images/ce44d0ebdd457aa06d3d65469be0bb830653ac28a3f238bfb2540c2ac21e20c7.jpg)  
(b) $I _ { \mathrm { a } }$ 的累加值波形

![](images/6e1598c3764f6bbbc8a254f95f10d1d3d512182337606d855ec3c893ecded322.jpg)  
图7直流实验仿真波形

![](images/035127e65c85e7507948455bde349cb3da6921ae8bff4f402ea13cb787ad46c9.jpg)  
Fig.7Simulation waveforms of DC test   
  
Fig.8Simulation waveforms of single-phase test

# 3.3空载实验仿真

图9所示为Vf空载实验得出的电机互感波形。电机转速稳定后，仿真得到的定、转子之间互感为$1 . 2 2 5 \mathrm { m H }$ 。

![](images/febd9ad82795df51bf1cf2c623339516d704d5087ddd317ebdf20884e0ce2910.jpg)  
图9空载实验仿真波形

# 4 实验研究

本实验平台是以TI公司生产的DSP芯片TMS320F28035为核心的控制平台，实验电机额定功率为 $3 . 5 \mathrm { k W }$ ，额定电压为 $7 2 \mathrm { V }$ ，额定频率 $1 0 0 \mathrm { H z }$ 的异步电机。

# 4.1定子电阻辨识

在定子电阻辨识实验中，使图1中的 $\mathrm { V T } _ { 1 }$ 和$\mathrm { V T } _ { 5 }$ 闭合，其余功率管关断。待电流稳定后，开始采样电机的线电压 $U _ { \mathrm { a b } }$ 和线电流 $I _ { \mathrm { a } }$ ，共采集514次，最后利用式（1）计算定子电阻 $R _ { \mathrm { s } }$ 。图10a为直流实验时A相上桥和B相下桥波形；图10b为累加的线电流波形。

# 4.2转子电阻与漏感辨识

在单相交流堵转时，其A相给定电流幅值为180A，给定频率为 $7 8 \mathrm { { H z } }$ 。待电流稳定后，通过FFT变换得到 $U _ { \mathrm { a b } }$ ， $I _ { \mathrm { a } }$ 的幅值和其相位差 $\theta$ ，最后利用式（3）～式（7）计算转子电阻和漏感。图11为单相实验中A相电流和A、B相之间线电压的波形。

![](images/e637445f1cfa3e62e002ae5bb2abf3e4ced2ac80a1fad821c259d8b3c7e17369.jpg)  
(a）A相上桥与B相下桥的波形  
Fig.10Experimental waveforms ofDC test

Tek Stop MPos:1.600ms CH3CL 耦带宽限制送100MHz伏/格粗调探头10XVoltage反相关闭  
CH110.0A M2.50ms CH3/43.3mV24-Feb-1715:49 <10Hz(b）电流 $I _ { \mathrm { a } }$ 的波形

![](images/fcdf890ea8d9f61c30eb36ffe288b3fd5ddda42a6ec603444f0f16d72656a9cc.jpg)  
Fig.9Simulation waveform of no-load test   
图10 直流实验波形  
图11 单相实验波形  
Fig.11Experimental waveforms of single-phase test

# 4.3电机互感辨识

在Vf空载实验中，给定频率为 $1 0 0 \mathrm { H z }$ ，电压幅值为 $3 0 \mathrm { V }$ 。频率稳定后，通过采样三相电压和电流来进行Clarke变换，求出无功功率后利用式（9)求出电机互感。图12为空载实验A、B相电流波形。

# 4.4实验结果分析

下表给出了该实验所用电机的实际值、仿真值以及实验所测值。可以发现，在误差允许范围内实验测值与实际值之间存在微小误差，原因主要如下：

Tek 几 Stop M Pos:1.800ms CH1 耦合 B相电流 直流   
WWWF A相电流 反相 关闭   
CH1 20.0A CH220.0A M5.00ms CH3/217mV 24-Feb-1716:19 <10Hz

（1）在电压重构计算的过程中，存在死区和功率管管压降的影响。（2）求解过程中对电机模型作了相应的近似计算。

# 表离线辨识实验、传统实验与仿真结果

Tab.Results of off-line identification test、traditional tes1

and simulation   

<html><body><table><tr><td>电机参数</td><td>实际值</td><td>实验值</td><td>仿真值</td></tr><tr><td>R/Ω</td><td>0.0307</td><td>0.0298</td><td>0.0302</td></tr><tr><td>R/Ω</td><td>0.048</td><td>0.0476</td><td>0.0473</td></tr><tr><td>L15/mH</td><td>0.05</td><td>0.048</td><td>0.049</td></tr><tr><td>Lm/mH</td><td>1.268</td><td>1.276</td><td>1.225</td></tr></table></body></html>

# 5 结论

本文提出了一种异步电机参数离线辨识的改进算法，该法在辨识电机定、转子之间的互感时，采用了无功功率计算的方法，避免了FFT复杂的计算过程。最后对一台额定功率为 $3 . 5 \mathrm { k W }$ 的异步电机进行了仿真和实际实验，辨识过程由系统自动完成，并且能够辨识出电机的所有参数。通过对比电机参数的实际值、仿真值和实验值，证明本文方法具有较高的精度，在工程中具有很高的应用价值。

# 参考文献

[1] ZeraouliaM，BenbouzidME1H，Diallo D. Electricmotor drive selection issues for HEV propulsionsystems:a comparative study[J].IEEE Transactionson Vehicular Technology,2006,55(6): 1756-1764.   
[2] 王明渝，况成瑜，慧娅倩．感应电动机矢量控 制参数离线辨识技术[J]．电工技术学报，2006, 21(8):90-96. Wang Mingyu, Xian Chengyu, Hui Yaqian.An offline parameter estimation technique for vector controlled induction machine drive[J]. Transactions of China Electrotechnical Society, 2006, 21(8): 90- 96.   
[3] 陈康平，曾岳南，李海波，等．基于TMS320F2812 的异步电机参数离线辨识系统[J]．电机与控制应 用，2013，40(8)：5-8. Chen Kangping, Zeng Yuenan, Li Haibo, et al. System of off-line parameter identification for AC motor based on TMS320F2812[J]. Electric Machines & Control Application,2013,40(8): 5-8.   
[4] Toliyat H A,Wlas M,Krzemiriski Z. Neuralnetwork-based parameter estimations of induction motors[J]. IEEE Transaction on Industrial Electronics,2008, 55(4): 1783-1794.   
[5] Liaw C M,Wang JB, Chang Y C. A fuzzy adapted field-oriented mechanism for induction motor drive[J]. IEEE Transactions on Energy Conversion, 2006,11(1): 76-83.   
[6] Sundareswaran K, Shyam H N, Palani S,et al. Induction motor parameter estimation using hybrid genetic algorithm[C]. IEEE Region 10 and the Third International Conference on Industrial and Information Systems, Kharagpur, 2008: 1-6.   
[7] Suman M, Chandan C,Yoichi H,et al. Model reference adaptive controller-based rotor resistance and speed estimation techniques for vector controlled induction motor drive utilizing reactive power[J]. IEEE Transactions on Industrial Electronics,2008, 55(2): 594-601.   
[8] 金海，黄进．基于模型参考方法的感应电机磁链的 自适应观测及参数辨识[J]．电工技术学报，2006, 21(1): 65-69. Jin Hai, Huang Jin.Adaptive flux estimation and parameters identification of induction motors based on model reference approach[J]. Transactions of China Electrotechnical Society, 2006,21(1): 65-69.   
[9] 李建军，盛洁波，王翠，等．异步电机定转子 参数的辨识方法研究[J]．电工技术学报，2006, 21(1): 70-74. Li Jianjun, Sheng Jiebo,Wang Cui, et al. Research on parameter identification method for induction motor[J]. Transactions of China Electrotechnical Society,2006,21(1): 70-74.   
[10] 陈永飞，雷良育，胡烨，等.基于Ansoft电动汽车 用轮毂电动机电磁场分析[J].电气应用，2016，35 (3):77-82.   
[11] 余功军，钟彦儒，杨耕．无速度传感器矢量控 制系统中的电机参数辨识[J]．电气传动，1999， 29(1): 7-10. Yu Gongjun, Zhong Yanru, Yang Geng. Parameter identification of induction motor in sensor-less vector control inverter[J].Electric Drive,1999,29(1): 7-10.   
[12] LinY N,Chen CL.Automatic IM parameter measurement under sensorless field-oriented control[J]. IEEE Transactions on Industry Electronics, 1999,46(1): 111-118.   
[13] 刘洋，赵金，王庆义．间接矢量控制系统中的异步 电机参数辨识[J]．电工技术学报，2008，23(7)： 21-26. Liu Yang,Zhao Jin,Wang Qingyi.An off-line parameter identification method for indirect vector controlled induction motor drive[J]. Transactions of China Electrotechnical Society,2008,23(7): 21-26.   
[14] 罗慧，刘军峰，万淑芸．感应电机参数的离线辨识 [J]．电气传动，2006，36(8)：16-21. Luo Hui,Liu Junfeng,Wan Shuyun.Off-line identification of induction motor parameter[J]. Electric Drive,2006,36(8):16-21.   
[15] 贺艳晖，王跃，王兆安．异步电机参数离线辨识改 进算法[J]．电工技术学报，2011，26(6)：73-80. He Yanhui,Wang Yue,Wang Zhao'an.An improved off-line parameter identification algorithm for induction motors[J].Transactions of China Electrotechnical Society,2011,26(6): 73-80.