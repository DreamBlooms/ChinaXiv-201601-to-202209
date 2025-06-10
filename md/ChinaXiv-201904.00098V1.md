# 基于FPGA的CCD视频波形发生器\*

张毅，张鸿飞，陈诚，唐琪杰，王坚（中国科学技术大学近代物理系，核探测与核电子学国家重点实验室，安徽，合肥230026）

摘要：为了测试用于南极CSTAR(Chinese Sma11Telescope Array）望远镜的CCD(ChargeCoupled Device）控制器视频采样电路的性能并对其进行低温可靠性验证，设计了一款基于FPGA的CCD视频波形发生器，它能产生CCD探测器输出的视频波形。上位机通过USB2.0接口与视频波形发生器进行指令通讯，可以改变波形的幅度、周期、上升沿时间以及叠加的噪声。通过设定不同参数的波形输入到CCD控制器的视频采样电路可以在不同温度下对电路的性能进行充分测试，不仅提高了测试效率而且有效地避免了安装CCD测试造成的风险。测试结果表明CCD控制器的视频采样电路性能满足要求并可以在低至 $- 8 0 ^ { \circ } \mathrm { C }$ 下稳定工作。

关键词：CCD视频波形发生器；真随机数发生器；FPGA；性能测试；低温可靠性验证;

中图分类号：TP337 文献标识码：A 文章编号：

# 1引言

随着电子技术的快速发展，科学级CCD探测器由于它在可见光波长下高达 $9 0 \%$ 的量子效率，超低读出噪声，高分辨率，宽光谱响应范围等优点广泛应用于天文[1观测领域。在天文观测中，观测台址的选择十分重要，在空间卫星上观测无疑是最佳的，Kepler 空间卫星曾对天鹅座附件约 $\mathrm { 1 0 0 d e g ^ { 2 } }$ 的天区进行了长达四年的观测，探测到了大量的系外行星、变星及恒星耀发事件[2]。然而空间卫星的建造及其昂贵，天文学家们继而把目光投向了南极这个具有低风，低湿度，大气平静的地点，同时南极没有大气污染，光污染，还具备长达数月的极夜[3]，这些有利的观测条件驱使着我国天文学家对南极的探索。2006年底，我国科学家提出了在南极冰穹A 建造首台天文仪器的计划，即中国南极小望远镜阵CSTAR，两年后 CSTAR望远镜成功安装在南极内陆最高点DOMEA，CSTAR是由4个10cm的望远镜组成，望远镜固定地指向南天极，其主要的科学目标是进行变星监测，获得多波段长时间的连续光变曲线，用于暂现天象如新星及超新星等观测，搜索系外行星等。同时CSTAR 的另一重要功能是天文台址测量，进行天光背景、云量和透明度的测量以及连续晴夜的统计[4]。虽然南极拥有诸多观测优势，但是其恶劣的条件也对望远镜系统的电子学及结构设计造成了极大的考验。根据南极CSTAR天文望远镜的观测要求以及低温可靠性的考虑，中国科学技术大学基于E2V 公司的CCD 47-20芯片设计了一款科学级CCD相机[5]。图1为CCD相机在南京天文光学技术研究所安装CSTAR望远镜的测试现场图片。

![](images/141350322c55c12cd002688ae9d3e913a1b3ed5c4e535726fa64a962d7cb5e22.jpg)  
图1.CCD相机安装在CSTAR望远镜测试图片  
Fig.1The test picture of CCD camera installed in CSTAR telescope

CCD 相机主要由真空腔体，快门，电源系统以及CCD 控制器组成。CCD 控制器提供CCD工作所需时钟信号和偏压信号，并将CCD输出的视频信号进行放大采样等处理，同时还具备一定的自检功能。视频采样电路是CCD控制器的关键部分，它直接决定了整个系统能否成像以及图像噪声的大小，因此需借助外部设备产生CCD视频波形输入到控制器进行系统测试。通常的做法是基于直接数字频率合成（DDS）技术产生任意波形，并利用可编程逻辑器件对整个系统加以控制，从而输出满足需求的CCD视频波形。如美国布鲁克海文国家实验室针对大型综合巡天望远镜（LSST）上的CCD 相机设计的CCD仿真器，使用12位DAC 通过高带宽运放驱动后可输出 $1 . 2 3 \mathrm { M H z }$ 的CCD视频波形。该技术在国内也有多处应用案例，如基于FPGA 设计的用于航天相机数据采集系统的TDI-CCD信号发生器7]，以及基于CPLD设计的用于CCD相机的信号发生器[8等。

本文针对CSTAR 相机控制器视频采样电路的测试设计了一款CCD视频波形发生器。整个系统由Altera公司的CycloneIV FPGA主控，可以模拟CCD输出的视频波形并能叠加不同大小的随机噪声，通过上位机的简单设定可以快速地对视频采样电路进行测试，不仅提高了测试效率而且极大程度上降低了CCD探测器损坏的风险。

# 2系统结构

整个CCD控制器以及视频波形发生器的系统框图如图2所示。上位机通过两个控制软件分别控制CCD控制器和CCD视频波形发生器，命令通过两个USB接口分别下发。控制器控制软件可以根据视频波形发生器产生的CCD 波形生成图像，通过感兴趣区（ROI）的选取可以自动计算出当前区域内像素均值以及均方差，以便分析视频采样电路的功能及性能。

CCD视频波形发生器由FPGA、USB2.0、视频波形产生电路、真随机数发生器（TRNG）以及电源组成。整个系统由FPGA主控，USB2.0用于下发指令参数、传输图像数据。视频波形产生电路可以根据上位机控制软件设定产生相应的CCD视频波形，也可以将一帧特定图像的像素值存入Flash，通过FPGA逻辑算法将像素值逐个转换后由视频波形发生器还原相应的CCD 视频波形。真随机数发生器基于FPGA内部震荡环的抖动设计，通过FPGA输出的使能信号来控制整个随机源，产生的随机噪声用于模拟CCD 芯片的读出噪声，随机噪声的大小可以通过视频波形发生器控制软件设定随机数的位宽来调节。控制器的触发时钟通过接插件连接至CCD 视频波形发生器，产生的视频波形通过同轴电缆线输入到视频采样电路输入端。

![](images/c92c53ad8b8013972ec04ab2ba4bcfd549aa9c9c9f7b532cc3395eb13d222401.jpg)  
图2.系统整体框图

# 2.1视频波形产生电路

通常科学级CCD输出的视频波形为三段台阶式波形，如下图3中Output信号，其中第一段台阶为复位电平，由R时钟上升沿触发。第二段台阶为参考电平，由R时钟下降沿触发。第三段台阶为像素电平，由R3时钟下降沿触发。当光子入射时，会在CCD探测器内部 MOS电容器的半导体材料中激发出电子形成电势差，该电势差对应CCD视频波形参考电平与像素电平的差值，视频采样电路通过相关双采样[（CDS）处理后得到有效像素值。为了使产生的视频波形的相位与实际CCD输出的视频波形一致，需要CCD控制器产生的R时钟和 R3 时钟来触发视频波形的不同阶段，以便视频采样电路能够准确得到每个周期的有效像素值。控制器输出到视频波形发生器的R时钟和R3时钟经过分压后进入比较器转换成LVTTL信号，通过分压电阻调节合适的比较器参考电压。受限于控制器的视频采样电路，目前读出速度最高支持到800kPixel/s，本设计采用 ${ 1 0 0 } \mathrm { M H z }$ 的FPGA时钟不断采样比较器的输出信号，从而判断触发时钟的电平变化。

![](images/e86a271c510d36db2279c20334347d52bb1d5db35d06cebbb243be35d43aca98.jpg)  
Fig.2 System overall block diagram

视频波形产生电路如图4所示。由500MSPS 高速DAC（max5888）、低通滤波模块和高速低噪声运放构成。由于输出的视频波形由R 时钟和R3 时钟触发，因此其频率与控制器设定的读出速度一致，最高为 $8 0 0 \mathrm { k H z }$ ，所选用的DAC足以满足设计需求。FPGA通过16位LVDS 数据和LVDS 时钟控制DAC，DAC 输出的差分电压信号 $V _ { \mathfrak { p } }$ ， $V _ { \mathrm { n } }$ 经过低通滤波模块后滤除高频噪声，高速低噪声运放将差分信号转换成单端信号输出。运放输出电压与DAC数据码之间的关系如式1所示

$$
V _ { \mathrm { o u t } } = \left( 2 \times \frac { D a t a _ { \mathrm { c o d e } } } { 2 ^ { 1 6 } } - 1 \right) \mathrm { { V } } \mathrm { ~ \ . ~ }
$$

式中： $V _ { \mathrm { o u t } }$ 为运放输出的电压， $D a t a _ { \mathrm { c o d e } }$ 为 DAC 的数据码，由于DAC 的分辨率为16 位，因此该视频波形产生电路输出的信号范围为-1V到 $\mathrm { 1 V }$ 。根据CCD47-20手册，其输出响应率为4.5$\mu \mathrm { \ V / e } ^ { - }$ ，满阱电子数约为10万个电子，因此在过曝光的情况下CCD 视频波形参考电平与像素电平之间的最大压差约为 $4 5 0 \mathrm { m V }$ ，所以该视频波形产生电路可以满足测试需求。

![](images/0a2a55ef061f1e4c2c5e54f4a9ae2793a26733ece3db92e8404a5381c1a352c6.jpg)  
图3．CCD47-20视频输出信号  
Fig.3 Video output signal of CCD47-20   
图4.视频波形产生电路  
Fig.4 Video waveform generation circuit

# 2.2真随机数发生器

真随机数发生器基于FPGA内部震荡环的抖动作为随机源设计，将产生的随机数同步的叠加到DAC 输出码上可以模拟CCD芯片的读出噪声，其框图如图5所示。本设计在FPGA 内部使用25个反相器首尾相连构成一个闭合回路作为一个震荡环，随机源由 24路震荡环组成通过使能信号控制产生高频震荡时钟，该时钟周期仅与反相器门延时有关，相比于用 PLL或 DLL 等采取反抖动措施产生的时钟，其具有更大的抖动[10]。随机源输出的高频时钟经过D触发器进行第一次采样，采样时钟为 ${ 1 0 0 } \mathrm { M H z }$ 。24位采样结果经过异或（XOR）处理后，通过D触发器进行二次采样输出一位随机数，采样时钟为 ${ 1 0 0 } \mathrm { M H z }$ 。在不需要随机噪声的情况下可以通过控制软件关闭随机源从而减少系统功耗。

![](images/3261ed7ff723964b74bc9bb71923cf5a81fb6c2ceddeba7cf0db96c18ca36918.jpg)  
图5.真随机数发生器

图6所示为在实际测试中使用SignalTap 来采样4bit 随机数的一段结果。

![](images/4ed486eea645241bb685663b778940da63a06f8d9c63e342800922c9a5e28471.jpg)  
图6．SignalTap 采样4位随机数的结果  
Fig. 6 Result of 4 bits random number sampled by SignalTap

# 3FPGA逻辑实现

视频波形发生器的FPGA逻辑框图如图7所示，包括USB 通信模块、命令解析模块、随机数产生模块、DAC 数据整合模块、Flash控制模块、图像数据处理模块以及DAC 输出模块，各个模块由FPGA 控制协同工作。

![](images/2cdb408c65c49e9303e0d77e3cb3e776d5d32162a12602cfb14379f21986bec5.jpg)  
Fig.5True randomnumber generator   
图7．FPGA逻辑框图  
Fig.7FPGAlogic block diagram

USB通信模块负责接收上位机下发数据，下发数据类型分为指令数据和图像数据。基本指令包括设定视频波形各个阶段电压值、设定视频波形上升沿/下降沿时间、设定真随机数发生器使能或失能以及设定随机数位宽，通过上位机设定参数后，视频波形发生器伴随触发时钟产生重复的周期性信号。图像数据为一帧特定图像的像素值，通过USB存入Flash 中。当命令解析模块产生开始读出标志位后，Flash控制模块依次读出每个像素值并输出到图像数据处理模块中。图像数据处理模块有两个功能，一是在R时钟上升沿和下降沿触发下向DAC 输出模块输出复位电平和参考电压所对应的DAC数据码，默认情况下逻辑将复位电平设成 $1 0 0 \mathrm { m V }$ ，参考电平设成 $5 0 \mathrm { m V }$ 。二是根据Flash控制模块输出的像素值以及视频采样电路增益计算出CCD视频波形中参考电平与像素电平之间的压差，并将此压差转换成DAC输出码，在 R3 时钟下降沿触发下输出给DAC 输出模块。在还原一帧特定图像模式中，DAC 输出模块以 ${ 1 0 0 } \mathrm { M H z }$ 的主频持续输出数据到DAC中，当有图像数据处理模块触发时，则输出当前数据，若无触发时，则输出上一时刻的数据直到下一次触发到来。

命令解析模块将指令解析后向后续相关模块传递参数及标志位。若产生随机数使能信号，随机数产生模块以 ${ 1 0 0 } \mathrm { M H z }$ 的主频输出相应位宽的真随机数到DAC数据整合模块。在上位机设定CCD 波形的模式中，命令解析模块将CCD各阶段幅度值所对应的DAC数据码以及上升沿/下降沿时间输出到 DAC 数据整合模块。DAC 数据整合模块有两个功能，一是在DAC 数据码上叠加真随机数，并将数据以 ${ 1 0 0 } \mathrm { M H z }$ 的主频传递给DAC 输出模块。二是在R和R3 时钟触发到来时，根据上升沿/下降沿时间计算波形跳变阶段每个点所对应的DAC 数据码，例如当上升沿设定为 $1 0 0 \mathrm { n s }$ ，复位电平和像素电平分别设定为 $1 0 0 \mathrm { m V }$ 和 $0 \mathrm { m V }$ 时，采样点将从0mV每次增加 $1 0 \mathrm { m V }$ 在10个周期内达到复位电平幅度。在上位机设定波形模式下,DAC输出模块由 DAC数据整合模块触发将产生的数据输出到DAC中，产生用户设定的CCD视频波形。

其中DAC 数据整合模块以及DAC 输出模块的工作主频均为 ${ 1 0 0 } \mathrm { M H z }$ ，对于 $1 0 0 \mathrm { k H z }$ 的视频波形，一个周期内可还原1千个采样点，足以满足测试需求。

# 4 测试结果

![](images/e0cd3799af1cf35fc22eb0fbf12a604f3c6e38e25f2cedd2c8c158f4a9bd3545.jpg)  
图8.测试流程图  
Fig. 8 The picture of test flow

在测试过程中系统工作的流程框图如图8所示。首先通过视频波形发生器控制软件设定波形幅度、上升沿/下降沿时间、以及所叠加的噪声位宽。再通过控制器控制软件设定读出参数，包括读出速度、积分时间、前放增益高低选择。所有参数设置完毕后通过控制器控制软件下发开始曝光指令，视频波形发生器会根据R时钟和R3时钟的变化输出实际的 CCD 视频波形，该波形进入视频采样电路采样后得到像素值，通过USB2.0接口传至上位机，在控制器控制软件上生成一帧图像，供用户分析。图9是通过将特定像素值固化到Flash后，通过 FPGA 控制产生的CCD视频波形以及还原得到的图像。整幅图像亮度从左到右依次减小，呈规律的条纹状，与预期一致。

![](images/f46e2a7336999b58d9994c6aeb3f48dc7ad5b5fbacf1c38c4de4feadf582b57b.jpg)  
图9. CCD视频波形及还原图像  
Fig.9 CCD video waveform and restored image

在视频采样电路的性能测试中，通过视频波形发生器控制软件设定产生一个均匀平场的CCD 视频波形，其复位电平，参考电平以及像素电平分别固定为 $1 0 0 \mathrm { m V }$ ， $5 0 \mathrm { m V }$ ， $0 \mathrm { m V }$ ，上升沿/下降沿时间为 $1 0 0 \mathrm { n s }$ ，并通过控制器控制软件设定读出速率为100kPixel/s。

在室温下将CCD视频波形分别叠加1到8位随机数噪声后，输入到CCD控制器的视频采样电路，通过实际叠加的噪声与视频采样电路测量的像素值均方差之间的关系，来评估视频采样电路的性能。根据多次测试结果，当不叠加随机噪声时，视频采样电路测量10万个采样点像素值的均方差大约为7.3ADUrms。参考电平和像素电平之间的差值如式2所示

$$
F \left( \Delta V \right) = \left[ \left( F \left( r e f \right) - F \left( p i x \right) \right) + \left( F \left( n r e f \right) - F \left( n p i x \right) \right) \right] .
$$

式中： $F { \big ( } \Delta V { \big ) }$ 为叠加随机噪声后参考电平和像素电平之间的差值， $F \big ( r e f \big )$ 和 $F \big ( p i x \big )$ 分别表示在不叠加随机噪声时参考电平值与像素电平值， $F \big ( n r e f \big )$ 和 $F \big ( n p i x \big )$ 分别表示在参考电平和像素电平上叠加的噪声值，则 $F { \big ( } \Delta V { \big ) }$ 的均方差如式3所示

$$
\sigma F \big ( \Delta V \big ) = \sqrt { \sigma ^ { 2 } \big [ F \big ( r e f \big ) - F \big ( p i x \big ) \big ] + \sigma ^ { 2 } F \big ( n r e f \big ) + \sigma ^ { 2 } F \big ( n p i x \big ) } \ .
$$

式中： $\sigma F { \bigl ( } \Delta V { \bigr ) }$ 为 $F { \big ( } \Delta V { \big ) }$ 的均方差， $\sigma ^ { 2 } \left[ F \left( r e f \right) - F \left( p i x \right) \right]$ 为参考电平与像素电平压差值的方差，即为7.3ADUrms²。 $\sigma ^ { 2 } F \bigl ( n r e f \bigr )$ 和 $\sigma ^ { 2 } F \bigl ( n p i x \bigr )$ 分别为在参考电平和像素电平叠加随机噪声的方差。随机数可近视为在 $\left[ 0 , 2 ^ { n } - 1 \right]$ 区间内服从均匀分布，其方差计算如式4所示

$$
\sigma ^ { 2 } R _ { \left[ 0 , 2 ^ { n } - 1 \right] } = \frac { \left( 2 ^ { n } - 1 \right) ^ { 2 } } { 1 2 } .
$$

式中：n为随机数的位数， $\sigma ^ { 2 } R _ { [ 0 , 2 ^ { n } - 1 ] }$ 为祎 $\mathfrak { n }$ 位随机数噪声的方差。因此，当不同的随机数噪声叠加到DAC输出码时，理论测量的像素值均方差与随机数位数的关系如式5所示。

$$
\sigma F \big ( \Delta V \big ) = \sqrt { \frac { 1 } { 6 } \times \big ( 2 ^ { n } - 1 \big ) ^ { 2 } + 7 . 3 ^ { 2 } } \mathrm { ~ . ~ }
$$

图10将视频采样电路实际测量像素值均方差的结果与理论值进行了对比，在叠加1到8位随机噪声后，通过式（5）计算而得的理论像素值的均方差如图10中虚线 STD2 所示。视频采样电路实际测量10万个采样点像素值的均方差如图10实线STD1所示。根据测试结果，两条曲线基本重合，这说明控制器视频采样电路的性能满足要求。

![](images/0096ce30d0193b891bd70a7a4e2473ae56bd30942a585d0f579acc68de4e0047.jpg)  
图10.像素值均方差与随机数位数的关系  
Fig.1O Relationship between pixel value Standard deviation and random number bit

此外我们利用该视频波形发生器对控制器视频采样电路进行了长期的低温测试，测试结果表明控制器在低至 $- 8 0 ^ { \circ } \mathrm { C }$ 的温度下可以正常成像，说明视频采样电路满足南极的低温需求。

# 5总结

本文设计了一款基于FPGA的CCD 视频波形发生器模拟CCD 输出的视频波形，可以在不安装CCD芯片的情况下，通过上位机的简单设定快速有效地对CCD控制器进行测试，避免了安装CCD测试所造成的风险。针对南极CSTAR相机控制器的视频采样电路做了详细测试，其结果表明视频采样电路的性能满足我们的要求，也间接证明了控制器的时钟电路在低至 $- 8 0 ^ { \circ } \mathrm { C }$ 的温度下可以正常工作。该视频波形发生器还可以应用于其它科学级CCD视频波形的仿真，对后续其它控制器的研发及测试提供了诸多便捷。

# The design of the CCD video waveform generator based on FPGA

ZHANG Yi, ZHANG Hong-fei, CHEN Cheng, TANG Qi-jie, FENG Yi, WANG Jian-min, WANG Jian

(Department of Modern Physics，University of Science and Technologyof China, State Key Laboratory of Nuclear Detection and Nuclear Electronics，Hefei Anhui，23o026,China) Abstract: In order to test the performance of the video sampling circuit of the CCD(Charge

Coupled Device) controller for an Antarctic CSTAR(Chinese Small Telescope Array) and verify low temperature reliability, a CCD video waveform generator based on FPGA was designed for generating the video waveform output by CCD detector. A computer can communicate with the video waveform generator through the USB2.O interface, which can change the amplitude, period, rising edge time and the superimposed noise of the waveform. The performance of the circuit can be fully tested at different temperatures by setting the waveform with different parameters and input to the video sampling circuit of the CCD controller, which not only improves test efficiency but effectively avoids the risk of installing the CCD test.The test results show that the performance of the video sampling circuit of the CCD controller meets the requirements and can work stably as low as $- 8 0 ~ ^ { \circ } \mathrm { C }$

Key words: CCD video waveform generator; True random number generator; FPGA;  
Performance test； Low-temperature reliability verification;

# 参考文献：

[1] 陈建军,李彬华,张牛虎等．一种天文用CCD 相机的电路设计[J]．天文研究与技术——国家天文台台刊，2009，6(02)：130-135.Cheng Jianjun,LiBinhua,Zhang Niuhu,etal.Designof electroniccircuits foranastronomical CCDcamera[J].AstronomicalResearch and Technology—Publicationsof National Astronomical Observatoriesof China,2O09,6(2):130-135.  
[2] 王松虎．基于CSTAR 的系外行星探测及后续研究[D]．南京：南京大学，2016.  
[3] Yang,H.KulsaC.A.,Walke,C.K,al.“Exetioalteraertrspaecdabilityboe,trctica,122,490-494 (2010).  
[4] 宗伟凯，付建宁，牛家树，等.2009 年南极冰穹 A 的双色天光背景统计和分析[J].天文研究与技术——国家天文台台刊，2013,11(1): 89-94.Zong Weikai,FuJianning,Niu Jiashu,etal.SkyBrightness Values in the SDSS $\mathbf { g }$ and r Bands at the Dome Aof the Antarctica in2009 [J].Astronomical ResearchandTechnology—PublicationsofNationalAstronomicalObservatoriesofChina,21,1():89-94.  
[5] Hong-fei Zhang,Jian-min Wang,YiZhang,etal.“ScientificCCDcameraforCSTARtelescopeinAntarctica,”Proc.SPE10709,High Energy,Optical,andInfraredDetectors forAstronomyVI,107091Q(July018);doi:10.117/12.309892.  
[6] LuW,OConnorP,FriedJ,etal.CCDemulatordesignforLSSTcameraC/HighEnergy,Optical,and IfraredDtectors forAstronomy VII.International Society for Optics and Photonics,2016,9915: 99152O.  
[7] 宋小龙,张犁,石光明.基于FPGA 的高精度 TDI-CCD 信号发生器的设计[J].电子科技,2007(04):1-4.Xiaolong S,Li Z, Guangming S.A High Accuracy TDI-CCD Signal Generator Based onFPGA[J]. Electronic Science andTechnology,2007,4: 1-4.  
[8] 姜博，阮锦.基于CPLD的CCD 信号发生器的研究[J].微计算机信息,2009,25(17):267-269.JiangBo,RuanJin.DesignofCCDsignal generatorbasedonCPLD[J].MicrocomputerInformation,2009，25(17):267-269.  
[9] 许秀贞，李自田，薛利军．CCD 噪声分析及处理技术[D]．2004.  
[10]张鸿飞，王坚，罗春丽，等．基于抖动的高速真随机数发生器的设计和实现[J]．核技术，2011，34(7)：556-560.Zhang HF,WangJ,LuoCL,etal.Developmentofahigh sped truerandomnumbergeneratorbasedonjiter[J].NuclTech,2011,34(7): 556-560.