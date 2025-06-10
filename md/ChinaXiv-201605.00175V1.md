# 单粒子翻转敏感区定位的脉冲激光试验研究

余永涛1'²，封国强1，上官士鹏1，陈睿¹，韩建伟1(1.中国科学院 空间科学与应用研究中心，北京100190;2.中国科学院大学，北京100049)

摘要：利用脉冲激光单粒子翻转敏感区定位成像系统，对静态随机存储器件IDT71256开展了单粒子翻转敏感区定位的试验研究。为避开器件正面金属层对激光的阻挡，试验采用背面辐照方式进行测试。试验结果表明，存储单元中存储数据类型对器件单粒子翻转的敏感性有较大影响，由测得的单粒子翻转敏感区分布图经处理得到单粒子翻转截面，结果与重离子试验测得的翻转截面数据一致。

关键词：单粒子效应；敏感区定位；数据类型；翻转截面

中图分类号： $\mathrm { T N } 4 0 6$ 文献标志码：A 文章编号：1000-6931(2015)01-0176-05  
doi:10.7538/yzk.2015.49.01.0176

# Experimental Study on Pulsed Laser Single Event Upset Sensitivity Mapping

YU Yong-tao1²， FENG Guo-qiang1 ， SHANGGUAN Shi-peng1 ， CHEN Rui' ，HAN Jian-wei'(1.Center for Space Science and Applied Research , Chinese Academy of Sciences， Beijing l00l9o， China;2.University of Chinese Academy of Sciences，Beijing lOoo49，China)

Abstract: The pulsed laser facility for single event upset (SEU） sensitivity mapping was utilized to study SEU sensitivity mapping of SRAM IDT71256. To avoid the block of the metal layer in the front side of integrated circuit， the backside testing method was used. The experiment results show that the SEU sensitivity of the SRAM cell depends on the pattern of data stored in the memory cell. The SEU sensitivity mapping could be used to construct the corresponding SEU cross section，which is validated by the heavy ion beam test result.

Key words: single event effect； sensitivity mapping；data pattern；upset cross section

空间粒子辐射环境容易诱发单粒子效应（SEE），它是导致航天器异常的常见空间辐射效应。因此，需对宇航器件在地面进行抗辐射性能测试，研究SEE的机理，进而采取相应的抗辐射加固措施。宇航器件的抗辐射性能测试主要是通过地面的加速器、放射源、脉冲激光等模拟手段进行。要深入研究器件的单粒子效应机理，准确获得器件抗辐照性能的阈值、截面及敏感区域等参数，有必要使用束斑为微米级甚至亚微米级的微束对器件的不同区域进行单粒子效应测试。

脉冲激光易聚焦成微米级的微束，配合亚微米级的精密电动移动台，可对器件的不同区域进行单粒子效应测试。脉冲激光模拟单粒子效应试验装置以其准确定位单粒子翻转（SEU)的优势，能准确获得SEU敏感区位图的分布情况。对于器件SEU敏感区亚微米级的定位研究，国外相关工作开展得早且较为深入[1-6]，国内的相关研究则刚起步[7-8]。静态随机存储器(SRAM)以其优异的性能而广泛用作航天器系统的存储器件，但同时也是对空间辐射环境敏感的器件。本工作利用脉冲激光单粒子翻转敏感区定位成像系统，采用背部辐照方式开展SRAMIDT71256单粒子翻转效应敏感性的研究。由测得的单粒子翻转敏感位图分析得到SEU截面，并与重离子试验的截面结果进行对比分析，讨论准确获得器件SEU截面及阀值的方法。本工作对宇航器件抗辐照性能的测试具有一定的借鉴意义。

# 1 试验方案

# 1.1脉冲激光试验装置与测试流程

脉冲激光单粒子效应敏感区定位成像系统示意图如图1所示，主要由4部分构成：激光装置[9、单粒子效应检测系统、电动移动台和同步控制装置。利用聚焦后的脉冲激光对SRAM存储器件进行逐点辐照，同时利用SRAM存储器单粒子效应检测系统对存储器的翻转地址、位数等进行检测和存储，利用电动移动台实现存储器不同区域的扫描测试，同步控制装置将脉冲激光辐照、单粒子翻转的检测、电动移动台的移动同步控制起来，并将每个辐照位置的激光脉冲注量、单粒子翻转数据、物理坐标对应起来传输至计算机，最终将单粒子翻转敏感位置显示为二维图像。

![](images/d9a8335f87c4e570450a14e8f47751131b33a84ad9f51c40670b1dedaa8a482e.jpg)  
图1脉冲激光SEU敏感区定位成像系统示意图 Fig.1Schematic diagram of pulsed laser facility for SEU sensitivity mapping

测试系统工作流程图如图2所示。初始化芯片和设定试验测试条件，包括在测试器件中写入数据，激光聚焦定位在测试原点，调节脉冲激光能量等。测试开始时，辐照一定数量的激光脉冲。辐照完成后，单粒子效应检测系统刷新器件存储的数据，一旦发生翻转，翻转的逻辑地址及对应的物理坐标会被记录，此坐标即是发生SEU的物理位置。然后电动移动台移动一定的距离到下一测试位置，重复以上过程，直至完成对所选区域的扫描测试，最终可获得器件测试区域内的SEU敏感位置分布图。

![](images/5838f6c9ba8c282dc9fc1ffffc7819d86a4fbdc4dc555d6b2364b4d8179bd8a4.jpg)  
图2SEU敏感区定位系统工作流程图Fig.2Flow diagram of SEU sensitivity mapping

在试验过程中，电动移动台的步距设定为$1 \ \mu \mathrm { m }$ ，每个测试位置辐照1个激光脉冲，芯片中写入 $\mathrm { F F H , 0 0 H }$ 等类型的数据。

# 1. 2 测试器件

测试器件为陶瓷DIP封装的IDT71256，其必须进行开封处理才能进行激光SEU测试。为避开器件正面金属层对激光的阻挡作用，测试采用背部辐照方式。背部辐照是对器件进行背部开封露出Si衬底，激光从背部入射。

芯片的工作电压为 $( 5 . ~ 0 \pm 0 . ~ 5 ) \mathrm { ~ V ~ }$ ，容量为$3 2 \mathrm { K } \times 8$ bits，存储阵列的位图如图3所示。芯片的存储区域分为4个阵列，每个阵列由512行和128列存储单元组成，一个存储单元的大小约为 $5 \ \mu \mathrm { m } \times 6 \ \mu \mathrm { m }$ 。 $\mathrm { A 0 } \sim \mathrm { A 1 4 }$ 为地址线，$\mathrm { I / O 0 } \sim \mathrm { I / O 7 }$ 为位线。A4、A5、A6、A7、A8、A9、A12、A13、A14为行地址，其他地址线为列地址，A2、A3确定存储单元所在的阵列，AO、A1、A10、A11确定存储单元所在的列。每一个阵列分为8组，每组有16列，8组对应的是同一逻辑字地址的8个存储单元，可看出，8个存储单元在物理坐标上并非相邻排列，而是中间间隔有15个存储单元。

![](images/1a98cae7b635a56d4b695dd32b5d5852e48d1163a9aceeed461845c18880a68f.jpg)  
图3SRAMIDT71256的位图Fig.3Bit map of SRAM IDT71256

# 2 试验结果及分析

# 2. 1 激光背部辐照

任意选定一测试区域（大小为 $3 0 \ \mu \mathrm { m } \times$ $3 0 \mathrm { \Omega } _ { \mu \mathrm { m } } )$ ，测试区域内约有30个存储单元，辐照激光能量为 $2 0 0 \mathrm { ~ p J }$ 。SEU敏感区分布如图4所示。图4a对应的存储数据为FFH，图4b为${ \mathrm { 0 0 H } }$ ，黑色方框区域表示激光辐照发生SEU的位置，背景为器件测试区域的显微图像。

![](images/c4a70e552c6636e2466b0810a570e632bcec8b2810433bb6a62488e764a8807e.jpg)  
图4背部辐照SEU敏感区分布  
Fig.4SEU sensitivity mapping for backside laser test

由图4a可看出，存储数据为1（即写入FFH)时，测试区域内SEU敏感区域大致呈现带状分布。由图4b可看出，存储数据为0（即写入OOH)时，测试区域内SEU敏感区域亦大致呈现带状排列。对比图4a、b可看出，存储数据相反，激光辐照发生SEU的区域不同，且两者具有较明显的互补性，即存储数据类型对器件存储单元的SEU敏感性产生影响。翻转结果分别列于表1、2，根据器件的存储位图，测试区域存储单元的逻辑地址均对应同一字地址 8位存储单元中第3位，因此，表1、2中仅给出翻转单元的字地址。

# 表1SRAMIDT71256 翻转结果(FFH)

Table 1 Upsetresultof SRAMIDT71256 forFFH data pattern   

<html><body><table><tr><td>翻转地址</td><td>翻转数</td><td>翻转地址</td><td>翻转数</td></tr><tr><td>770A</td><td>15</td><td>72EB</td><td>14</td></tr><tr><td>7719</td><td>16</td><td>72CB</td><td>11</td></tr><tr><td>76F9</td><td>17</td><td>730A</td><td>19</td></tr><tr><td>76EA</td><td>18</td><td>7319</td><td>17</td></tr><tr><td>76CA</td><td>19</td><td>72F9</td><td>15</td></tr><tr><td>730B</td><td>17</td><td>72EA</td><td>17</td></tr><tr><td>7718</td><td>19</td><td>72CA</td><td>18</td></tr><tr><td>76F8</td><td>20</td><td></td><td></td></tr></table></body></html>

表2SRAMIDT71256翻转结果(00H) Table 2Upset result of SRAM IDT71256 for 0oH data pattern   

<html><body><table><tr><td>翻转地址</td><td>翻转数</td><td>翻转地址</td><td>翻转数</td></tr><tr><td>7709</td><td>14</td><td>731A</td><td>11</td></tr><tr><td>76E9</td><td>15</td><td>72FA</td><td>13</td></tr><tr><td>76C9</td><td>13</td><td>7309</td><td>11</td></tr><tr><td>7708</td><td>14</td><td>72E9</td><td>12</td></tr><tr><td>76E8</td><td>15</td><td>72C9</td><td>10</td></tr><tr><td>76C8</td><td>14</td><td>7308</td><td>10</td></tr><tr><td>731B</td><td>12</td><td>73C8</td><td>13</td></tr><tr><td>72FB</td><td>14</td><td></td><td></td></tr></table></body></html>

由表1、2可看出，器件IDT71256在写入FFH和OOH两种情况下的翻转逻辑地址不同，这与图4敏感区的不同分布相对应，而其排列规律与器件的逻辑地址与物理坐标的映射关系一致。这说明该器件有些存储单元存储数据1时敏感，而另一些存储单元存储数据0时敏感，且这两种单元在物理位置上大致相间排列。相对而言，存储数据为1时SEU翻转数较多，阈值能量较低。对其他区域进行测试，试验结果与此类似。

# 2.2 结果分析

器件IDT71256中不同存储单元的SEU敏感性差别较大，存储数据会对SRAM器件SEU的敏感性产生影响，这与作者对SRAM器件SEU特性的认识不一致。可能的解释是，器件的结构（图5，器件的存储单元是4T2R结构[1°)并不完全对称，若N1、N2两个NMOS管的敏感性不一致，N2NMOS管相对较敏感，当其处于off 状态时，存储数据为1，此时存储单元敏感；反之，当其处于on 状态，而N1为 off 状态时，存储数据为0，则此时存储单元相对不敏感。而对于其相邻的镜像单元，现象正好相反。这样，存储单元全部存储1或。时，即会出现SEU敏感区相间分布的情形。按照以上解释，若相邻的存储单元存储的数据相反，SEU敏感区的分布应为均匀分布。但根据此器件逻辑地址与物理位置的映射关系，同一逻辑地址的8位存储单元并非连续排列，每相邻两位间隔15个其他逻辑地址的存储单元，因而不能通过在相邻存储单元写入相反存储数据进行验证。

![](images/027ea6225adb97f76cf2be3c205a3b3a8921ff108d831717ac0b42e27e6db8e4.jpg)  
图5SRAMIDT71256存储单元结构示意图Fig.5Schematic diagramof SRAMIDT71256 memory cell

# 3激光SEU截面与重离子SEU截面对比

# 3.1 激光测试SEU截面

存储数据对器件单粒子翻转敏感性的影响还可通过SEU截面数据表现出来，可通过处理脉冲激光定位SEU敏感区的结果获得SEU截面。改变脉冲激光辐照能量，可得到不同能量下SEU的敏感分布图，进而可获得测试区域的SEU截面。截面 $\sigma _ { \mathrm { l a s e r } }$ 可表示为：

$$
\sigma _ { \mathrm { l a s e r } } = \frac { S _ { \mathrm { s e u } } } { N _ { \mathrm { c e l l } } } 
$$

其中： $S _ { \mathrm { s e u } }$ 为敏感区分布图中发生SEU的区域面积； $N _ { \mathrm { c e l l } }$ 为测试区域内存储单元数。

图6为激光背部辐照条件下，存储单元在存储不同类型数据时测得的SEU截面，存储数据为FFH时饱和截面约为 $1 . \ 9 \times 1 0 ^ { - 7 } \ \mathrm { c m } ^ { 2 }$ ·$\mathrm { b i t } ^ { - 1 }$ ，存储数据为 ${ \mathrm { 0 0 H } }$ 时饱和截面约为 $1 . 1 \times$ $1 0 ^ { - 7 } ~ \mathrm { c m } ^ { 2 } \cdot \mathrm { b i t } ^ { - 1 }$ 。可看出，随辐照激光能量的增大，单个bit的翻转截面增大。在相同的激光辐照能量下，存储数据为FFH时，SEU的截面较大，约为存储数据为 ${ \mathrm { 0 0 H } }$ 时的2倍。不同的存储数据会对器件的SEU截面产生影响，这对器件的抗辐照性能测试提出了新要求。在实际应用时，器件存储的数据一般无规律，可认为是随机的。而在辐照试验中，器件通常的存储数据为FFH、OOH或 $5 5 \mathrm { H }$ 、AAH，这与器件的真实使用情形不一致。因此，在单一存储数据类型条件下测得的辐照试验结果可能不能代表器件真正的抗辐照性能。估算器件在空间辐射环境中的翻转率时，通常考虑最恶劣情形，SEU阈值取不同存储数据类型条件下测试阈值结果的最低值；SEU饱和截面与存储数据类型条件下测试结果的最大值应不同。就SRAMIDT71256而言，存储数据为FFH时的SEU敏感区分布图与存储数据为 ${ \mathrm { 0 0 H } }$ 时的SEU敏感区分布图是互补的。所以，在最恶劣的情况下，SEU饱和截面应是存储数据为FFH时的饱和截面与存储数据为 ${ \mathrm { 0 0 H } }$ 时的饱和截面之和，并将SEU敏感区分布图去除两者的重合部分，计算结果如图6中修正曲线所示。

![](images/cc9027bd51a3a42b5b2bbb74ccc499d95c986a3d65de573b7b2ef24eaac6dac5.jpg)  
图6SRAMIDT71256激光背部辐照SEU截面 Fig.6Laser backside test SEU cross section of SRAMIDT71256

# 3.2重离子测试SEU截面

本文对激光试验得到的SEU截面进行重离子测试验证，图7为SRAMIDT71256的重离子测试SEU截面。本试验分别测试存储数据为FFH和AAH时SRAMIDT71256的翻转截面。可看出，随辐照离子LET值的增大，单个bit的翻转截面逐渐增大。存储数据为FFH的SEU截面明显大于存储数据为AAH的，存储数据为FFH时饱和截面约为 $1 . 8 \times$ $1 0 ^ { - 7 } ~ \mathrm { c m } ^ { 2 } ~ \cdot ~ \mathrm { b i t } ^ { - 1 }$ ，存储数据为AAH时饱和截面约为 $1 . \ 5 \times 1 0 ^ { - 7 } \ \mathrm { c m ^ { 2 } \bullet b i t ^ { - 1 } }$ 。

![](images/a57945c3f7b3851ee30973c1ebbedf10a4734aaf5b9c8cc6c38ed43494c6eb42.jpg)  
图7SRAMIDT71256重离子测试SEU截面 Fig.7Heavy ion test SEU cross section of SRAMIDT71256

重离子测试SEU截面与激光试验的结果相比，两者所表现出的趋势一致。存储数据为FFH时，重离子测试SEU截面略小于激光测试的，存储数据为AAH时，重离子测试SEU截面小于存储数据为FFH的SEU截面，而大于存储数据为 ${ \mathrm { 0 0 H } }$ 的激光测试SEU截面。因为激光的光斑尺寸较大[1]，相同条件下激光测试的SEU截面较重离子测试的截面稍大。重离子测试结果表明：对于SRAMIDT71256，存储数据类型会对器件SEU截面的测量产生影响。

# 4结论

本工作利用脉冲激光单粒子翻转效应敏感区定位成像系统，采用背部辐照方式对SRAMIDT71256开展了单粒子翻转效应敏感区定位的试验研究。结果表明，对于此款器件，存储单元中存储的数据会对器件存储单元SEU敏感性产生较大影响。处理SEU敏感位图可获得SEU截面，结果与重离子测试结果符合较好。

不同类型的存储数据可能对器件SEU截面及阀值的测量产生影响，这对器件的抗辐照性能测试提出了新要求。存储器件抗辐照试验中，采用单一类型存储数据的测试条件与器件的真实使用情形不一致，测试结果可能不能表示器件真正的抗辐照性能。对于存储器件SEU截面及阀值测试，应该综合分析不同类型存储数据条件下的测试数据，得到较为可靠的SEU辐照测试结果。

# 参考文献：

[1] BARAKJ，ADLER E，FISCHER BE，et al.Microbeam mapping of single event latchups andsingle event upsets in CMOS SRAMS[J].IEEETrans Nucl Sci，1998，45(3)：1 595-1 602.  
[2] DARRACQF，BEAUCHENET，POUGETV,et al. Single-event sensitivity of a single SRAMcell[J].IEEE Trans Nucl Sci，2002，49（3）：1 486-1 490.  
[3] MCMORROWD,LOTSHAW W T，MELINGER JS，et al. Three-dimensional mapping of single-eventeffects using two photon absorption[J]. IEEE TransNucl Sci，2003，50(6)：2 199-2 207.  
[4] MILLERF，BUARD N，HUBERTG，et al. Lasermapping of SRAM sensitive cells：A way to obtaininput parameters for DASIE calculation code[J].IEEE Trans Nucl Sci，2006，53(4)：1 863-1 870.  
[5] CHUGGAM，BURNELLMJ，MOURTRIEMJ，et al. Laser SEE sensitivity mapping of SRAMcells[J]．IEEE Trans Nucl Sci，2007，54（6）：2 106-2 112.  
[6] CHUGGAM，WARDJ，MCINTOSHJ，etal.Improved fine-scale laser mapping of componentSEE sensitivity[C]//12th Radiation and ItsEffects on Components and Systems.Sevilla:IEEE，2011：19-23.  
[7] 罗尹虹，郭红霞,陈伟，等．SRAM激光微束单粒子效应实验研究[J]．微电子学，2010，40(3)：464-468.LUO Yinhong，GUO Hongxia，CHEN Wei，etal.Laser microbeam experiment on single eventeffect in SRAM[J].Microelectronics，2010，40(3)：464-468(in Chinese).

[8]史淑廷，郭刚，王鼎，等．单粒子翻转二维成像技术[J].信息与电子工程，2012，10(5)：608-612.SHI Shuting，GUO Gang，WANG Ding，et al.Technique of single event upset mappinglJl.In-formation and Electronic Engineering，2ol2，10(5）：608-612(in Chinese).

[9]封国强，马英起，张振龙，等．光电耦合器的单粒 子瞬态脉冲效应研究［J]．原子能科学技术， 2008，42(增刊)：36-42. FENG Guoqiang，MA Yingqi，ZHANG Zhenlong, et al.Study of single event transients effects for op tocoupler[J].Atomic Energy Science and Technolo gy，2008，42(Suppl.）：36-42(in Chinese).   
[10]KOGAR，CRAWFORDKB，GRANTPB，et al. Single ion induced multiple-bit upset in IDT 256K SRAMs[C]//Radiation and Its Effects on Components and Systems. Saint-Malo：IEEE, 1993：13-16.   
[11]MILLERF，BUARDN，CARRIERET，etal. Effects of beam spot size on the correlation between laser and heavy ion SEU testing[J].IEEE Trans Nucl Sci，2004，51(6):3 708-3 715.