# 新疆天文台南山站DBBC2数字终端系统的建立

杨文军1,4，杨军²，江悟，夏博³，李健1，崔朗1，张华1，李鹏1，高志福1（1.中国科学院国家天文台新疆天文台，新疆 乌鲁木齐 830011；2.查尔姆斯理工大学 Onsala 天文台，瑞典 43992；3．中国科学院上海天文台，上海 200030；4.中国科学院射电天文重点实验室，新疆 乌鲁木齐 830011)

摘要： 随着计算机数字技术的高速发展，甚长基线干涉仪测量（Very Long Baseline Interferometry，VLBI）所需的关键观测终端设备基带转换器（Base Band Converter，BBC）已从模拟系统（Analog BBC，ABBC）发展为数字系统（Digital BBC，DBBC）。相对于模拟系统，数字系统具有很高的灵活性，并能成倍地提高 VLBI观测带宽，进而能满足各种高灵敏度的VLBI观测需求。考虑到这些技术优势，以及新疆天文台南山站在国内和国际VLBI网中的重要作用，南山站 2016年对 VLBI终端系统进行了升级，引进了一套意大利 Hat-Lab 公司研发的DBBC2 终端。介绍了欧洲 DBBC2 系统的主要构成模块和工作原理以及系统的组装、连接、配置、校准和调试方法。在对系统硬件和软件进行全面的检测和测试后，与国内和国际的主要台站开展了联合观测，并多次成功获得相关干涉条纹。这一系列的成功观测表明，南山DBBC2 系统已成功安装，并具有很高的可靠性。应用新的 DBBC2 系统，南山站可参与 2/4Gbps 的记录速率的宽带VLBI观测，极其有助于天文学家对宇宙中更暗弱的射电源开展毫角秒分辨率的成图观测。

关键词：DBBC2系统；甚长基线干涉测量；基带转换器中图分类号：p111.44 文献标识码：A 文章编号：1672-7673

射电观测由于信号频率高、频带宽，一般要经过下变频为中频，再分为若干一定带宽的通道。VLBI网把完成这一数据采集过程的设备叫做基带转换器[1-2]。南山站目前拥有两套上海天文台生产的数字基带转换器（Chinese DataAcquisition System，CDAS）[3]和一套美国生产的模拟基带转换器。其中数字基带转换器主要用于国内联测和东亚联测，模拟基带转换器主要用于欧洲VLBI网（The European VLBI Network，EVN）和 IVS（International VLBI Service forGeodesy&Astrometry）国际联测。2010年以后，国际许多台站的模拟终端逐步更新为数字终端。当前较为流行的是欧洲数字基带转换器，其中DBBC1系统主要是测试产品，未进行推广，而DBBC2系统已经广泛应用于欧洲VLBI网天文观测台站。近几年，DBBC3数字终端系统也已研制出来，它将应用于欧洲VLBI网天体物理宽带VLBI终端系统和测地VGOS（The VLBI2010 Global ObservingSystem)超宽带VLBI系统中[4]。目前DBBC3数字终端系统已在瑞典OnsalaVLBI测站进行了测试并取得成功。南山站的模拟基带转换器建造于20世纪80年代末，使用至今已进行过多次升级和改造，由于设备使用过久，许多器件早已停产，使得设备维护比较困难，维护成本也相对较高。另外，随着电子技术的高速发展和天文观测需求的提高，南山站的模拟基带转换器已经远远不能满足未来的天文观测要求，为此南山站于2016年从意大利HAT-Labs.r.1公司购进了一套DBBC2数字终端系统，该系统经过数月的检测和调试后，与国内和国际主要台站开展了VLBI联合观测并成功相关出干涉条纹。实践表明，该套DBBC2系统已完全能够取代模拟基带转换器并参加未来国际和国内的各项联合观测。

# 1DBBC2系统基本原理和组成

DBBC2系统主要由模拟信号调节模块、AD采样器、数据处理模块CORE、连接伺服器、FILA10G 模块、时序和时钟板以及PC 机组件等构成[5-6]。

中频信号IF送到模拟信号调节模块，经滤波整形和增益控制后送到AD 采样器，变成数字信号后经高速输入总线（High Speed Input，HSI）到数据处理模块CORE，进行数字下变频（DigitalDownConvert），滤波变成数字基带信号，最后经HSO 总线（High Speed Output）和第2块FILA 板的VSI接口输出。VSI接口可连接到Mark5B[1]数据记录设备或连接到FILA10G 模块。1024MHz频率综合器产生AD采样器所需的采样时钟。PC机组件接收FS计算机发送的命令，经PCI总线控制DBBC2，原理如图1。

![](images/e7a5de7354be2e57889fb40823898c9484f252ce18636ff8a88ddfd1f17d5d93.jpg)  
图1.DBBC2原理图  
Fig.1 DBBC 2Schematic Diagram

# 2 DBBC2结构

DBBC2系统安装在 $4 8 3 \mathrm { m m }$ 宽， $3 7 0 \mathrm { m m }$ 高， $5 0 0 \mathrm { m m }$ 深的机箱内。在DBBC2前面板下边，蓝色指示灯表示主电源开关有效，如图2。在后面板上有多个连接器件和接口，其中在左下角有3个开关，1个大的，2个小的，大的作为普通主连接，2个较小的电源开关中，红色按钮开关用于电子设备供电，绿色按钮开关用于内部PC机系统供电。开机顺序从左到右依次打开，关机顺序正好相反，如图3。

![](images/222d5addc1f78fbc41f4f5f4eec01bc3f4f0860e5a5eadf753e69b4e738f0f2d.jpg)  
图2.DBBC2前面板图Fig .2 Front panel picture of DBBC2

![](images/05bed531d3cfca7e4628526722b4754e7f404f49a4b2e6bedf3947186c75db16.jpg)  
图3.DBBC2后面板图 Fig.3 Rear panel picture of DBBC2

DBBC2内部结构主要包括电子部分、PC部分、散热系统和电源系统4大部分，如图4。

![](images/e8547d07c743f274768890fe3881511e4ddb0f7c1ae3a7cd6a9d08ebbba66c24.jpg)  
图4.DBBC2 内部机构  
Fig.4 The internal structure of DBBC2

# 3 DBBC2主要性能指标

DBBC2主要性能指标[5]如表1。

表1DBBC2 性能指标 Table1Performance index ofDBBC2   

<html><body><table><tr><td>主要参数</td><td>性能指标</td></tr><tr><td>自带中频滤波可选输出中频信号 (MHz)</td><td>1（1-512），2（512-1024），3（1024-1536），4（1536-2058)</td></tr><tr><td>通道带宽（MHz）</td><td>V105E:32,16.8,4,2,1</td></tr><tr><td>A/D采样器</td><td>采样时钟：1024MHz</td></tr><tr><td>数据处理模块</td><td>CORE2</td></tr><tr><td>FILA10G 模块</td><td>5B 格式器；10G光纤输出；VSI输入/输出</td></tr><tr><td>1024MHz综合器</td><td>产生系统时钟</td></tr><tr><td>连接伺服器</td><td>FILA板</td></tr><tr><td>PC 主要配置</td><td>WindowsXP系统；PCI7200；PCI9111HR；JTAG接口</td></tr></table></body></html>

# 4DBBC2软件和观测模式

DBBC2 软件是在 Windows XP 环境下运行。其中 DBBC2 控制软件在c:\DBBC\bin目录下，使用手册在c:\DBBC\doc目录下，配置文本文件在c:\DBBC_CONF\目录下，固件在c:\DBBC_CONF\FilesDBBC目录下。主要软件有•DBBC2 Control DDC V105_1.exe 和 DBBC2 Control DDCV105E_1.exe等。观测模式主要包括DDC和PFB 模式。其中DDC是可调谐的，通道带宽范围在1-16MHz，上下边带，持续的80Hz同步校准。观测模式有 geo,astro,astro2,W-astro,VLBA 和 test。DDC 模式中还包括 DDC-E,它的带宽可以达到32MHz，可以用于astro3观测模式。PFB 模式是固定调谐，通道带宽为32/64MHz，都是上边带或下边带，主要取决于奈奎斯特分布。

# 5 系统建立和调试

# 5.1 硬件连接及自检

（1）在DBBC2后面板上连接10MHz信号，幅度为0dBm左右，连接1pps信号，将DBBC2输出的VSI电缆线连接至Mark5B上，接通220V电源，将DBBC2接入VLBI终端系统的内网中并配置好IP地址。开机顺序是先开DBBC2后面板左下的总电源，然后依次打开工控机电源和PC电源。

（2）在DBBC2的Windows桌面上运行DDC软件，此时系统对硬件进行配置，DBBC2内的4片FPGA将编程并载入本振频率，编程完成后，所有板卡上的LED 灯都显示同样的图案。观察DBBC2前面板上的4列灯依次闪烁，最后以每秒1次的频率同步闪烁，DBBC2系统加电正常，软件工作正常。

（3）根据手册说明编辑配置文件，为ADB选择不同的中频输入，通过AGC进行信号幅度的调整。在WindowsXP桌面运行DBBCclientv4.exe 程序，弹出客户端窗口，在“EnterCommand：”提示符下按照DBBC2手册说明输入相关指令来检测DBBC中频功率幅度、带宽、中频衰减等状态。

（4）Mark5B需要同步DBBC2经VSI电缆线传来的1PPS信号，在Mark5B上运行tstDIM程序[7]，参考Mark5B手册在提示符下执行时间同步指令。

# 5.2时钟校准

由信号发生器产生一个764MHz的信号，幅度为-15dBm左右。该信号经过一个一分四的功分器输出至DBBC2的后面板IFA1，IFB1，IFC1，IFD1上，此时DBBC2内部中频滤波输出所选取的都为2号滤波器（512-1024MHz）。时钟校准的具体步骤参考文[8]。

# 6.3 FS 相关设置

（1）修改FS计算机中/usr2/control/目录下的“dbbad.ctl”文件，将DBBC2的IP写入文件，端口号为4000。（2）clock 钟差采集

观测中需要格式器时钟与GPS 时钟比对值，修改FS 计算机的/usr2/control目录下的ibad.ctl文件，定义C2的端口地址号为3，格式为 ${ \mathrm { C } } 2 { = } { \mathrm { d e v } } 0 3 { , } 0$ 。在FS的operator窗口上运行clock，验证读取钟差是否正常。

(3） 点噪声控制

它主要用来控制接收机噪声源9的开和关，进而测试系统温度。在天线测量[10]时需要进行点噪声控制。在 FS 计算机的/usr2/st/stqkr/目录下的 stqkr.c 文件中设置控制点噪声控制的串口端口，格式为：pcaltty_numb $\ c = \mathrm { i }$ "/dev/ttyr03”;。重新编译后，在FS 的operator 窗口上运行cal=on 和cal=off 指令，验证通讯是否正常。

（4）equip.ctl文件修改

将文件中的机架类型选择为dbbc，版本选择为v105_1，Mark5B时钟速率选择为32，FiLa10G 输入选择为vsi1。

# 5.4 互相关测试

2017年1月12日，南山站与昆明站和上海天马站联合进行了S/X波段的条纹测试实验，成功获得干涉条纹。2月23日和25日，南山站与欧洲EVN各台站进行了L波段的条纹测试实验，也成功获得干涉条纹。3月21日南山站和天马站都参加了EVN的 $\mathrm { g r } 0 3 9$ 观测，南山站同时使用了DBBC2和ABBC设备进行记录。实验结束后，取了相同时间段的数据和上海天马站进行互相关，处理结果如图5，其中图5(a)为DBBC2的测试结果，图5(b)为ABBC的测试结果，可以看出DBBC2结果明显好于ABBC。4月3日南山站又和天马站进行了K波段条纹检测实验并获得较好的测试结果如图6。通过国内和国际联合测试结果表明南山站的DBBC2系统已成功建立。

![](images/29cc640251232c9efe7c54252eb513e2d6f5426b5811940f8bc043de38cd1c4e.jpg)  
图5.DBBC2和ABBC处理结果对照图  
Fig. 5 Comparison diagram of DBBC2 and ABBC processing results

Mk4/DiFXfourfit3.12rev1320 NRAO150.zmcoty, No0006, LU multiband delay (us) 4x1-TANA65UUL -6×10-3 -4×10-3 -2×10-3 。 2x10-3 Fringe quality 9 8 80 SNR 567.6 Int time 9.995   
o Amp 93.021 \$e Phase -0.4 PFD 0.0e+00 1 Delays (us) 4 du SBD 0.001430 0 MBD 0.000009 Fringerate (Hz) 2 20 0.016536 lonTEC0.000 Ref freq (MHz) 0 22131.0000 -0.01 -5×10-3 delay rote (ns/s) 5x10-3 0.01 8 APpe 008 8   
rtitt apntidro 10 Yrday2017:093 □ Start 104450.00 000 A 006-08 -10 0 10 -20 0 20 2016:110:012737 singleband delay (us) Avgd.Xpower Spectrum (MHz) RA&Dec (J2000) 03h59m29.7473s Amp.and Phase vs.time for each freq.,6 segs,1APs /seg (2.00 sec/seg.),time ticks 1 sec +50\*57'50.162"

# 5.5 升级中遇到的问题

（1）DBBC2后面板没有设计VSI连接端口，因此对连接在DBBC2内部的VSI电缆线还需要做一些相应的固定。

（2）收到设备时，机箱内的FILAIN，ADB1/2，CORE 和FILAOUT电路板之接的连接插头和插座都处于断开状态。在把所有连接板接口连好并检查无误后，加电运行，发现软件无法加载，通过设备指示灯无法判断原因。经过分析和判断，软件无法加载的原因是在连接各电路板之间的插头和插座时连接不够紧密造成的，对其进行紧固后，软件加载正常。

（3）在最初的几次测试中发现相关处理后的信号其信噪比较低，猜测是由于输入信号幅度过低造成的。增加了DBBC2输入端信号幅度后相关结果并未改善。通过反复分析和测试，发现应该降低DBBC2输入端的信号幅度，因为此时进入DBBC2内部的信号已经处于接近饱和的状态，这也是DBBC2和ABBC以及CDAS（ChineseData Acquisition System）在输入信号幅度上的区别。

# 6 DBBC2中频接线分配

当DBBC2的所有测试正常后，新建立的系统就可以参加正式的国际和国内联测了，但需要提供本台站接收机各波段信号在DBBC2上的中频连接示意图给制作纲要的相关人员，他们根据台站提供的接线图制定该台站的观测模式以及BBC的具体分配情况等等。图7为南山站DBBC2中频接线图。

![](images/95a7a540f4b4ed29d4bd59e8ed870571480a79e1359881f95c9f9b4a8a7ef6bc.jpg)  
图7．南山站DBBC2 连接图  
Fig.7DBBC2 Connection diagram at Nanshan Station

# 7结论

随着超大规模集成电路和软件无线电技术的发展，世界上开发的宽带数字记录终端—一数字基带转换器（DBBC）已逐步取代了模拟记录终端（ABBC）。与模拟设备相比，DBBC性价比高、带通特性好、稳定性和可靠性指标均优于模拟设备[I。对南山站引进的DBBC2系统进行了全面的测试后，证明其各项技术指标均达到预期要求。通过对该系统与国内外主要台站的联合测试结果进行分析，证明其性能优于原有的模拟基带转换器。在实际操作方面，该系统相比于模拟基带转换器也是更加的便捷。此次南山站DBBC2系统的成功建立，标志着全球VLBI的模拟基带转换器时代已彻底终结。可以预见，在未来的VLBI联测中，南山站的DBBC2系统将发挥更大的作用。

致谢：感谢云南天文台昆明站和上海天文台天马站在南山DBBC2条纹测试中给予观测支持；感谢上海天文台工程师赵融冰和蒋甬斌以及新疆天文台工程师李光辉在软件控制方面给予帮助；感谢新疆天文台工程师陈勇、刘烽和李笑飞在设备硬件测试过程中给予帮助。

# 参考文献：

[1]杨文军，郝龙飞.VLBI终端系统的发展历史和未来展望[J].天文研究与技术—国家天文台台刊，2012,  
9（4）:374-381.Yang Wenjun，Hao Longfei. Development history and future prospects of VLBI terminals [J].Astronomical Research & Technology--Publications of National Astronomical Observatories of China,2012，9（4）:374-381.  
[2] 张碧娟，吴亚军，于威，等．一种VLBI数字基带转换器的阈值计算方法及其FPGA实现[J]．天文研究与技术—国家天文台台刊，2013，10（3）：219-226.Zhang Bijuan，Wu Yajun，Yu Wei，et al.A method of calculating the quantization threshold for a VLBIDBBC and its FPGA implementation[J].Astronomical Research & Technology--Publications of NationalAstronomical Observatories of China，2013，10（3）：219-226.  
[3]朱人杰，张秀忠，韦文仁，等．我国新一代VLBI数字基带转换器研制进展[J]．天文学进展，2011，29(2）:207-217.Zhu Renjie， Zhang Xiuzhong，Wei Wenren，et al. The progress of modern Chinese data acquisitionsystem[J].Progress in Astronomy，2011，29（2）：207-217  
[4] Gino Tuccari. DBBC Developments[R]. 2015 https://ivs.nict.go.jp/mirror/meetings/tow2015/  
[5] Gino Tuccari. DBBC2 hardware User Manual_V2.4.1[R]. 28 February 2011  
[6] Uwe Bach. DBBC Setup and Opreation[R]. 2015https://ivs.nict.go.jp/mirror/meetings/tow2015/ .  
[7] Dan Smythe. Mark5B Operations[R]. 20 April 2007  
[8] DBBC2 calibration[EB/OL].https://deki.mpifr-bonn.mpg.de/GMVA/GMVA_HOWTO/DBBC2_calibration .  
[9] 吴亚军，刘庆会，李娟，等．上海天文台65 米射电望远镜谱线观测及数据校验[J]．天文研究与技术，2017，14（1）：1-7.Wu Yajun，Liu Qinghui，Li Juan，et al. Spectral line observation and data calibration of Tianma 65m radiotelescope [J].Astronomical Research & Technology--Publications of National Astronomical Observatories ofChina，2017，14（1）：1-7.  
[10] 项斌斌，刘志勇，杨文军．基于FS 系统对乌鲁木齐射电望远镜进行天线测量[J].天文研究与技术—国家天文台台刊，2014，11（4）:343-349.Xiang Binbin，Liu Zhiyong，Yang Wenjun. Antenna measurement of Urumqi VLBI radio telescope withfield system [J].Astronomical Research & Technology--Publications of National Astronomical ObservatoriesofChina，2014，11（4）：343-349.  
[11] 洪晓瑜，曹凝.VLBI数字基带转换器（DBBC）[J]．中国科学院院刊，2011,26（5）：593-596.Hong Xiaoyu， Cao Ning. VLBI Digital Base Band Convert[J]. Bulltin of Chinese Academy of Sciences ,2011，26（5）:593-596.

# Installing a VLBI digital backend with DBBC2 at Nanshan Station, Xinjiang Astronomical Observatory

Yang Wenjun1， Yang Jun² ， Jiang ${ \mathbf { W } } { \mathbf { u } } ^ { 3 }$ ，Xia ${ \bf B } 0 ^ { 3 }$ ，Li Jian1，Cui Lang1, Zhang Hua1，Li Peng1，Gao Zhiful, (1.XinjiangstrooyOseratryalstrocalOseatois,secadefieesUioal: yangwj@xaoaccnOsalaceObeatoryhaesUityofchg4saleen3gistroo National Astronomical Observatories,Chinese Academy of Sciences, Shanghai 2Ooo30,China)

Abstract: Base Band Converters (BBC) are the key component of Very Long Baseline Interferometry (VLBI) backend. With the rapid development of computer and digital technology, Anolog BBCs (ABBC) have recently been superseded by Digital BBCs (DBBC) in the field of radio astronomy. Comparing with ABBC, DBBC have much more flexibility and support much wider bandwidth recording in VLBI observations. Considering these advantages and the key role of Nanshan station in international VLBI networks,a VLBI digital backend with DBBC2, developed by Hat-Lab (Italy)，has been instaled at Nanshan station， Xinjiang Astronomical Observatory. The DBBC2 is fully compactible with the European VLBI network (EVN). In the paper,we give a proper introduction to the new equipment including its structure, key modules, input and output interfaces.We also mentioned how to assemble, connect, configure,calibrate and test the equipment. After all these necessary verifications, we performed some testing observations. Fringes to Nanshan DBBC2 were successfully found in these experiments. These successes indicate that the new digital backend is successfully established and works quite stably at Nanshan station. With the new digital backend,we can achieve a recording rate of 2/4 Gbps in the wide-band VLBI observations.This will enable astronomers to image much fainter radio sources with the milliarcsecond resolution.

Key Words: DBBC2 System;VLBI; BBC

# 基金及课题项目：

(中科院西部之光项目No.YBXM-2014-02)2、 (国家自然科学基金青年项目No.11503072)3、 (新疆射电天体物理重点实验室开放课题No.2016D03020)作者简介：杨文军，男，高级实验师，硕士研究生，研究方向：射电天文观测，Email:yangwj@xao.ac.cn手机：13565858007地址：新疆乌鲁木齐北京南路 40 号科学一街150 号新疆天文台