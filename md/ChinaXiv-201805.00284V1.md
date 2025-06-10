# 异构环境下的多子阵合成孔径声纳距离多普勒成像算法

钟何平，唐劲松，黄攀(海军工程大学 海军水声技术研究所，武汉 430033)

摘要：为解决多子阵合成孔径声纳成像效率低的问题,提出了一种异构环境下的多子阵合成孔径声纳快速成像方法。根据多子阵合成孔径声纳距离多普勒成像算法特点以及CPU和GPU各自计算特点，通过将算法中距离向脉冲压缩、固定相位补偿、距离徙动校正和方位向脉冲压缩密集型运算采用GPU 计算，极大提高了多子阵合成孔径声纳成像效率。最后通过实测数据的成像实验对所提算法的正确性和高效性进行了验证，与串行计算方法相比加速比高达14.45。

关键词：合成孔径声纳；距离多普勒成像；并行计算；图形处理器中图分类号：TN958 doi:10.3969/j.issn.1001-3695.2017.08.0867

# Range doppler algorithm for multi-array synthetic aperture sonar in heterogeneous environment

Zhong Heping, Tang Jinsong, Huang Pan (Naval Institute ofUnderwater Acoustic Technology,Naval Universityof Engineering, Wuhan 43oo33,China)

Abstract: Aiming tosolvingtheloweficiencyimagingofmulti-arraysynthetic aperture sonar,afastimaging methodformultiarrysyntheticaperture sonarinheterogeneous environment is proposed.Consideredtherange Doppleralgorithmcharacteristic for multi-array syntheticaperture sonarand diferentcalculationfeatures between CPUand GPU,the intensivecalculationsuch as rangecompresion,phase compensation,rangecellmigrationcompensation and azimuth compresion isimplementedon GPU,which greatly enhancesthe imaging efficiencyfor multi-arrysynthetic aperture sonar.In theend,thevalidityand eficiencyof the proposed methodare verified through the imaging experiment performedonreal data and thespeedup is upto 14.45 times compared to the serial algorithm.

:ey Words: synthetic aperture sonar; range Doppler algorithm; parallel computing; GPU

# 0 引言

合成孔径声纳(synthetic aperture sonar,SAS)是一种高分辨率成像声纳，其原理是利用小尺寸的声基阵沿空间作匀速直线运动来合成大的虚拟孔径，并在运动过程中以恒定的脉冲重复间隔发射和接收信号，根据空间位置和相对关系将不同位置的回波信号进行相干叠加，进而获得方位向上的高分辨率[1-4]。距离向上的高分辨率通过发射大带宽信号，然后通过脉冲压缩技术得到。正是由于合成孔径声纳具备高分辨率特性，近年来在军用和民用众多领域得到应用[56]。军用方面，合成孔径声纳主要应用于沉底雷/掩埋雷探测、未爆破物探测、重要海域的高分辨侦察等。民用方面主要应用于水下地形测绘、海底地质勘探、考古搜救、海底电缆或石油管道的铺设和定位、航道疏浚工程量评估等方面。

随着合成孔径声纳技术的不断发展，一方面成像分辨率仍在不断提高以满足小目标探测需要，另一方面测绘带宽度不断加大以满足高速测绘需求，这两个因素的共同作用导致了原始数据距离向点数的不断增加。测绘带宽度增加的同时，最大测绘距离不断加大导致了合成孔径长度的增加，原始数据方位向点数也在不断增加。原始数据量的增加将显著延长合成孔径成像所需要的时间，导致成像效率降低，难以满足合成孔径声纳系统实时性需求。合成孔径成像在硬件选择上主要有专用硬件方案[7]和通用硬件方案[8\~10]两种。在合成孔径声纳发展早期，因通用计算机性能难以满足合成孔径声纳信号处理需求，一般采用专用硬件方案，但存在研发周期长、成本高和难以拓展等缺点。随着计算机技术的发展，研究人员通过构建计算机集群的方法来提升计算能力，实现了合成孔径雷达和合成孔径声纳成像算法的并行，取得了显著效率提升。集群计算机存在体积大、功耗大，并且不满足合成孔径声纳对信号处理平台可移动的需求。图形处理器(GraphicProcessingUnit,GPU)的出现为合成孔径声纳信号处理提供了新的处理平台，它具有强大信号处理能力和高性价比特点，并且已得到广泛应用[11,13]。

本文提出了一种基于GPU异构环境下的多子阵合成孔径声纳距离多普勒成像方法，有效解决了合成孔径声纳系统的实时成像问题，并且为多子阵合成孔径声纳异构环境下的软件开发提供了基本框架。首先给出了合成孔径声纳距离多普勒成像算法的基本原理，分析了各步骤信号处理特点，然后针对距离向脉冲压缩、固定相位补偿、距离徙动校正、方位向脉冲压缩在GPU环境下的运行进行了并行化设计。最后通过实测数据的合成孔径声纳成像实验，验证了所提算法的性能。

# 1 多子阵SAS成像模型

![](images/e484676cefeac21f33376173dbf8ddb5e3cf0bbf34b8e662a9c81fe23a189a50.jpg)  
图1多子阵 SAS成像模型

图1直角坐标系中，SAS平台沿着方位向运动，目标位于坐标 $( r , 0 )$ 处，发射阵和 $N$ 个接收子阵沿方位向排列，发射阵位于尾端，其位置为 $( 0 , \nu t )$ 。为简化处理，本文仅考虑一个接收子阵(取第 $i$ 个接收子阵)的情况，此接收子阵与发射阵方位向等效相位中心间隔为 $\Delta h _ { _ i }$ ，假设信号传播期间平台移动距离为 $\nu t ^ { * }$ ，其中变量 $t ^ { * }$ 表示平台运行时间，第 $i$ 个接收子阵接收到的回波信号可表示为

$$
\begin{array} { l } { s s _ { i } ( \tau , t ; r ) = A _ { 0 } \cdot r e c t { \displaystyle \left( \frac { \tau - R _ { i } ( t , r ) / c } { T } \right) } \cdot \omega _ { a } \left( t \right) } \\ { \displaystyle \qquad \cdot \exp \left. j \pi k \left( \tau - \frac { R _ { i } ( t , r ) } { c } \right) ^ { 2 } \right. } \\ { \displaystyle \qquad \cdot \exp \left. - j \frac { 2 \pi f _ { 0 } } { c } R _ { i } ( t , r ) \right. } \end{array}
$$

其中 $r e c t ( \cdot )$ 是矩形窗函数，定义如下：

$$
r e c t ( x ) = \left\{ \begin{array} { l l } { 1 , \quad } & { | x | \leq 0 . 5 } \\ { 0 , \quad } & { | x | > 0 . 5 } \end{array} \right.
$$

$R _ { i } \left( t , r \right) = R _ { _ { i } } + R _ { _ { i } }$ 为信号实际传播路径，其中去程为：$R _ { _ 1 } = \sqrt { \left( \nu t \right) ^ { 2 } + r ^ { 2 } }$ ，回程为 $R _ { 3 } = \sqrt { ( \nu t + \Delta h _ { \scriptscriptstyle i } + \nu t ^ { \scriptscriptstyle * } ) ^ { 2 } + r ^ { 2 } }$ ，$s ( \tau ) = r e c t { \bigl ( } \tau / T { \bigr ) }$ 为发射信号包络， $\mathbf { \Psi } _ { c }$ 为声速， $f _ { \mathrm { 0 } }$ 为信号中心频率， $k$ 为信号调频斜率。

# 2 多子阵SAS距离多普勒成像算法

距离多普勒成像算法是一类经典的合成孔径成像算法，其基本思想是利用距离相同而方位不同的散射点在距离多普勒域具有相同的能量轨迹，通过插值解二维耦合，将二维成像处理转换为两个一维处理的级联形式。多子阵合成孔径声纳成像最常用方法就是将多子阵回波信号转换为单子阵回波信号，然后调用单阵距离多普勒成像算法。

图2给出了RD算法的流程图，图中FFT和IFFT分别表示傅立叶变换和傅立叶逆变换。从图2中可以看出RD 算法的距离向处理和方位向处理是分开进行的。当回波信号在距离向和方位向不能解耦和时，需要利用sinc插值实现距离向徙动校正以完成解耦。

![](images/9eb791b518e1411f2cf40a5ea31e8a7867ece36c8b3ca1a38473c2db0a529aea.jpg)  
图2距离多普勒算法流程图

从信号处理流程上看，采用距离多普勒算法进行合成孔径声纳成像主要包括原始数据预处理、距离脉冲压缩、固定相位补偿和方位脉冲压缩4个步骤。原始数据预处理主要包括有效数据截取、数据类型转换和子阵数据叠加，其中原始数据有效截取主要是根据脉冲重复间隔 $P R I$ 、平台速度 $\boldsymbol { V }$ 、子阵长度 $D$ 之间的关系 $P R I \cdot V = D \cdot M / 2$ 确定用于成像的有效子阵个数$M$ ，然后对原始数据进行有效截取。由于原始数据预处理步骤计算量小，直接采用CPU完成。距离向脉冲压缩，主要包括FFT、点乘和IFFT运算，所有计算都是在距离向上进行处理，不同距离向上的处理过程完全独立。固定相位补偿主要是将多子阵接收的信号转换为单子阵接收的信号，然后调用单阵成像算法进行处理。方位向脉冲压缩主要包括FFT、IFFT、距离向徙动校正和点乘运算，其中距离向徙动校正过程是一个逐点插值过程，严重影响合成孔径声纳系统成像效率。

# 3 GPU环境下并行算法

为解决合成孔径声纳距离多普勒成像算法实时性问题，对其中耗时处理步骤：距离向脉冲压缩、固定相位补偿和方位向脉冲压缩处理计算方法进行了重新设计，以满足GPU并行处理条件，提升算法计算效率。

# 3.1距离向脉冲压缩

距离向脉冲压缩首先是对每一距离向采样回波数据进行FFT 变换，由于每一距离向回波数据在内存中连续存放，因此这一步可以直接通过调用CUDA中高效FFT变换函数cufftExecC2C实现。在调用cufftExecC2C执行FFT变换前，首先需要通过cufftPlanld函数来构造FFT变换句柄，指定FFT变换数据类型、1次连续变换点数（距离向点数）、连续变换次数（方位向点数）和变换类型。变换句柄的好处在于可根据输入参数预先配置好内存和计算资源，使得运算时处理器能达到最佳性能。距离向完成FFT变换后，数据在距离向变为频域，然后与距离向参考函数 $H _ { \mathrm { r } } ( f _ { \mathrm { r } } ) = \exp \left( \pi f _ { \mathrm { r } } ^ { \mathrm { ~ 2 ~ } } / k _ { \mathrm { r } } \right)$ 相乘，其中 $f _ { r }$ 表示距离向频率， $k _ { r }$ 为信号调频斜率。距离向参考函数从本质来说是一个1维数组，在成像之前首先计算后存放在共享存储器，其点数与距离向点数相同。由于参考函数是与每一距离向数据对应相乘，同一距离位置所乘数据相同，为减小参考函数重复读取时间开销，在进行线程块划分时，按照距离向进行1维线程块划分，如图3所示。假设当前线程块索引为BN，其包含的线程个数为TN，则该线程块完成列数为 ${ \mathrm { B N } } ^ { * } { \mathrm { T N } }$ 至（ $\mathrm { B N } { + } 1$ ）\*TN-1距离向数据点乘，线程块中每一线程按照方位向顺序依次完成该距离向上所有数据的点乘运算。完成点成运算后，再一次调用FFT逆变换函数，完成距离向脉冲压缩。由于FFT逆变换句柄与正变换相同，只需要在调用cufftExecC2C函数中改变变换类型参数。

![](images/26bcde2f2c76a45cb215f03af009b686e4e40fcbc59b978ddc4fe980117771f8.jpg)  
图3距离向点乘示意图

# 3.2 固定相位补偿

固定相位补偿是完成将原始多子阵回波形式变为单子阵回波形式，然后调用单子阵回波算法进行成像处理。合成孔径声纳成像的关键就在于固定相位补偿的精度，不同学者对不同环境下的具体补偿方法进行了深入研究。通常相位补偿精度与计算量乘正比，在考虑非停走停情形下的固定相位补偿公式为

$$
H ( \Delta h _ { i } , r ) = \exp \left\{ j \frac { 2 \pi f _ { 0 } } { r c } \Biggl ( \nu \frac { r } { c } + \frac { \Delta h _ { i } } { 2 } \Biggr ) ^ { 2 } \right\}
$$

其中 $f _ { \mathrm { 0 } }$ 为中心频率， $\Delta h _ { _ i }$ 为第 $i$ 个接收子阵与发射阵方位向等效相位中心间隔， $\boldsymbol { \mathbf { \mathit { c } } }$ 为声速， $\nu$ 为载体运动速度， $\boldsymbol { r }$ 为斜距。从补偿公式可以看出， $H ( \Delta h _ { _ i } , r )$ 的取值仅与接收子阵的位置和斜距有关，不同脉冲之间的补偿过程是完全相同并且独立的。根据固定相位补偿特点，这里仍然采用1维线程块进行固定相位补偿，具体方法如图4所示。

![](images/d0beed2346f133b9e104f0c09d59e3116f1d33e1baf1179552db6a1cb456f17e.jpg)  
图4固定相位补偿示意图

在进行固定相位补偿时，将原始数据看做3维形式，每个脉冲原始数据为1个2维数组，不同脉冲原始数据看做层叠形式。1维线程按照距离向进行分块，假设当前线程块索引为BN，其包含的线程个数为TN，则该线程块完成列数为 ${ \mathrm { B N } } ^ { * } { \mathrm { T N } }$ 到（ $\mathbf { B N + } 1$ ） $\ast _ { \mathrm { T N - 1 } }$ 距离向数据的固定相位补偿。线程块中每一线程按照先子阵、后脉冲顺序完成同一距离向上所有数据固定相位补偿。为节省计算量，充分考虑固定相位补偿特点，在子阵和距离确定情况下，补偿因子为常数，因此补偿顺序上先对第1个子阵所有脉冲数据进行补偿，然后依次对后续每个子阵数据进行补偿，从而可有效避免冗余计算。

# 3.3方位向脉冲压缩

方位向脉冲压缩是在距离时域方位频域进行的，其核心是距离向徙动校正。方位向脉冲压缩流程如图5所示，完成固定相位补偿后，需要在方位向上进行FFT变换。为满足CUDA中FFT 函数变换条件，需要对数据进行转置操作，使得数据在内存中连续。从流程图中可以看出，在进行FFT变换和IFFT变换前后分别需要进行1次矩阵转置操作。矩阵转置过程需要使用共享存储器，采用合并读写方式来提高转置速度。

![](images/bbb2799599c793e6647f84c2b822d9cd671dd716990c2829b572425d234c1f28.jpg)  
图5方位向脉冲压缩流程图

将数据变为距离时域方位频率后，根据距离徙动公式

$$
\Delta R ( f _ { a } , r ) = \left( f _ { a } / f _ { a M } \right) ^ { 2 } r / 2
$$

计算出对应徙动量，其中 $\boldsymbol { r }$ 为斜距， $f _ { a }$ 为方位频率， $f _ { a M }$ 为最大方位频率。从徙动公式可看出徙动量是一个二元函数，它与斜距和方位频率有关。在进行距离徙动校正时，不同方位频率上数据校正过程是完全独立的，这里采用1维线程，每一线程块完成当前距离向上所有方位频率数据距离徙动校正。由于同一方位频率数据在距离徙动校正中，相邻线程插值所需数据存在重复，为减小数据访问延迟，在进行校正前，当前线程块将校正过程中所需要的数据先共同载入到共享存储器，校正过程中直接使用共享存储器中数据。假设插值点数为 $2 N$ ，当前1维线程块中线程 $i$ 所对应的空间距离徙动量为 $( f _ { _ a } / f _ { _ { a M } } ) ^ { 2 } r / 2$ ,则其对应的距离向徙动单元数△N,=floor((fIfa)²△R/(2Rbn)),其插值所用原始数据下标在 $i + \Delta N _ { _ { r } } - N$ 和 $i + \Delta N _ { , } + N$ 之间。完成距离向徙动校正后，然后与方位向参考函数$H _ { _ a } ( f _ { _ a } ) = \exp \left( \pi f _ { _ a } ^ { _ 2 } / k _ { _ a } \right)$ 相乘，其中 $f _ { a }$ 表示多普勒频率， $k _ { \mathrm { a } }$ 为多普勒调频斜率，并且为斜距 $\boldsymbol { r }$ 函数。最后再一次进行方位向IFFT变换，完成方位向脉冲压缩，获得最终成像结果。

# 4 实验结果

为验证异构环境下的合成孔径成像算法效率，本文在如下环境下进行了测试：处理器Intel(R)Core(TM)i5-4200H$\mathrm { C P U } @ 2 . 8 0 \mathrm { G H Z } 4$ 核，显卡NVIDIAGeForceGTX950M，内存4G，操作系统Windows7旗舰版，软件环境开发环境：VS2008+CUDA5.0。为测试算法效率，本文比较了CPU串行计算方法、基于OpenMP的共享内存并行计算方法和CPU+GPU的异构并行计算方法效率。成像过程中，距离徙动校正插值点数设置为6。异构并行算法中，1维线程块大小设置为。

实验过程中采用了一组真实数据，该数据是2010年7月在某内陆湖进行干涉合成孔径声纳海试样机实验中获得的，具体实验参数如表1所示。实测数据所对应的原始回波幅度信息如图6(a)所示，距离向点数为9600，方位向点数为3456，采集起始距离和结束距离分别为 $5 1 \mathrm { m }$ 和 $2 3 1 \mathrm { m }$ ，在距离向上回波幅度一致性较好。原始回波方位向上数据由4个合成孔径长度共计72个脉冲数据组成，数据采集总时间为 $2 3 . 0 4 \mathrm { s }$ 。由于相邻原始数据块在方位向上存在1个合成孔径长度的重叠，因此实际可用于信号处理的时间仅为 $1 7 . 2 8 \mathrm { s }$ 。由于三种成像方法的计算结果是相同的，均如图6(b)所示，成像结果中清晰重构出了成像场景轮廓信息，验证了距离多普勒成像算法的有效性。

表1实验系统参数  

<html><body><table><tr><td>参数</td><td>数值</td><td>参数</td><td>数值</td></tr><tr><td>载频(kHz)</td><td>150</td><td>脉冲重复时间(ms)</td><td>320</td></tr><tr><td>带宽(kHz)</td><td>20</td><td>子阵长度(m)</td><td>0.08</td></tr><tr><td>脉宽(ms)</td><td>20</td><td>子阵个数</td><td>48</td></tr><tr><td>声速(m/s)</td><td>1448</td><td>载体速度(m/s)</td><td>2.5</td></tr></table></body></html>

![](images/1b4fac38985ce1cb7317c3b5c16eb11ac1cf3027ba4878695954f7180ae836b9.jpg)  
图6实测数据成像实验

为充分体现异构环境下的距离多普勒成像算法效率优势，将其与串行计算方法和共享内存并行计算方法进行了比较，具体结果如表2所示。合成孔径成像预处理步骤主要完成原始数据截取、数据类型转换和子阵数据叠加处理，由于这一部分计算量小，在比较合成孔径成像算法效率时可忽略不计。从表 2中可看出，采用CPU串行计算进行合成孔径成像所需时间最长为 $1 4 6 5 3 \mathrm { m s }$ ，采用OpenMP方式进行共享内存方法并行后，各部分计算时间均显著降低，总计算时间降为 $5 ~ 7 0 6 \mathrm { { m s } }$ ，加速比达到2.58。采用GPU进行计算时，由于采用了CUDA中高效FFT 变换函数库，距离向脉冲压缩、方位向FFT 和方位向脉冲压缩计算效率都得到了显著提高，分别由3736、2783和3895ms 下降为82、109和 $1 4 3 \mathrm { m s }$ 。采用GPU进行合成孔径声纳成像计算时，虽然增加了显存分配、数据上传和数据下载时间，但总计算时间大幅度下降，只需 $1 \ 0 1 3 \ \mathrm { m s }$ ，加速比高达14.45，满足实时成像需求。

表2不同计算方法效率比较(ms)  

<html><body><table><tr><td>成像 方法</td><td>距离向脉冲压缩</td><td>固定相位补偿</td><td>方位向FFT</td><td>距离徙动校正</td><td>方位向脉冲压缩</td><td>显存 分配</td><td>数据 上传</td><td>数据 下载</td><td>总时间</td><td>加速比</td></tr><tr><td>方法1</td><td>3736</td><td>152</td><td>2783</td><td>4087</td><td>3895</td><td>0</td><td>0</td><td>0</td><td>14653</td><td>1</td></tr><tr><td>方法2</td><td>1562</td><td>54</td><td>1079</td><td>1664</td><td>1347</td><td>0</td><td>0</td><td>0</td><td>5706</td><td>2.58</td></tr><tr><td>方法3</td><td>82</td><td>17</td><td>109</td><td>483</td><td>143</td><td>38</td><td>71</td><td>70</td><td>1013</td><td>14.45</td></tr></table></body></html>

方法1：CPU串行计算方法，方法2：基于OpenMP 的共享内存并行计算方法，方法3： $\mathrm { C P U + G P U }$ 的异构并行计算方法。

# 5 结束语

本文提出了一种异构环境下的多子阵合成孔径声纳距离多普勒成像方法。通过将成像算法中耗时计算步骤采用多核GPU进行并行计算后，达到了显著提升计算效率目的，与串行算法相比，加速比高达14.45，有效解决了合成孔径声纳成像的实时性问题。从实验结果来看，异构环境下的距离多普勒成像算法时间主要消耗在距离徙动校正步骤，后续工作主要围绕该步骤并行优化方法展开，以进一步提升算法效率。

# 参考文献：

[1]Hayes MP,Gough PT.Synthetic aperture sonar: a review of current status [J].IEEE Journal of Oceanic Engineering,2009,34(3):207-224.   
[2] Zhang X B,Tang J S,Zhong HP.Multireceiver correction for the chirp scaling algorithm in synthetic aperture sonar [J].IEEE Journal of Oceanic Engineering,2014,39 (3): 472-481.   
[3]Tian Z, Tang J S,Zhong HP, et al.Extended Range Doppler Algorithm for Multiple-Receiver Synthetic Aperture Sonar Based on Exact Analytical Two-Dimensional Spectrum[J].IEEE Journal of Oceanic Engineering,2016, 41 (1): 164-174.   
[4]Zhang Xuebo,Huang Haining,Ying Wenwei,et al.An indirect rangedoppler algorithm for multireceiver synthetic aperture sonar based on lagrange inversion theorem [J].IEEE Trans on Geoscience and Remote Sensing.2017,55 (6):3572-3587.   
[5]Carballini J, Viana F.Using synthetic aperture sonar as an effective tool for pipeline inspection survey projectsg [Cl//Proc of Acoustics in Underwater Geosciences Symposium. 2015: 1-5.   
[6]Hoggarth A,Kenny K.Using synthetic aperture sonar as an effective hydrographic survey tool[J]. Oceans,2014,107(3): 1-12.   
[7]Cholewa F,Pfitzner M,Fahnemann C,et al. Synthetic aperture radar with backprojection: A scalable,platform independent architecture for exhaustive FPGA resource utilization. [C]// Proc of Radar Conference. 2014: 1-5.   
[8]徐永健，王贞松，罗晓广．星载 SAR 数据成像的并行和实时处理研究- 曙光机的应用实例[J]．电子与信息学报,2001,23(8):736-742.   
[9] 龙卉，皮亦鸣，黄顺吉．合成孔径雷达并行成像算法研究及在曙光 3000 并行计算机上的实现[J]．电子与信息学报，2002,24(12):1990- 1993.   
[10]江泽林，刘维，李保利，等．基于集群的高频合成孔径声呐并行处理方 法[J].应用声学,2011,30(3):167-176.   
[11] Fasih A, Hartley T. GPU-accelerated synthetic aperture radar backprojection in CUDA[C]//Proc of Radar Conference.2010:1408-1413.   
[12] Ning Xia,Yeh C, Zhou B,etal.Multiple-GPU accelerated range-doppler algorithm for synthetic aperture radar imaging [C]// Proc of Radar Conference.2011: 698-701.   
[13]吴胜强，彭建平，郭建强．基于GPU 的合成孔径超声成像算法并行处 理[J].信息技术,2017,30(2):126-129.