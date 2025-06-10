# WCDA时间标定系统的研制与测试

陈宝民1²，高博²,陈明君²，庞兆广1

（1.河北师范大学，石家庄10094;2.中国科学院高能物理研究所，北京100049）

摘要：地面水切伦科夫探测器实验（WCDA）是高海拔宇宙线观测站(LHAASO)项目的重要组成部分，主要物理目标是实现在甚高能中低能段（ $1 0 0 \mathrm { G e V } \sim 3 0 \mathrm { T e V } \ ,$ ）对整个北天区伽马源的巡天观测。为了确保对辐射源探测的指向准确性，需要对探测器阵列进行时间标定。本文主要介绍了WCDA探测器中时间标定方法、标定系统的搭建以及关键部件-分光光纤束的批量测试。

关键词：时间标定方法、标定系统搭建、光纤束批量测试中图分类号：P172.4文献标识码：A

# 1.简介

(1）时间标定方案

水切伦科夫探测器阵列（WCDA）是LHAASO的重要组成部分，主要功能是实现在甚高能中低能段（ $1 0 0 \mathrm { G e V } { \sim } 3 0 \mathrm { T e V } )$ 对整个北天区伽马源的巡天观测。包括甚高能伽马源的探测与监测、能谱测量以及扩展形态的研究。WCDA 探测器为水池结构，总面积 78000平方米，用黑色隔光帘分割成3120个探测单元，每个单元尺寸为 $5 \mathrm { m } { \times } 5 \mathrm { m }$ ，图1为WCDA探测器整体布局图，图中右下方1号水池每个探测单元采用1支8英寸直径和1支1.5英寸直径光电倍增管（PMT)，左下方2号水池、及上方3号水池每个探测单元内将布置1支20英寸直径和1支3.5英寸直径光电倍增管。1

![](images/8574f820df56d906ea6d5873bc80ed5552a533c1baff589b2847baf5c1e18061.jpg)  
图1：WCDA探测器分布图

WCDA每个探测单元用来探测簇射事例次级粒子产生的切伦科夫光。为了满足WCDA的性能指标，阵列指向精度要求好于0.1度，要求探测器时间标定精度要好于 $0 . 2 \mathrm { n s } ^ { 5 }$ 。该时间标定精度是通过Toy模拟得到的，模拟大气簇射粒子打在一个簇射区域内，得到角度分辨率和时间精度之间的关系式 $\delta t = \frac { \delta \theta } { A } \sqrt { ( N - 2 ) S }$ 。其中 80 是重建事例在不同设置的时间精度8t下对应的角分辨率，触发区域面积为S，PMT的击中数为N，大气簇射拟合的自由度为 N-2，A是一个常系数，它是对于不同的时间精度拟合得出A的平均值。大型探测器在标定方面通常采用统一的外部光源去照射所有探测单元的方法。对于WCDA，探测器占地面积大，各探测单元之间为了防止切伦科夫光的串扰选用了黑色隔光帘进行分隔，这一布局特点使其难以采用单一光源进行全阵列的标定。若采用光源加光纤的方法，对于单个水池光纤长度将需要 $2 2 0 \mathrm { m }$ 以上，这会对标定脉冲光的衰减及展宽影响很大，从而影响测试精度，且不利于安装维护。因此，为了实现全阵列的标定，WCDA采用了分布式标定的方案-“交叉标定”，基于电子学的布局，每 $6 { \times } 6$ 个单元组成一个cluster，一个水池包含 900 个探测单元，即25个cluster。通过先刻度cluster之间的相对时间差，再完成全阵列刻度的方式来标定。为此，每个cluster 放置两套 $\mathrm { L E D + }$ 光纤束的光源系统，其中一套光纤束用于标定cluster内部的36支PMT，另外一组光纤束，与相邻cluster进行光纤交换，以此来实现整个阵列内cluster交叉的目的（如图2）。

8888888888888888  
Jttlt LEDLA LEDJACluster Cluster j  
t00融  
1000lLEDiB LED

(2）交叉标定方法

选取中心cluster 作为基准cluster，其他cluster 通过一定的传导路径得到内部探测单元。对于相邻的cluster，假设ci_chi为待计算的cluster 内单元，cO_chO 为参考cluster 内的参考单元， $\Delta \mathrm { T }$ 为 ci_chi与cO_chO之间的时间差，即计算对象。

两个cluster之间共有8根交叉光纤，所在单元分别为ci_chx（x为光纤编号，定义为1,2,3,4)，和c0_chx 得到，通过一个交叉光纤(ci_chx)可以得到

$$
\Delta \mathrm { T } = T _ { c i \_ c h i } - T _ { c 0 \_ c h 0 } = \left( T I N _ { c i \_ c h i } - T I N _ { c i \_ c h x } \right) - ( T C R _ { c i \_ c h x } - T C R _ { c 0 \_ c h 0 } )
$$

公式(1)中， $\mathrm { T I N } _ { \mathrm { c i \_ c h i } }$ 为内部光纤待计算的cluster内单元对应的信号到达时间，TINci_chx为对应光纤编号为 $\textbf { \^ { x } }$ 的待计算的cluster 单元-对应的信号到达时间， $\mathrm { T C R } _ { \mathrm { c i \_ c h x } }$ 为对应光纤编号为 $\mathbf { x }$ 的参考cluster单元对应的信号到达时间， $\mathrm { T C R } _ { \mathrm { c 0 } \_ \mathrm { c h 0 } }$ 为参考cluster内的参考单元对应的信号到达时间。

相邻cluster共有四组光纤可用，理想情况下可以得到四组数据来验证光纤整个通道的标定。将4组数据取平均数值即可得到两个单元的时间差，

$$
< \Delta T > = \frac { { \displaystyle \sum _ { x = 1 } ^ { 4 } } ( \Delta T _ { i x } + \Delta T _ { 0 x } ) } { 4 }
$$

光纤的长短及弯折程度等都会在光强的传输过程中产生一定的衰减，为了保证探测器探测信号的均匀性，探测器安装前需要对使用的光纤束进行标定。每个cluster需要两套光纤，每套光纤需要36根，根据工程标定需求光纤束光强差异性不超过正负 $10 \%$ 。

# 2.标定系统搭建

时间标定系统主要由两部分组成：

# （1）光源系统

光源系统由LED、光筒（LightTube）和光纤分光束（FiberBundle）组成。LED的发光峰值波长为 $4 6 8 ~ \mathrm { n m }$ ，发散角为 $1 2 0 ^ { \circ }$ ，对应塑料光纤衰减长度为 $2 6 \mathrm { ~ m ~ }$ 。光筒是LED 光源和光纤束连接的关键部件，光筒一端固定LED，另外一端连接固定光纤束入光端，LED与光纤分光束入光端距离 $6 . 0 \ \mathrm { c m }$ ，两者中间等间距放置3个黑色不透明通孔隔板用于隔档杂散光使得光纤束接收到的LED光斑均匀度达到平均值的 $\pm 2 \%$ 水平。

分光光纤束是整个系统内最关键部件，承担着光传输的作用。WCDA探测器面积大，施工难，因此在研制时，每套光纤束设计为1分41，每根光纤长度设计为 $4 0 \mathrm { m }$ 以满足交叉标定的需要。

# （2）远距离触发系统

光触发系统由主控母板（Motherboard)和子板（Slave board)组成，两者通过RS485总线相连。RS485线连接主控母板和子板之间的通信，包括指令传输、发光频率、驱动脉宽控制，来调节LED发光状态。同一套光纤束内的PMT，通过接收经过分光光纤束分发后的同步LED信号，得到相对时间信息，再经过扣除光纤之间的时间差异以及数据修正，得到PMT之间的时间差。整个系统架构如图3所示。

![](images/07c543838df77e7bfe65d8a3cd38bceabdbd3e55f3461e698573dfd35e03018d.jpg)  
图3：WCDA1号水池时间标定构建布局图

# 3.光纤束的批量测试

为了满足探测器需求，每个cluster需要2套光纤束，在制作过程中，光纤束内部光纤之间存在一定的裁剪误差，每套光纤束内部光纤的相对时间差以及需要进行刻度。因此搭建了一套基于一维电动步进滑台以及基于VME/NIM机箱插件的半自动化批量测试系统。

(1）测试平台、测试方案介绍

首先将光纤束出光端依次固定在一维电动滑台支架上，使用LED 触发板给予10 ns脉宽信号驱动LED发光。LED发出的光脉冲信号经过光纤束到一支快速PMT上，通过高压插件给PMT提供工作高压，PMT输出信号通过信号分发板，10倍快速放大器、前沿甄别器后分别接入到TDC和QDC插件以分别收集时间和电荷信息。通过严格刻度光纤之间的距离，使得每次步进电机运动后，只有一根光纤能够正对PMT光阴极中心。通过上位机脚本控制步进滑台驱动器以及DAQ程序，实现一套光纤束内每根光纤的自动扫描，分别得到光纤输出光强的均匀度以及光纤时间的时间差。该平台通过长时间测试标定，系统误差为 $5 . 4 0 \mathrm { p s }$ ，完全满足测试进度需求。

![](images/0b5082df47f16c697f14db53ba7b5b8c4a2908172207641e5335de34d1676c77.jpg)  
图4：光纤测试流程图

(2) 测试结果$\textcircled{1}$ 光强均匀度

经过步进电机的扫描，在 $1 0 \mathrm { n s }$ 脉宽信号驱动条件下，LED发光通过 $6 \mathrm { c m }$ 的光筒，然后照射到光纤束的入光端，其中一套光纤束41根光纤的光强往复扫描测试结果如图5所示，可以看到差异性在 $10 \%$ 范围内，扫描结果在如图5中也有体现，可以看出重合度很高，系统稳定性很好。

![](images/20ac6289c5e6cd3891ccd606f7cff6ecb68efb188a87e1b388e005d0594bf3a8.jpg)  
图5：光纤重合度测试结果

通过上述测试系统，将53套光纤全部测试完毕，得到批量测试结果，测试过程中为了工程需要采用不同的LED和光筒与光纤束配套，得到53套光纤光强的批量测试结果如图6，可以看出每套光纤束光强平均值均在350-600ADCcount范围内。53套光纤合格根数统计结果用图7表示，可以看出每套光纤至少有36根光纤达到工程标定需求，从中选取50套光纤，部署在WCDA的1号水池。

![](images/bcf79aeebad14f559ada4dd1e4f180fe612397bac8c1deb754ae8d700accf4c9.jpg)  
图6：光纤批量测试光强分布图

![](images/e02d3c48233237fae4f0d90ea589b81c46c3a82fe13356bbfbf5e7bd67fc0b3f.jpg)  
图7：53套光纤合格数统计分布

横坐标为光纤编号，纵坐标为光纤束合格根数

$\textcircled{2}$ 时间差

利用上位机控制装有光纤束的步进滑台行进，测试得到每一根光纤对应的时间信息，经过步进电机的扫描，在10ns光强下，LED发光通过 $6 \mathrm { c m }$ 的光筒，其中一套光纤束41根光纤的时间测试结果如图8所示。

图中将每根光纤的时间测量结果与41根光纤时间平均值的差值作统计，横坐标为每根光纤的编号，纵坐标为时间差，可以看出其时间的差值不超过$0 . 4 ~ \mathrm { { n s } }$ 。

![](images/8c364dfbedd99e8ca85824c0e66c8da6ab4b9146e77dd85cbfd50a74d95480ec.jpg)

# 4.结论

LHAASO-WCDA的时间标定系统对整个探测器进行标定，本文对整个时间标定系统的布局及方法进行了介绍，并对其核心部件光纤束进行了批量测试，另外对测试平台的研制进行了说明，53套光纤束能够满足36根光强的一致性在平均值的 $\pm 1 0 \%$ 范围内，时间差分布差异相对平均值在 $\pm 0 . 4 \mathrm { n s }$ 范围内，达到了探测器的标定需求。时间标定系统的研制确保了探测器数据的准确性，为今后的探测器的标定工作提供了宝贵经验。

# Development and testing of WCDA time calibration system

Chen Baomin1², Gao $\mathbf { B o } ^ { 2 }$ , Chen Mingjun², Pang Zhaoguang (1.HebeiNormal University, Shijiazhuang10094;

2.Institute of High Energy Physics,Chinese Academy of Sciences,Beijing 100049)

Abstract: The Water Cerenkov Detector Array (WCDA) is an important part of Large High Altitude Air Shower Observatory (LHAASO). The main physical goal is to achieve a survey of the gamma source of the entire northern sky in the very high energy middle and low energy section 1 $( 1 0 0 \mathrm { G e V } \sim 3 0 \mathrm { T e V } )$ ). In order to ensure the accuracy of the detected radiation source,the detector array needs to be time-calibrated. Therefore,the time calibration method and calibration system construction of the WCDA detector should be studied,and the key component-split fiber bundle should be tested in batches.

Keywords: Time calibration method. Calibration system construction.Fiber bundle batch test

# 参考文献

1.Z.G.YAO et al.,Designand performanceofLHAASO-WCDA experiment,Procedingsofthe32nd International CosmicRayConference,ICRC 2011. Vol.9,2011，pg. 3.  
2.L.Zhaoetal.,Desigof thereadout electronicsprototype forLHAASO WCDA,Procedingsof the2Oth IE-NPSS Real TimeConference,2016,pg. 3.  
3．游晓浩,LHAASO-WCDA 时间标定的研究[D].河北师范大学，2014.  
4．高博,LHAASO-WCDA 电荷标定与时间标定的研究[D].中国科学院高能物理研究所，2013.  
5．J.Y.Liuet al.,Testbench for fibersoftheLHAASO-WCDAtime calibrationsystem,2017,JINST12,P10021.