# 基于傅里叶变换色散条纹法的实验研究

党策1,2,3，姜爱民1,2.3，董志超1,²2，薛建伟1.2(1．中国科学院国家天文台,北京 100101；2．中国科学院空间天文与技术重点实验室,北京 100101;3．中国科学院大学，北京100049)

摘要：光干涉要求实现各光路共相位叠加，对于宽波带的白光干涉要求则更加苛刻。因此，要实现稳定的白光光干涉需要对光程进行实时探测和控制。本文对基于傅里叶变换的色散条纹法进行了理论推导、算法设计，并利用实验室建立的Fizeau型干涉实验装置开展开、闭环实验研究。在开环实验中，采集不同光程差的多幅色散条纹图像，研究了图像频谱次峰偏移量和光程差的关系，结果显示，偏移量与光程差之间呈现出良好的线性关系；在闭环实验中，利用光程差的实时计算结果和光程补偿机构，对光程差进行闭环控制，结果显示，在外加扰动的情况下，系统能够始终保持在初始的干涉状态。

关键词：光程探测；傅里叶变换；色散条纹法；控制中图分类号：P111.2 文献标识码： 文章编号：

光学综合孔径技术是将多个小口径的光学元件或系统以某种构型进行精确排列，使通过各子孔径的光束在焦平面上实现光场的相干叠加，经图像复原技术处理后，达到与单一大口径系统相当的衍射极限分辨率的技术。它可以突破单望远镜口径衍射极限的限制。

光学综合孔径望远镜按照拼接方式的不同，分为拼接主镜和拼接子望远镜两种形式。目前，世界各国已建立了多台拼接子望远镜形式的光学综合孔径望远镜。2002 年，美国麻省理工学院建立了白光自适应GOLAY-3型 ARGOS 望远镜[1，它由3个孔径为 21cm的子望远镜组成，角分辨率 $0 . 3 5 ^ { \prime \prime }$ ，光谱范围 $4 0 0 { - } 7 0 0 { \mathrm { n m } }$ ，视场为 $3 ^ { \prime } \times 3 ^ { \prime }$ ，等效口径 $0 . 6 2 \mathrm { { m } }$ ，信噪比100。美国洛克希德·马丁公司联合NASA、JPL 实验室、加州理工学院、加利福尼亚大学和罗切斯特大学，建立了空间多仪器口径分布式传感系统（MIDAS）[2]，该系统能够实现大视场、衍射极限成像，可以在 $5 0 0 0 \mathrm { k m }$ 高的轨道上进行对地观察，地面分辨率小于1m，也可以在 $1 0 0 \mathrm { k m }$ 高的轨道上进行高分辨率成像，地面分辨率达到2cm。

光学综合孔径望远镜在进行干涉成像时，必须实现光束的相干叠加，才能提高图像的空间分辨率。对于白光宽带成像系统，由于光源的相干长度非常小，相当于要求不同路径的光束实现零等光程干涉。因此，对光程差进行精确探测，就成为了实现光干涉的先决条件。

目前，国内外在光程探测领域已开展了大量的研究。出瞳面检测：四棱锥波前检测法通过探测出瞳处4个像点的能量差异计算光程差[3]。离焦面检测：相位恢复法通过焦面和离焦面的一对光强分布数据反解出各自的相位分布[4。焦面检测法：(1)窄带一哈特曼夏克法和宽带一哈特曼夏克法通过检测采样孔径衍射图样和“样板图样”的相关系数，计算拼接子镜间的光程差[5]。(2)色散条纹法通过检测所提取的相邻孔径之间的干涉条纹中横向光强信号，对其进行非线性最小二乘拟合，求解光程差[]。

为尽可能达到光程差探测范围大于 $\pm 5 0 \mu \mathrm { m }$ ，探测精度小于20nm的技术指标，并利用国家天文台空间天文技术实验室所建立的光学综合孔径原理样机系统，本文对基于傅里叶变换的色散条纹法进行了理论推导和算法设计，并开展了开环和闭环实验。在开环实验中，采集不同光程差的色散条纹图像，通过图像频谱次峰偏移量解算光程差，并与设定的光程差进行比对，验证方法的线性关系；在闭环实验中，对人为引入的光程差进行实时计算和闭环控制，观察系统对光程差变化的校正能力。

# 1理论基础

基于色散条纹法的焦平面光强分布表达式为[7]：

$$
I ( x , y ) = I _ { 0 } \Biggl [ 1 + \gamma \cdot \mathrm { c o s } \Biggl ( 2 \pi \cdot \frac { \phi } { \lambda ( x ) } + \varphi _ { 0 } ( y ) \Biggr ) \Biggr ]
$$

其中 $I _ { 0 }$ 为平均光强， $\gamma$ 为条纹对比度， $\phi$ 为光程差， $\lambda ( x ) = \lambda _ { 0 } + C _ { 0 } x$ ，其中 $\lambda _ { 0 }$ 为中心波长， $x$ （204号为色散方向， $C _ { 0 }$ 为线色散率， $\varphi _ { 0 } ( y )$ 为初相位。由于波数的表达式 $k ( x ) = \frac { 2 \pi } { \lambda ( x ) } = \frac { 2 \pi } { \lambda _ { 0 } + C _ { 0 } x }$ ，将该表达式进行1阶泰勒近似展开，得到 $k ( x ) \approx k _ { \mathrm { 0 } } - \frac { { k _ { \mathrm { 0 } } } ^ { 2 } C _ { \mathrm { 0 } } } { 2 \pi } x$ $k _ { \mathrm { { 0 } } } = \frac { 2 \pi } { \lambda _ { \mathrm { { 0 } } } }$ 将 $k ( x )$ 的1阶泰勒近似展开式带入(1)，可得：

$$
I ( x , y ) = I _ { 0 } \Biggl [ 1 + \gamma \cdot \mathrm { c o s } \Biggl ( ( k _ { 0 } - { \frac { { k _ { 0 } } ^ { 2 } C _ { 0 } } { 2 \pi } } x ) \cdot \phi + \varphi _ { 0 } ( y ) \Biggr ) \Biggr ]
$$

对式(2)进行二维傅里叶变换，得到：

$$
I _ { F } ( f _ { x } , f _ { y } ) = \int \int I ( x , y ) e ^ { [ - j 2 \pi ( x f _ { x } + y f _ { y } ) ] } d x d y
$$

由于表达式(2)中的余弦项可以用欧拉公式表达，因此 $I ( x , y )$ 中余弦项可表示为：

$$
\cos \Biggl ( ( k _ { 0 } - \frac { { k _ { 0 } } ^ { 2 } C _ { 0 } } { 2 \pi } x ) \cdot \phi + \varphi _ { 0 } ( y ) \Biggr ) = \frac { e ^ { \int _ { \left( k _ { 0 } - \frac { k _ { 0 } ^ { 2 } } { 2 \pi } x \right) \cdot \phi + \varphi _ { 0 } ( y ) } { 2 } } } { 2 } + \frac { e ^ { - j \left( ( k _ { 0 } - \frac { k _ { 0 } ^ { 2 } } { 2 \pi } x ) \cdot \phi + \varphi _ { 0 } ( y ) \right) } } { 2 }
$$

用式(4)来表示(2)中的余弦项，得到 $I ( x , y )$ 的二维频谱表达式：

$$
\begin{array} { l } { { { \displaystyle I _ { _ { F } } ( f _ { x } , f _ { y } ) = 2 \pi I _ { 0 } \cdot \delta ( f _ { x } , f _ { y } ) + \pi I _ { 0 } \gamma \cdot e ^ { - k _ { 0 } \phi j } \cdot \delta ( f _ { x } + \frac { C _ { 0 } k _ { 0 } ^ { ~ 2 } } { 2 \pi } \phi , f _ { y } - A ) } } } \\ { { { } } } \\ { { + \pi I _ { 0 } \gamma \cdot e ^ { k _ { 0 } \phi j } \cdot \delta ( f _ { x } - \frac { C _ { 0 } { k _ { 0 } } ^ { 2 } } { 2 \pi } \phi , f _ { y } + A ) } } \end{array}
$$

其中假设 $A$ 为两个次峰相对于 $\mathrm { ~ x ~ }$ 轴的偏移量。在 $I ( x , y )$ 的频谱中有三个峰，其中主峰位于(0,0)，  
两个次峰分别位于 $( - \frac { C _ { 0 } { k _ { 0 } } ^ { 2 } } { 2 \pi } \phi , A )$ $( \frac { C _ { 0 } { k _ { 0 } } ^ { 2 } } { 2 \pi } \phi , - A )$   
表达式为：

$$
d x = \frac { C _ { 0 } { k _ { 0 } } ^ { 2 } } { 2 \pi } \phi
$$

其中 $C _ { 0 }$ 和 $k _ { 0 }$ 均为常数，因此频谱次峰相对于y轴的偏移量 $d x$ 与光程差 $\phi$ 之间呈现出良好的线性关系，故可以用基于傅里叶变换的方法对色散条纹图像进行处理，从而求得光程差值。

# 2光程探测算法流程设计

基于色散条纹图像的光程探测算法流程如图1所示[8。首先，读取某一光程差下的干涉条纹图像，然后对其进行二维傅里叶变换，并求取幅值。得到频谱图像后，首先将主峰所在的区域全部置零，然后求取最大幅值所在的位置，此时所求得的就是两个次峰所在的位置。选取其中一个次峰，并确定该次峰相对于y轴的偏移量 $d x$ ，以该次峰所在位置为中心，进行亚像素精度拟合，设次峰位于 $( x , y )$ ，其幅值为 $F ( x , y )$ ，拟合式为[9]：

$$
d x ^ { \prime } = d x + \frac { 0 . 5 \cdot \lbrack F ( x - 1 , y ) - F ( x + 1 , y ) ] } { \lbrack F ( x - 1 , y ) + F ( x + 1 , y ) - 2 F ( x , y ) \rbrack }
$$

在此基础上，乘以一个比例系数就可以求得光程差值，比例系数可以通过计算得到也可由实验进行标定，至此，对于一幅干涉条纹图像的光程差求解过程结束。

![](images/b860c9e4bd8180d6f8200e52969855a0a866de4c2ee1a48d90a64aa3ae63d004.jpg)  
图1基于一幅图像的光程探测算法流程图  
Fig.1 Piston error detection algorithm flow based on one image

# 3光学综合孔径实验系统

国家天文台建立的Fizeau 型光学综合孔径实验装置由光源系统、子望远镜系统、指向探测和补偿系统、光程探测和补偿系统、合光成像及处理系统5部分组成，见图 $2 ^ { [ 1 0 ] }$ 。其电子学系统由图像分发板、3块计算控制板、数模输出板、模拟电源板、数字电源板和接口底板共8块板卡组成，见图3。在开环实验中，采集色散条纹的系列图像，利用MATLAB求解光程差。在闭环实验中，利用电子学系统，基于Visual $\mathrm { D s p + + 5 . 0 }$ 开发TS201的程序，进行光程差的实时探测及控制。

在实验中，光源系统均采用NKTPhotonics 公司的 SuperKEXTREME系列高功率超连续白光光源，其滤光器输出光谱范围为 $4 0 0 \mathrm { n m }$ 至 $7 0 0 \mathrm { n m }$ ，具有波段中心、波段宽度、输出功率可调的特点。光源望远镜是典型的卡塞格林望远镜，具有 $5 0 0 \mathrm { m m }$ 通光孔径，20m焦距，大于2arcmin的视场角，F#/40。子望远镜系统由3路子望远镜组成，采用反射式无焦系统，放大率为5，基线长度200mm，入射光束口径 $1 0 0 \mathrm { m m }$ ，出射光束口径 $2 0 \mathrm { { m m } }$ ，系统组合焦距4500mm。为保证经子望远镜1#,2#,3#的三路光束可进行相干成像，光程探测模块内设置2个光程探测望远镜，以子望远镜1#为基准，分别对1#，2#和1#，3#进行光程探测并解算出光程差值，最终达到控制 3路光束间光程差的目的。其中1#，2#和1#，3#间的两路光束经光程探测模块内的 Amici 色散棱栅以及光程探测望远镜后，在焦面上形成色散干涉条纹。光程补偿模块分为粗调平台与精调平台，如图4所示。在开环实验中，利用光程补偿组件中的粗调平台（PI公司的M-122微位移平台）调整运动反射镜的位置改变光学延迟线的大小，从而得到不同光程差下的干涉条纹图像。M-122 微位移平台以线性编码器作为集成传感器，行程 $2 5 \mathrm { m m }$ ，分辨率 $0 . 1 \mu \mathrm { m }$ ，最小位移 $0 . 2 \mu \mathrm { m }$ 最大速度 $2 0 \mathrm { m m / s }$ 。在闭环实验中，利用光程补偿组件中的精调平台（PI公司的P-753 促动器)，对光程差进行精补偿。P-753促动器带有电容式集成传感器，行程 $1 2 \mu \mathrm { m }$ ，分辨率 $0 . 0 5 \mathrm { n m }$ ，重复精度±1nm。合光成像系统是由1个合光成像望远镜组成，该望远镜为卡赛格林形式，口径$1 1 0 \mathrm { m m }$ ，焦距 $1 6 8 0 \mathrm { m m }$ 。在完成倾斜误差与光程差的校正后，该系统将3路光束进行相干成像。

![](images/b2c7737b01fb15a458d6f2d854fd86626213f22f930e69da18f3c70d23c42f4a.jpg)  
图2原理样机系统Fig.2 Principle prototype system

![](images/7d0ac34446a5d1617ecd642e6399c5618138e0b35df850c4356a496e3bf7331c.jpg)  
图3电子学系统Fig.3 Electronic system

![](images/18dd2d395270df54ce0b58f3395f4dcb869f75fcfab529dacc9ac416ceb2597c.jpg)  
图4光程补偿组件粗调平台和精调平台  
Fig.4Piston compensation elements coarse and fine adjustment platform

4开环实验

在开环实验中，我们设置NKT光源输出的光谱范围为 $5 5 0 { - } 6 5 0 \mathrm { n m }$ 、中心波长为 $6 0 0 \mathrm { n m }$ 。通过移动 M-122平台，在 $- 9 0 \mu \mathrm { m }$ 至 $+ 9 0 \mu \mathrm { m }$ 的光程差范围内，以 $1 \mu \mathrm { m }$ 为间隔，采集两束光干涉所形成的181幅色散干涉条纹图像。图5、图6中，从上至下分别为- ${ \cdot } 6 0 \mu \mathrm { m }$ 、 $0 \mu \mathrm { m }$ 、 $+ 6 0 \mu \mathrm { m }$ 光程差下的色散干涉条纹图像及其频谱。当光程差为零时，干涉条纹未发生倾斜。当光程差为正、负时，干涉条纹分别斜向下、斜向上倾斜。由于干涉条纹的倾斜线与两个次峰之间的连接线互相垂直，因此当光程差为零时，两个次峰对称分布于y轴正、负半轴。当光程差为正、负时，两个次峰对称分布于一、三象限和二、四象限。

![](images/042fcfab002198ecbff2cbbdadc1efc65e86335ab035f70306296f9224ead92f.jpg)  
图5不同光程差的干涉条纹图像

![](images/6dcf56ad1a93c52541fa5277dc1058901a394bb71f9aa290b04e1cdf16f60607.jpg)  
图6与干涉条纹图像所对应的频谱图

对 181 幅图像求得的偏移量 $d \boldsymbol { x } ^ { \prime }$ 及其拟合结果如图7所示。其中横坐标为光程差设定值，单位 $\mu \mathrm { m }$ ，纵坐标为所选取的位于 $\mathrm { ~ x ~ }$ 轴上方的次峰相对于y轴的偏移量 $d x ^ { \prime }$ ，单位为pixel。红色圆点为与181个光程差所对应的偏移量 $d \boldsymbol { x } ^ { \prime }$ ，蓝色直线为181个偏移量的线性拟合结果，拟合式为 $d x ^ { \prime } = 0 . 2 5 3 6 \phi + 0 . 9 1 0 4$ ，因此可以通过该表达式计算出181个光程差值。图8为实际求解光程差与设定光程差的对比图，其中横坐标为设定光程差，单位 $\mu \mathrm { m }$ ，纵坐标为实际解算出的光程差值，单位为 $\mu \mathrm { m }$ 。绿色圆点为实际求解出181个光程差的分布，蓝色直线为设定的光程差值。所求解的部分偏移量 $d \boldsymbol { x } ^ { \prime }$ 及实际光程差 $\phi$ 如表1、2所示。

![](images/208628bb467f9e29b8ce8c7b0443efb0ae4376c5e79d5b4bb1a22d4b84372af9.jpg)  
Fig.5Interference fringe images with different piston errors   
图7偏移量求解及线性拟合结果  
Fig.7Peak displacements and linear fitting results

![](images/571a2d0e6bfe7aa4ccf26b306feae76baf8ea242a28f0b201c5a8b173fb6808d.jpg)  
Fig.6Spectrogramsrelated to interference fringe images   
图8设定光程差与实际光程差对比图 Fig.8 Set and real piston errors comparison

# 表1次峰相对于y轴偏移量

Table 1 Peak displacements related to y-axis   
表2光程差解算结果  

<html><body><table><tr><td>设定值 (um）</td><td>-60</td><td>-40</td><td>-20</td><td>0</td><td>20</td><td>40</td><td>60</td></tr><tr><td>偏移量 (pixel)</td><td>-14.0</td><td>-9.1</td><td>-4.0</td><td>1.0</td><td>6.0</td><td>11.0</td><td>15.9</td></tr></table></body></html>

Table 2 Piston error calculation results   

<html><body><table><tr><td>设定值 （um）</td><td>-60</td><td>-40</td><td>-20</td><td>0</td><td>20</td><td>40</td><td>60</td></tr><tr><td>解算值 （um)</td><td>-58.7</td><td>-39.5</td><td>-19.5</td><td>0.4</td><td>20.0</td><td>39.7</td><td>59.0</td></tr></table></body></html>

在得到 ${ \it \cdot } 9 0 \mu \mathrm { m }$ 至 $+ 9 0 \mu \mathrm { m }$ 范围内的光程差计算结果后，我们计算了均方根误差值。设 $\phi _ { i }$ 为设定光程差值， $\phi _ { d }$ 为实际解算光程差值，测量误差 $\varepsilon$ 的表达式为：

$$
\varepsilon = \phi _ { d } - \phi _ { i }
$$

在开环实验中，计算得到181个光程差的均方根误差 $\varepsilon _ { r m s }$ 为 $1 . 5 6 4 \mu \mathrm { m }$ 。

# 5 闭环实验

光学综合孔径系统光程探测及闭环控制框图如图9所示，其中 $\delta _ { s e t }$ 为设定的光程差， $\delta _ { a c t }$ 为实测的光程差。利用基于傅里叶变换的光程计算方法，通过数字信号处理器完成光程差的实时计算，驱动执行机构，即P-753，通过改变镜面的位置，从而对光程差进行补偿控制。控制方法采用离散比例-积分-微分控制(PID)，其中比例控制的动作与偏差大小成正比，其作用是以某一比例对稳态误差进行消除，积分控制的动作与偏差对时间的积分成正比，其作用是消除每次采样时刻产生的余差，微分控制的动作与偏差的变化速度成正比，其效果是阻止被调参数的变化，有超前调节的作用。增量式PID表达式为：

$$
\begin{array} { l } { { u ( k ) = u ( k - 1 ) + K _ { p } [ e ( k ) - e ( k - 1 ) ] + K _ { i } e ( k ) + K _ { d } [ e ( k ) - 2 e ( k - 1 ) + e ( k - 2 ) ] = } } \\ { { \ } } \\ { { u ( k - 1 ) + q _ { 0 } e ( k ) + q _ { 1 } e ( k - 1 ) + q _ { 2 } e ( k - 2 ) } } \end{array}
$$

其中 $q _ { 0 } = K _ { _ p } + K _ { i } + K _ { _ d } , q _ { 1 } = - K _ { _ p } - 2 K _ { _ d } , q _ { 2 } = K _ { _ d } $ 其中 $u ( k )$ 为第 $\mathbf { k }$ 次采样的输出， $K _ { \mathfrak { p } } \setminus K _ { i } \setminus K _ { d }$ 分别代表PID控制器的比例系数，积分系数和微分系数。

![](images/cd230259748c8e4f6444ad25936b3ed92dc53f974818a8ca086d74bf9410b54f.jpg)  
图9光学综合孔径光程探测及闭环控制框图  
Fig 9. Optical synthetic aperture piston error detection and close-loop control diagram

在闭环实验中，我们同样使用NKT光源，中心波长设为 $6 0 0 \mathrm { n m }$ ，光谱范围为 $5 5 0 – 6 5 0 \mathrm { n m }$ 。设置 $K _ { p } = 0$ ， $K _ { i } { = } 0 . 0 4$ ， $K _ { d } = 0$ 。图10、图11、图12分别为调节到零光程、 $2 . 5 \mu \mathrm { m }$ 光程差以及 ${ 5 } { \mu } { \mathrm { m } }$ 光程差时的开、闭环实验结果。当系统处于开环状态时，干涉条纹图像随着光程差的增加而发生了偏移。当系统处于闭环状态时，不管光程差如何变化，干涉条纹始终稳定在零光程的位置，表明光程差的闭环控制起到了良好的效果。

![](images/8c0614b5b7d4bf54e2baaab74c9139154dd90e19924fd7a2637d6fc9ae225ebe.jpg)

![](images/f23620da5d02d1cbe5efb6abf4c6473d4ee7b08e6887605b76de47ebcba00df9.jpg)  
Fig $1 0 . 0 \mu \mathrm { m }$ piston error open-loop (left) and close-loop (right) experiments comparison   
图 $1 1 2 . 5 \mu \mathrm { m }$ 光程差开环实验（左）与闭环实验（右）对比图

![](images/e95e6b2142fdf2f98c7958c92b1c6a3676f16cf3d7c94db5a25f391bd6591e9f.jpg)  
图10 零光程开环实验（左）与闭环实验（右）对比图  
Fig $1 1 . 2 . 5 \mu \mathrm { m }$ piston error open-loop (left) and close-loop (right) experiments comparison   
图 $1 2 \ 5 \mu \mathrm { m }$ 光程差开环实验（左）与闭环实验（右）对比图 Fig $1 2 . 5 \mu \mathrm { m }$ piston error open-loop (left) and close-loop (right) experiments comparison

# 6总结

本文主要介绍了我们开展基于傅里叶变换的色散条纹法进行光程探测及开、闭环实验结果的情况。首先，我们进行了理论推导，得到次峰相对于y轴偏移量与光程差之间的线性关系。然后，进行了算法流程设计。最后，利用实验室的光学综合孔径实验装置，进行了开、闭环实验。在开环实验中，采集多幅不同光程差的色散条纹图像，对图像频谱次峰偏移量和光程差的关系展开研究，结果显示，偏移量与光程差之间呈现出良好的线性关系；在闭环实验中，利用光程差的实时计算结果和光程补偿机构，对光程差进行闭环控制，结果显示，在外加扰动的情况下，系统能够始终保持在初始的干涉状态。

# 参考文献：

[1]白静,姜爱民,戴妍峰.Golay3 型光学稀疏孔径系统退化图像的频率信息提取及合成研究[J].天文研究与技术,2016,13(03):351-357.   
[2]NiM,BesoL,CapJetal.Autoooustip/tlligntdsigofdtrbtedaertureiagigtestbedJ].Opt, 2010,18(12):13051-13056.   
[3]EspositoS,DevaneyN.Segmented telescopesco-phasingusingPyramid Sensor[Cy/European SoutherObservatoryConferenceand WorkshopProcedings.2oO2,58:161.[4]ChananGTroyM,SirkoE.Phasediscontinuitysensing:amethodforphasingsegmented mirrors in the infrared[J].Applied optics,1999,38(4): 704-713.   
[4]BolcarMR.Phase diversityforsegmentedandmulti-aperture systems[D].UniversityofRochester.InstituteofOptics,208.   
[5]ChananGOharaC,TroyM.PhasingthemirrorsegmentsoftheKecktelescopesI:thenarrow-band phasingalgorithm[J].Aplied Optics,2000,39(25): 4706-4714.   
[6]张勇,张靓.色散条纹传感技术用于拼接镜面位移探测的仿真研究[J].中国科学院大学学报,2010,27(4):471-479.   
[7]刘清,姜爱民.光学综合孔径望远镜光程探测方法研究[J].天文研究与技术,2017,14(04):519-525.   
[8]vaDamMA,McLeodBAouchezAH.DspersedrgesesorfortheiantMagellnTelescopeJ].Appliedoptics,26,55(3): 539-547.   
[9]PoynerLA.Scene-basedShack-Hartmannwave-frontsesing:analysisandsimulation[J].AppliedOptics,O3,42(9):585815.   
[10]JiagA,WangS,DongZetal.Wide-bandwhitelightsparse-apertureFzeauimaginginterferometertestbedforadistributed small-satellites constellation[J].Applied optics,2018,57(11): 2736-2746.

# Experimental Research on Dispersed Fringe Sensing Based on Fourier Transform

Dang $\mathrm { C e } ^ { 1 , 2 , 3 }$ ， Jiang Aimin1.²，Dong Zhichao1.2， Xue Jianwei1,2   
(1.National Astronomical Observatories,Chinese Academyof Sciences,Beijing1Oolol,China；2.KeyLaboratoryof Space   
AstronomicalandTechnology,NationalAstronomicalObservatories,Chinese AcademyofSciences,BeijingOoo,China; 3. University of Chinese Academy of Sciences，Beijing lOoo49，China，Email: dangce @nao.cas.cn)

Abstract: For optical interference,to realize the co-phasing efect is important, especially rigorous for broadband white light interference.In order to realize stable white light interference, we need to make real-time detection and compensation control for the piston error. Through theoretical derivation,algorithm design for dispersed fringe sensing based on Fourier transform and open-loop, close-loop research with the Fizeau interference experiment facilities in our lab.In the open-loop experiment, we collect many dispersed fringe images with different piston errors and research on the relationship between peak displacements in the spectrogram and piston errors,the results show a good linear relationship.In the close-loop experiment, we make close-loop control for the piston error with real-time calculation results and piston error compensating elements, the results show that the system remains at the initial interference state with extra perturbation.

Key Words:Piston error detection; Fourier transform; Dispersed fringe sensing; Control