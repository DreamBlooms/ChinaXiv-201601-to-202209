# 基于GPU的非相干消色散算法

托乎提努尔1,3，张海龙1,2,3，王杰1,3，冶鑫晨1,3(1.中国科学院新疆天文台，新疆乌鲁木齐，830011；2．中国科学院射电天文重点实验室，南京，210008；3.国家天文科学数据中心，北京，100101)

摘要：针对脉冲星信号实时消色散处理需求，实现了基于GPU的非相干消色散算法。采用高性能并行计算方法对非相干消色散算法的多线程处理进行了深入研究，提出了算法的并行化加速方案，解决了消色散算法计算量大无法实时处理问题。分析算法的密集型计算部分，高效利用GPU的层次存储结构，提高了GPU资源利用率，进而减少了计算时间，显著提升了非相干消色散算法的计算性能。

关键词：消色散；GPU；并行计算；实时处理中图分类号：P111．44文献标识码：A 文章编号：

# 0引言

宇宙空间中的星际介质（Inter-Stellar Medium，ISM）[1]包含大量电离气体云、中性尘埃粒子和自由电子等物质。脉冲星信号在宇宙空间中传播的时候会因为ISM色散的影响而降低速度，高频的无线电波传播速度比低频快，所以高频和低频电磁波到达射电望远镜的时间有一定延迟，脉冲星信号因此出现能量分散而使脉冲轮廓加宽，信噪比下降，甚至会导致脉冲信号消失。

为了解决脉冲星信号色散问题，天文学家研究了消除色散方法[2-3]及高速消色散处理技术。利用多通道滤波器组[4]对脉冲星信号进行通道划分，生成多个窄带信号，针对窄带信号进行时间延迟处理，每个通道延迟时间可以通过色散公式计算，最后将所有窄带通道进行累加，获得高信噪比脉冲信号。

非相干消色散是脉冲星观测数据处理中最常用的色散处理方法，具备实现简单、速度快、数据后期处理灵活等优势。在脉冲星搜寻中，随着色散量（Dispersion Measure，DM)、数据通道及采样数量的增加，非相干消色散算法计算量迅速提高，通用的计算平台难以实现脉冲星数据的实时处理。近年来，GPU[5的可编程能力及并行处理能力迅速提高，应用范围也不断扩展，在 $\mathrm { C P U + G P U }$ 混合计算系统中，GPU的加入大大提高了整个系统的数据处理能力。高性能GPU集群系统可提供强大的计算资源，能够满足海量天文数据的实时处理需求，从而解决脉冲星消色散算法计算量巨大无法实时处理的问题。

# 1非相干消色散

非相干消色散算法根据色散公式计算每个通道的延迟时间，然后加上各个通道的延迟，并把所有通道叠加在一起，即可消除数据的色散影响。非相干消色散原理如图1所示。

非相干消色散采用多通道滤波器组来实现，消色散处理过程主要包括： (1)通道划分，使用滤波器组把观测的天文信号总带宽分成若干个相互独立的狭窄通道；(2）补充时间延迟，根据色散公式计算每个通道的时间延迟，按延迟进行通道平移，将各个窄带通道的脉冲信号在同一时刻对齐；（3）通道累加，将所有通道时间序列叠在一起。

![](images/204ed6e917e9430e8e47d12cc0e060431c3eb122800a40201174310df67e447a.jpg)  
图1非相干消色散原理  
Fig 1.The principle of incoherent de-dispersion

图1说明了非相干消色散的处理过程。图中左半部分未进行消色散，右半部分是消色散处理后的结果。从图中可以看出，消色散前，通道累加之后脉冲宽度被展宽，输出信号信噪比下降，消色散之后可以得到信噪比大幅提高的脉冲星轮廓。

非相干消色散已被广泛应用于脉冲星、快速射电爆搜寻。非相干消色散方法处理后的脉冲星数据，其各个子通道内的色散延迟依旧存在，不能得到脉冲的真实轮廓，随着频谱通道数的增加，每个通道的带宽变小，带内的色散效应可相应减轻，低频信号 $f _ { 1 }$ 和高频信号$f _ { 2 }$ 在星系际介质中的传播速度时间差为：

$$
t _ { 2 } - t _ { 1 } = \frac { e ^ { 2 } } { 2 \pi c m } \times D M \times ( \frac { 1 } { { f _ { 1 } ^ { 2 } } } - \frac { 1 } { { f _ { 2 } ^ { 2 } } } )
$$

式中， $\boldsymbol { c }$ 为光在真空中的传播速度， $e$ 为电子电荷，DM为色散量， $\boldsymbol { \mathit { m } }$ 为电子质量。DM可表示为：

$$
D M = \int _ { 0 } ^ { d } n _ { e } d l \approx n _ { e } d \
$$

式中， $\eta _ { e }$ 为电子密度， $d$ 为电磁波实际所经过的路径。

脉冲星消色散处理中，一个频率通道 $f _ { \mathrm { c h a n } }$ 相对于参考通道 $f _ { \mathrm { r e f } }$ （通常是观测带宽中心频率）的时间延迟，可根据色散量公式（3）计算：

$$
{ \Delta t } = { K } _ { _ { D M } } \times D M \times ( \frac { 1 } { { f _ { r e f } } ^ { 2 } } - \frac { 1 } { { f _ { c h a n } } ^ { 2 } } )
$$

式中， $K _ { D M }$ 是色散量常数，DM为观测脉冲星信号的色散量，其单位为 $\mathrm { c m } ^ { - 3 } \mathrm { p c }$ ，频率单位为 $\mathrm { M H z }$ 。色散量常数为：

$$
K _ { _ { D M } } = { \cfrac { e ^ { 2 } } { 2 \pi c m } } = 4 . 1 4 8 8 0 8 \times 1 0 ^ { 3 } ~ { \mathrm { M H z ^ { 2 } ~ p c ^ { - 1 } ~ c m ^ { 3 } ~ s } }
$$

在实际观测中，观测频率 $f$ 往往远大于划分的通道带宽 $\Delta f _ { : }$ ，如果 $f \gg \Delta f$ 时，频率通道的延迟时间可写为：

$$
t _ { \mathrm { { D M } } } = 8 . 3 { \times } 1 0 ^ { 6 } \mathrm { { m s } } \times \mathrm { { D M } } \times \Delta f \times f ^ { - 3 }
$$

式（5）说明，通道带宽和色散延迟时间成正比，为了得到更小的色散延迟，需要划分很细的窄带通道，尽量减少单通道信号带宽。

# 2非相干消色散算法的GPU实现

GPU 是现代PC 中常见的设备，专为执行复杂的数学和几何计算而设计的一种高度并行化、多线程、多核处理器，高速实现图形渲染。基于GPU的通用计算技术已经成为高性能并行计算领域的研究热点。GPU由于具备多个核心，更适合计算密集型操作。GPU的内核相当于CPU的多个线程，这些线程可以并行运行完成指定的计算任务，而且数值计算的速度远远优于CPU。GPU的线程结构如图2所示。

![](images/36c6be09efdec49dfd9ae392247aace63c56a8b472dc825b6cc5e6073f49ce1e.jpg)  
图2GPU线程结构  
Fig 2.GPU thread structure

GPU 的开发使用CUDA[8程序，CUDA 是一种由NVIDIA推出的通用并行计算平台和编程模型，使GPU能够解决复杂的计算问题。CUDA提供了硬件的直接访问接口，不依赖图形 API接口来实现GPU访问，在架构上采用了全新的计算体系结构来使用GPU提供的硬件资源。CUDA采用标准C语言的扩展作为编程语言提供大量的高性能计算指令，使我们能够在GPU的强大计算能力基础上实现效率更高的密集数据计算算法。

分析和研究非相干消色散算法结构，把计算量大的任务部分映射到GPU的多线程进行处理。非相干消色散算法复杂度为（ $\mathrm { ) \ C N _ { \mathrm { d } } \times N _ { \mathrm { s } } \times N _ { \mathrm { c } } \ }$ ，其中 $\mathrm { N _ { d } }$ 为DM总数， $\mathrm { N _ { c } }$ 为通道数， $\mathrm { N _ { s } }$ 为采样数，算法数学模型计算量较大，但是通过GPU处理可得到很好的加速比。在GPU算法中，对非相干消色散的色散量和时间维度上进行并行化，频率通道累加采用了串行的处理方法，即使用GPU的单线程实现了 $\mathrm { N _ { c } }$ 个通道的相加计算。在整个消色散过程中，CPU负责系统的初始化和输入数据读取，GPU负责并行消色散处理，CPU接收消色散后的时间序列并输出到数据文件。非相干消色散算法CUDA程序流程图如图3所示。

![](images/0c4af7ee9e6d9c3195a10d9a6002ef202911100058e01dbe5496bdbb4ccfb899.jpg)  
图3非相干消色散CUDA程序流程图  
Fig 3.Flow chart of CUDA program for incoherent de-dispersion

首先在CPU内存中开辟缓冲区，写入所需要处理的数据。缓冲区暂存的采样都存在一定的色散，因此需要对各个频率通道进行位移和累加运算，随着时间延迟增大，通道位移也增大，低频通道的位移量更大。为了减少CPU和GPU之间的频繁数据传输对算法计算性能的影响，在GPU中也设置全局内存缓冲区，尽量把大量数据一次性复制过去，并且为写入和读取数据保留足够大存储空间。GPU kernel 函数执行过程中，使用共享内存减少全局内存的延迟，提高kernel 函数运行速度。

为了提高算法的并行化加速，将非相干消色散算法的计算分为两部分，第一部分在CPU

上执行。

$$
t _ { \mathrm { c h a n } } = 4 . 1 5 { \times } 1 0 ^ { 3 } { \times } ( f _ { 1 } ^ { - 2 } - f _ { 2 } ^ { - 2 } )
$$

式中 $f _ { 1 }$ 、 $\mathcal { f } _ { 2 }$ 的单位是 $\mathrm { M H z }$ ， $t _ { \mathrm { c h a n } }$ 的计算与DM值无关，使用GPU 的常量内存存储。然后在GPU上执行计算的第二部分：

$$
t _ { _ { \mathrm { D M } } } = \frac { t _ { _ { \mathrm { c h a n } } } \times D M } { t _ { _ { \mathrm { s a m p } } } }
$$

式中 $\mathrm { t _ { s a m p } }$ 为采样时间，单位是ms。

根据非相干消色散算法特性，GPU kernel函数中定义了两个缓冲区：共享内存和常量内存。其中，共享内存存储积分运算的结果，常量内存用于存储DM_shift。为了快速通道累加，使用共享内存，隐藏了全局内存的访问延迟。一个线程块里面的所有线程获取 DM 平移值，并且存储到共享内存。对于每一个DM值，在共享内存中进行积分运算，并把消色散处理结果写入到GPU 的全局内存。

# 3实验分析

本次实验平台使用了Intel XeonE5-1620、TITANV、CUDA10.0及Ubuntu18.04。TITANV 是一款NVIDIAGeForce系列高端GPU,拥有5120个CUDA核，内存访问带宽为 $6 5 2 . 8 \mathrm { G B } / \mathrm { s }$ 。

为了验证GPU并行算法性能，首先分别模拟生成了32、64、128、256、512及1024通道脉冲星数据，其中心频率为 $4 2 0 \mathrm { { M H z } }$ ，带宽为 $6 ~ \mathrm { { M H z } }$ ，采样间隔时间为 $1 6 5 \mu \mathrm { ~ s ~ }$ ，脉冲星信号周期为0.1s，然后将每一块数据单独读取并加载到GPU中进行处理。实验结果如表1、表2、表3及表4所示。

表1采样数为固定时非相干消色散处理时间（单位：s，采样：131072）  
Tab.1 lncoherent de-dispersion processing time when the number of samples is fixed (time:s， samples: 131072)   

<html><body><table><tr><td rowspan="2">number of DM</td><td colspan="2">32 channel</td><td colspan="2">64 channel</td><td colspan="2">128 channel</td></tr><tr><td>CPU</td><td>TITAN V</td><td>CPU</td><td>TITAN V</td><td>CPU</td><td>TITAN V</td></tr><tr><td>1</td><td>0.0273</td><td>0.0078</td><td>0.0566</td><td>0.0148</td><td>0.1078</td><td>0.0289</td></tr><tr><td>2</td><td>0.0548</td><td>0.0085</td><td>0.1125</td><td>0.0154</td><td>0.2153</td><td>0.0296</td></tr><tr><td>5</td><td>0.1395</td><td>0.0102</td><td>0.2837</td><td>0.0172</td><td>0.5502</td><td>0.0324</td></tr><tr><td>10</td><td>0.2813</td><td>0.0132</td><td>0.5774</td><td>0.0204</td><td>1.1226</td><td>0.0357</td></tr><tr><td>20</td><td>0.5776</td><td>0.0189</td><td>1.2642</td><td>0.0265</td><td>2.3252</td><td>0.0434</td></tr><tr><td>40</td><td>1.4008</td><td>0.0314</td><td>2.7714</td><td>0.0393</td><td>5.3281</td><td>0.0599</td></tr><tr><td>80</td><td>3.0338</td><td>0.0574</td><td>6.0615</td><td>0.0658</td><td>11.9435</td><td>0.0962</td></tr><tr><td>160</td><td>6.1332</td><td>0.1193</td><td>13.0557</td><td>0.1273</td><td>26.7130</td><td>0.1636</td></tr><tr><td>320</td><td>13.8274</td><td>0.2556</td><td>29.5114</td><td>0.2740</td><td>56.2105</td><td>0.3399</td></tr><tr><td>640</td><td>33.9295</td><td>0.5106</td><td>65.7593</td><td>0.6378</td><td>134.9701</td><td>0.7307</td></tr><tr><td>1280</td><td>75.4416</td><td>1.0504</td><td>154.0248</td><td>1.3330</td><td>312.0603</td><td>1.7597</td></tr><tr><td>2560</td><td>158.7455</td><td>2.2094</td><td>329.0613</td><td>2.8760</td><td>668.0033</td><td>4.0038</td></tr></table></body></html>

<html><body><table><tr><td>5120</td><td>322.9089</td><td>4.3976</td><td>698.3460</td><td>6.0016</td><td>8.6268</td></tr><tr><td></td><td></td><td></td><td></td><td></td><td>1389.3232</td></tr></table></body></html>

表2采样数为固定时非相干消色散处理时间（单位：s，采样：131072）

Tab.2 Incoherent de-dispersion processing time when the number of samples is fixed (time:s, samples:131072)   

<html><body><table><tr><td rowspan="2">number of DM</td><td colspan="2">256 channel</td><td colspan="2">512 channel</td><td colspan="2">1024 channel</td></tr><tr><td>CPU</td><td>TITAN V</td><td>CPU</td><td>TITAN V</td><td>CPU</td><td>TITAN V</td></tr><tr><td>1</td><td>0.2103</td><td>0.0565</td><td>0.4204</td><td>0.1127</td><td>0.8289</td><td>0.2249</td></tr><tr><td>2</td><td>0.4308</td><td>0.0579</td><td>0.8371</td><td>0.1143</td><td>2.2732</td><td>0.2275</td></tr><tr><td>5</td><td>1.1644</td><td>0.0614</td><td>2.1853</td><td>0.1197</td><td>4.9677</td><td>0.2379</td></tr><tr><td>10</td><td>2.5279</td><td>0.0664</td><td>4.6357</td><td>0.1280</td><td>9.5110</td><td>0.2492</td></tr><tr><td>20</td><td>5.4891</td><td>0.0785</td><td>10.3499</td><td>0.1459</td><td>18.5704</td><td>0.2838</td></tr><tr><td>40</td><td>11.5288</td><td>0.1039</td><td>21.8757</td><td>0.1830</td><td>36.8282</td><td>0.3424</td></tr><tr><td>80</td><td>23.8050</td><td>0.1597</td><td>48.0757</td><td>0.2638</td><td>74.0204</td><td>0.4728</td></tr><tr><td>160</td><td>57.7672</td><td>0.2726</td><td>119.5114</td><td>0.4276</td><td>194.2584</td><td>0.7379</td></tr><tr><td>320</td><td>136.8641</td><td>0.5256</td><td>274.3375</td><td>0.7527</td><td>507.1785</td><td>1.2810</td></tr><tr><td>640</td><td>299.1812</td><td>1.0638</td><td>590.8383</td><td>1.4577</td><td>1161.6285</td><td>2.3831</td></tr><tr><td>1280</td><td>632.3722</td><td>2.5118</td><td>1238.2926</td><td>2.9597</td><td>2463.5231</td><td>4.6113</td></tr><tr><td>2560</td><td>1299.2245</td><td>6.8297</td><td>2592.5578</td><td>7.0263</td><td>5102.2142</td><td>9.3347</td></tr><tr><td>5120</td><td>2749.8164</td><td>19.221491</td><td>5533.0351</td><td>17.4777</td><td>10995.2138</td><td>20.4063</td></tr></table></body></html>

表1、表2是在采样数为131072（单通道采样)，通道和DM数都变化的情况下GPU 并行算法和CPU串行算法的非相干消色散处理消耗时间。从表中可以看出，当通道数量固定时，随着DM数的增加，GPU和CPU的数据处理时间线性增加，GPU的消色散处理时间远远少于CPU的计算时间；当DM数为固定时，随着数据通道数量的增加，CPU和GPU处理需要的时间增大，但是CPU的计算时间比GPU大的多。

表3通道数为固定时非相干消色散处理时间（单位：s，通道：1024）  
Tab.3 lncoherent de-dispersion processing time when the number of channels is fixed (time:s， channels: 131072)   

<html><body><table><tr><td rowspan="2">number</td><td colspan="2">4096 sample</td><td colspan="2">8192 sample</td><td colspan="2">16384 sample</td><td colspan="2">32768 sample</td></tr><tr><td>CPU</td><td>TITAN</td><td>CPU</td><td>TITAN</td><td>CPU</td><td>TITAN</td><td>CPU</td><td>TITAN</td></tr><tr><td>of DM 1</td><td>0.0259</td><td>0.0073</td><td>0.0519</td><td>0.0145</td><td>0.1037</td><td>0.0287</td><td>0.2072</td><td>0.0577</td></tr><tr><td>2</td><td>0.0518</td><td>0.0073</td><td>0.1036</td><td>0.0144</td><td>0.2075</td><td>0.0286</td><td>0.4147</td><td>0.0569</td></tr><tr><td>5</td><td>0.1307</td><td>0.0077</td><td>0.2624</td><td>0.0151</td><td>0.5251</td><td>0.0298</td><td>1.0499</td><td>0.0598</td></tr><tr><td>10</td><td>0.2656</td><td>0.0081</td><td>0.5379</td><td>0.0157</td><td>1.0764</td><td>0.0313</td><td>2.1585</td><td>0.0625</td></tr><tr><td>20</td><td>0.5430</td><td>0.0086</td><td>1.1102</td><td>0.0171</td><td>2.2238</td><td>0.0348</td><td>4.4429</td><td>0.0699</td></tr><tr><td>40</td><td>1.0930</td><td>0.0099</td><td>2.2470</td><td>0.0205</td><td>4.5026</td><td>0.0414</td><td>9.1970</td><td>0.0852</td></tr><tr><td>80</td><td>2.2684</td><td>0.0129</td><td>4.6959</td><td>0.0266</td><td>9.3686</td><td>0.0565</td><td>18.5134</td><td>0.1147</td></tr><tr><td>160</td><td>5.4016</td><td>0.0191</td><td>12.2362</td><td>0.0401</td><td>24.2389</td><td>0.0859</td><td>48.6114</td><td>0.1781</td></tr><tr><td>320</td><td>12.6597</td><td>0.0296</td><td>31.9656</td><td>0.0705</td><td>63.5571</td><td>0.1461</td><td>126.8976</td><td>0.3047</td></tr><tr><td>640</td><td>28.2764</td><td>0.0541</td><td>71.4992</td><td>0.1230</td><td>144.0788</td><td>0.2692</td><td>288.2967</td><td>0.5664</td></tr><tr><td>1280</td><td>61.5773</td><td>0.1020</td><td>150.4389</td><td>0.2408</td><td>299.1604</td><td>0.5263</td><td>614.7442</td><td>1.1099</td></tr><tr><td>2560</td><td>129.2098</td><td>0.2064</td><td>302.7521</td><td>0.4777</td><td>637.8879</td><td>1.0559</td><td>1280.9965</td><td>2.2027</td></tr></table></body></html>

<html><body><table><tr><td>5120</td><td>281.6858</td><td>0.4243</td><td>672.2270 0.9917</td><td>1374.9966</td><td>2.1815</td><td>2756.7142</td><td>4.5928</td></tr></table></body></html>

表3是当数据为1024通道时，采样和DM数都变化情况下的GPU并行算法和CPU 串行算法的非相干消色散处理消耗时间。当采样数固定时，随着DM数的增加，GPU和CPU的数据处理时间增加；当DM数为固定时，随着数据采样的增加，并行和串行算法执行需要更多的时间。但是，GPU的色散处理时间少于CPU的计算时间，计算速度有几百倍的差距，从表中可以看出GPU 大大缩短了非相干消色散的执行时间。

表4是在DM数为5120，采样和通道数都变化时，GPU并行算法和CPU串行算法的非相干消色散处理消耗时间。当采样固定时，随着数据通道的增加，GPU和CPU的数据处理时间也增加；当通道数固定时，随着数据采样的增加，并行和串行算法执行需要更多的时间。在通道数或采样数变化的情况下，GPU的运算时间均小于CPU，且消耗时间差距明显。

表4DM数为固定时非相干消色散处理时间（单位：s，DM：5120） Tab.4 lncoherent de-dispersion processing time when the number of DMs is fixed (time:   

<html><body><table><tr><td colspan="7">S, DMs: 131072)</td></tr><tr><td>Channel</td><td>Sample</td><td>4096</td><td>8192</td><td>16384</td><td>32768</td><td>65536</td></tr><tr><td rowspan="2">32</td><td>CPU</td><td>7.4468</td><td>15.0353</td><td>30.2430</td><td>60.6416</td><td>133.7846</td></tr><tr><td>TITAN V</td><td>0.1002</td><td>0.2003</td><td>0.4215</td><td>0.8864</td><td>2.0978</td></tr><tr><td rowspan="2">64</td><td>CPU</td><td>14.5728</td><td>29.8505</td><td>59.7925</td><td>123.8967</td><td>330.8217</td></tr><tr><td>TITAN V</td><td>0.1127</td><td>0.2164</td><td>0.4667</td><td>1.2664</td><td>2.8659</td></tr><tr><td rowspan="2">128</td><td>CPU</td><td>28.6676</td><td>57.8297</td><td>118.1305</td><td>316.7424</td><td>703.6475</td></tr><tr><td>TITAN V</td><td>0.1307</td><td>0.2665</td><td>0.7702</td><td>1.9095</td><td>4.0631</td></tr><tr><td rowspan="2">256</td><td>CPU</td><td>53.8793</td><td>111.2041</td><td>301.5122</td><td>694.0670</td><td>1386.7769</td></tr><tr><td>TITAN V</td><td>0.1519</td><td>0.4544</td><td>1.1833</td><td>3.4037</td><td></td></tr><tr><td rowspan="2">512</td><td>CPU</td><td>104.1580</td><td>282.3113</td><td>684.1435</td><td></td><td>8.927236</td></tr><tr><td>TITAN V</td><td>0.2411</td><td>0.6064</td><td>1.4260</td><td>1361.1676</td><td>2718.7850</td></tr><tr><td rowspan="2">1024</td><td>CPU</td><td>281.2189</td><td></td><td></td><td>3.3107</td><td>7.3363</td></tr><tr><td>TITAN V</td><td>0.4230</td><td>684.9610 1.0071</td><td>1375.0873 2.1739</td><td>2744.7187 4.6273</td><td>5494.2190 9.8898</td></tr></table></body></html>

![](images/0325ce423d3cca40e33ce6acba1f705fadd12f44713d70198ac0af79c26c1a8a.jpg)  
图4采样数为131072时GPU算法加速比

和CPU比较，GPU非相干消色散的数据能力达到几百倍的加速比，具有显著的加速优势。GPU并行算法的加速比性能如图4、图5及图6所示。

图4是在采样数为131072，通道和DM数均变化的情况下GPU并行算法的加速比。从图中可以看到，随着 DM数的增加，并行算法的加速比提高。当DM个数为2560时，TITAN V的加速比最高（即达到CPU速度的538倍），然后加速比开始下降。如图5所示，通道数量越多，GPU算法的加速比越大，得到的加速性能越好。当通道数为1024时，加速比最高；当通道数为32时加速比最小。

![](images/306c58f72e0dffb10842debd761904135be7afbd9f24dba798da87b011faabf2.jpg)  
图5DM数为5120时GPU算法加速比

图5显示的是当DM数为5120时，在通道数量和采样数都变化的情况下GPU并行算法的加速比。从图中可以看到，随着采样的增加，并行算法的加速有所下降，但算法加速高达550多倍。当通道数为1024时，TITANV达到最高的加速比。当通道数为1024、采样为8192时，GPU 并行算法是CPU算法速度的780多倍。

![](images/151bbd5ee96d0c6c999dca2a7fa716de8b075bbb84d983075352a190af50a9d6.jpg)  
Fig 5.GPU algorithm speed-up when the number of DMs is 5120   
图6通道数为1024时GPU算法加速比

图6 是在通道数为1024，采样和DM数都变化的情况下GPU并行算法的加速比。从图中可以看到，DM个数对GPU非相干消色散算法加速比影响最大。随着DM数的增加，GPU 并行算法的加速比迅速提高。如图6所示，DM个数越大，计算消耗时间越多，当DM数为5120时，加速比最大。

实验结果表示，采样数、通道数及DM值个数都是影响GPU 算法加速性能的关键因素。非相干算法执行中GPU展示了强大的并行化处理优势，节省了大量重复计算时间，提升了算法的计算效率。

# 4总结

本文研究基于GPU的非相干消色散算法，提出了相关算法的GPU并行化加速方案。分析了算法的密集型计算部分、研究了GPU多线程任务分配、管理及存器层次的优化方法，提高了GPU资源利用率，显著提升了算法的计算性能。在GPU算法的实现过程中，深入分析了影响并行算法性能的主要因素，优化了CUDA程序，大大减少了算法执行消耗时间，GPU消色散算法加速比接近700倍，解决了算法在CPU上计算量巨大无法实时处理的问题。通过实验分析了算法的数据处理消耗时间和加速比，验证了并行算法性能。

# 参考文献：

[1] Spitzer JrL.Physical processes in the interstellar medium[M].John Wiley& Sons,2008.   
[2]Barsdell,BlesBaesDG,etal.Aceleratingincoherentdedispersio[J].onthlyoticsofteoalAstrocal Society,2012,422(1):379-392.   
[3] 黄玉祥,汪敏,郝龙飞,李志玄,徐永华.脉冲星信号相干消色散与非相干消色散的比较研究[J].天文研究与技术(Huang Yuxiang， Wang Min，HaoLongfei，LiZhixuan，Xu Yonghua.Comparative Study betweethe Coherent De-dispersionandtheIncoherent De-dispersion of Pulsar Signal.Astronomical Research & Technology),2O19,16(O1):16-24.   
[4]托乎提努尔,张海龙,王杰.基于CUDA 的射电天文多相滤波器组设计[J].天文研究与技术(Tohtonur，Zhang Hailong，Wang Jie.A DesignofPolyphaseFilterBankforRadioAstronomyBasedonCUDA.AstronomicalResearch &Technology),2017,14(Ol):17-123. [5] 苏统华,李东,李松泽.CUDA 并行程序设计 GPU 编程指南[M].机械工业出版社(Su Tonghua,Li Dong,Li Songze.CUDA Programming:A Developer's Guide to Parall Computing with GPUs.China Machine Press),2014.   
[6] Rob Farber.高性能 CUDA 应用设计与开发[M].机械工业出版社(Rob Farber.CUDA Aplication Design and Development. China Machine Press)，2013.   
[7]PetroffE,OostrumLC,tappersBW,etal.Afastradioburstwithalowdispersionmeasure[J].MonthlyNoticesofheoyal Astronomical Society,2019,482(3): 3109-3115.   
[8] Cheng J,Grossman M,McKercherT.Professional CUDAC programming[M].John Wiley& Sons,2014.

# Incoherent Dedispersion Algorithm Based on GPU

Toktonur1,3， Zhang Hai1ong1,2,3\*,， Wang Jie¹,³，Ye Xinchen1,3 (1.Xinjiang AstronomicalObservatory,ChineseAcademyofciences,Urumqi 83oChina; 2.KeyLaboratoryofRadioAstroomy Chinese Academyof Sciences,Nanjing 210o8,China;3.National Astronomical Data Center,Beijing l00l01,China)

Abstract: In order to meet the requirements of real-time de-dispersion processing of pulsar signals，a GPU based incoherent de-dispersion algorithm isimplemented. Weuse high-performance parallel computing methods to conduct in-depth research on the incoherent de-dispersion algorithm for multi-thread processing,and propose a parallel acceleration scheme for the algorithm, which solves the problem that the de-dispersion algorithm has a large amount of calculation and cannot be processed in real time.We analyze the intensive computing parts of the algorithm, efciently use the hierarchical storage structure of the GPU,improve the utilization rate of GPU computing resources， thereby reducing the calculation time，and significantly improving the calculation performance of the incoherent de-dispersion algorithm.

Key words: De-dispersion; GPU; Parallel Computing; Real-time Processing