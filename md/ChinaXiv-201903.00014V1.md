# 永磁体削角对表贴式永磁同步电机齿槽转矩的影响研究

![](images/b68f0fb5b9b4b1e73254dd852c65f329fb7c0e8d766e2fad56fe960e38d3120b.jpg)

张宇男1994年生，本科，研究方向为电气工程及其自动化。

张　宇　王沐凡　侯崇琦　王传庆　施建雄　张　栋　鲍晓华（合肥工业大学电气与自动化工程学院合肥230009）

摘要：针对永磁电机的齿槽转矩影响其控制精度和性能的问题，本文提出削角可以有效抑制齿槽转矩的方案。以一台30槽10极永磁电机为例，利用数值仿真原理，建立电机电磁场有限元模型，对削角削弱齿槽转矩的方法进行仿真分析。研究表明，齿槽转矩的大小与削角高度和削角宽度有关，选取合适的削角高度和宽度可以有效地削弱齿槽转矩。仿真结果证明了本文基于削角的齿槽转矩削弱方法的有效性和正确性。

关键词：表贴式永磁同步电机有限元法 齿槽转矩 削角中图分类号：TM351

# Influence of Permanent Magnets Chamfering on Cogging Torque of Surface-Mounted Permanent Magnet Synchronous Motor

![](images/90c8c04f8d7f07df953f212d2a14050780d85714d798262ec15e7d61e5ece245.jpg)

Zhang Yu Wang Mufan Hou Chongqi Wang Chuanqing Shi Jianxiong Zhang DongBao Xiaohua (School of Electrical Engineering and Automation, Hefei University of TechnologyHefei230009 China)

王沐凡女 1995年生，本科，研究方向为电气工程及其自动化。

Abstract: Aiming at the problem that the cogging torque of permanent magnet motor influences its control precision and performance, this paper proposed a method that the permanent magnets chamfering can suppress the cogging torque effectively. Take a 30- slot/10-pole permanent magnet motor as an example,the finite element model of the electromagnetic field of the motor is established by using the numerical simulation principle,The method of reducing the cogging torque by chamfering is simulated and analyzed.The results show that the size of the cogging torque is related to the height and the width of the permanent magnet chamfering. Selecting the appropriate cuting angle height and width can effectively reducing the cogging torque. The simulation results show the effectiveness and correctness of the method of cogging torque reduction.

Keywords: Surface-mounted permanent magnet synchronous motor, finite element method, cogging torque,chamfering

# 1 引言

永磁电机具有功率密度高，稳定性好，能在宽调速范围内高效运行等一系列优点。随着高性能永磁材料的出现以及控制技术的发展，永磁电机在各个行业得到广泛的发展与应用[1。永磁电机由于开槽电枢铁心与永磁体之间的相互作用引起磁场能量变化，从而产生齿槽转矩[2]，进而产生电机振动和噪声，影响永磁电机的控制精度和性能，限制其在精度要求较高的系统中的应用。因此如何减小永磁电机由齿槽转矩引起的转矩脉动一直是国内外学者研究的重点。

关于永磁电机转矩脉动的降低方法，国内外有很多文献对其进行了分析，主要有槽口偏移[3和转子分段斜极[4]、改变极槽配合[5]、改善控制策略[6]和永磁体分块[等。而对于齿槽转矩的计算分析方法，一般有解析法和有限元法两种[8]。解析法能够体现出结构参数变化时齿槽转矩变化的大体趋势，但难以考虑到漏磁和饱和等因素，无法进行准确计算。有限元法能够考虑漏磁、饱和以及复杂结构的影响，可以较为准确地计算齿槽转矩。

本文主要研究通过永磁体削角对表贴式永磁同步电机由于齿槽引起的转矩脉动，即齿槽转矩的削弱。削角方法使永磁体的厚度发生变化，气隙变的不均匀，气隙磁密以及气隙磁导改变使电机的齿槽转矩降低。并运用有限元法进行仿真验证，对永磁体不同削角高度和削角宽度时齿槽转矩的变化程度进行对比分析，得出最佳削角方案。从结果可以看出本文研究的方法能够减小电机的转矩脉动。

# 2 齿槽转矩解析分析

齿槽转矩是由于永磁体与有槽电枢的相对位置变化引起的能量变化导致的，定义为电机电枢不通电时，磁场能量 $W$ 相对于位置角 $\alpha$ 的导数，即

$$
T = T _ { \mathrm { c o g } } = - { \frac { \partial W } { \partial \alpha } }
$$

式中，W为磁共能； $\alpha$ 为永磁体中心线与定子齿的中心线的夹角。

假设铁心的磁导率为无穷大，同一电机中的永磁形状相同，永磁材料的磁导率与空气相同。基于以上假设，电机内的磁场能量可近似为永磁体与气隙内磁场能量之和

$$
W \approx W _ { \mathrm { a i r g a p } } + W _ { \mathrm { p M } } = { \frac { 1 } { 2 \mu _ { \mathrm { 0 } } } } { \int _ { \nu } B ^ { 2 } \mathrm { d } V }
$$

式中， $\mu _ { 0 }$ 为空气磁导率。

该能量 $W _ { \mathrm { a i r g a p } }$ 取决于电机结构和电枢与永磁体的相对位置。气隙的磁密在任意相对位置 $\alpha$ 可表示为

$$
B ( \theta , \alpha ) = B _ { \mathfrak { d } } ( \theta ) { \frac { h ( \theta , \alpha ) } { h ( \theta , \alpha ) + g ( \theta , \alpha ) } }
$$

式中， $B _ { \ S } ( \theta )$ 为沿圆周的分布的磁体剩磁密度； $g ( \theta , \alpha )$ 为磁极中性线与齿中心线夹角为 $\alpha$ 时沿圆周分布的有效气隙长度； $h ( \theta , \alpha )$ 为永磁体充磁方向长度。

假设永磁体内的能量不变化，只考虑气隙磁场变化，气隙内的能量表示为

$$
\boldsymbol { W } _ { \mathrm { a i r g a p } } = \frac { 1 } { 2 \mu _ { 0 } } \int _ { \nu } \boldsymbol { B } _ { \boldsymbol { \delta } } ^ { 2 } ( \boldsymbol { \theta } ) \left( \frac { h ( \boldsymbol { \theta } , \boldsymbol { \alpha } ) } { h ( \boldsymbol { \theta } , \boldsymbol { \alpha } ) + g ( \boldsymbol { \theta } , \boldsymbol { \alpha } ) } \right) ^ { 2 } \mathrm { d } V
$$

因此，对 $B _ { \ S } ^ { 2 } ( \theta )$ 和 $\left( { \frac { h ( \theta , \alpha ) } { h ( \theta , \alpha ) + g ( \theta , \alpha ) } } \right) ^ { 2 }$ 进行傅里叶分解，展开后的表达式为

$$
B _ { \delta } ^ { 2 } ( \theta ) = B _ { \delta 0 } + \sum _ { n = 1 } ^ { \infty } B _ { \delta n } \cos { ( n n _ { \mu } \theta ) }
$$

$$
\left( \frac { h ( \theta , \alpha ) } { h ( \theta , \alpha ) + g ( \theta , \alpha ) } \right) ^ { 2 } = \lambda _ { 0 } + \sum _ { n = 1 } ^ { \infty } \lambda _ { _ n } \cos \left[ n n _ { \mathrm { s } } ( \theta + \alpha ) \right]
$$

式中， $n _ { \mathrm { p } }$ 为电机极数； $| n _ { \mathrm { s } } ^ { } \rrangle$ 为定子槽数。

将式（5）、式（6）代入式（4）、式（1）可得齿槽转矩表达式为

$$
T _ { \mathrm { c o g } } ( \alpha ) = \frac { \pi n _ { \mathrm { s } } L _ { \mathrm { F e } } } { 4 \mu _ { 0 } } \Big ( R _ { 2 } ^ { 2 } - R _ { 1 } ^ { 2 } \Big ) \sum _ { n = 1 } ^ { \infty } n \lambda _ { n } B _ { \delta n } \frac { n n _ { \mathrm { s } } } { n _ { \mathrm { p } } } \sin { ( n n _ { \mathrm { s } } \alpha ) }
$$

式中， $L _ { \mathrm { F e } }$ 为电枢铁心长度； $R _ { 1 }$ 为转子外径； $R _ { 2 }$ 为定子内径。

从以上分析可以看出电机的齿槽转矩与电机的磁场分布、气隙磁导、电机转子外径及定子内径等参数有关。可以考虑通过改变磁极形状与气隙分布的方法来减小齿槽转矩，抑制转矩脉动。

# 3永磁体削角对齿槽转矩影响的有限元分析

# 3.1永磁同步电机仿真模型

以一台 $1 . 5 \mathrm { k W }$ ，30槽10极表贴式永磁同步电机样机为例，利用有限元软件研究永磁体底部削角对齿槽转矩的减小程度进行仿真分析，样机主要参数见表1。

表1电机主要参数  
Tab.1The main parameters of the motor   

<html><body><table><tr><td>参数</td><td>数值</td></tr><tr><td>额定功率/kW</td><td>1.5</td></tr><tr><td>额定电压/V</td><td>224</td></tr><tr><td>额定频率/Hz</td><td>150</td></tr><tr><td>极数</td><td>10</td></tr><tr><td>槽数</td><td>30</td></tr><tr><td>定子外径/mm</td><td>126</td></tr><tr><td>转子内径/mm</td><td>78</td></tr><tr><td>铁心长度/mm</td><td>50</td></tr></table></body></html>

本文所研究的永磁体底部削角示意图如图1所示，该结构为在永磁体底部两侧削去高度为 $h$ ，宽度为 $b / 2$ 的角，这两个角关于永磁体中心对称，原永磁体宽度为 $b _ { 0 }$ ，厚度为 $h _ { 0 }$ 。并且削去的角利用硅钢片补上，削去后气隙变为不均匀气隙，气隙磁导发生了改变，使电机磁场分布发生变化，从式(1)可以看出，电机的齿槽转矩也发生变化。从以上推导结果式（7）可以看出添加硅钢片后转子外径 $R _ { 1 }$ 的分布发生了变化，并且磁场分布 $B _ { \mathrm { r n } }$ 也与原先不同，电机的齿槽转矩相应变化。本文将对不同削角高度与削角宽度对齿槽转矩产生的具体影响进行仿真分析，以得到最佳方案。

波形分布，可以看出，气隙磁密波形分布的变化并不大，气隙磁密幅值会有略微差别， $h = 0 . 7 5 h _ { 0 }$ 时，波形有所改善。通过不同削角高度时电机的气隙磁密的波形，对气隙磁密波形进行傅里叶分解后可得如图2b所示的气隙磁密各次谐波幅值。可以看出，削角后气隙磁密的基波幅值会有明显减小，削角高度越大时减小幅值越大，这对提高电机的转矩密度是不利的，会降低电机输出的平均转矩。当削角高度从 $0 . 5 h _ { 0 }$ 增加到 $0 . 7 5 h _ { 0 }$ 时，气隙磁密的3次、5次谐波幅值与未削角时相比均呈下降趋势，这能使电机的齿槽转矩得以减小。因此对永磁体底部削角后一方面能减小电机的齿槽转矩，另一方面又会使电机输出的平均转矩减小，这是一组相互矛盾的结果。

![](images/168a0e82be4eaa65ab93ffbff143d0fa9a611e661fbe89986daf1bf35e1677b2.jpg)  
图2气隙磁密  
Fig.2The air-gap flux density

![](images/4c6c60bc1f8729f04dbfb1a783991d49416108056b78c6fc02ab8b17f019964f.jpg)  
图1电机剖面图  
Fig.1The profile of the motor

# 3.2不同削角高度对齿槽转矩的影响

用有限元软件对于不同削角高度 $h$ 进行有限元仿真计算。图2为不同削角高度时的气隙磁密，在进行对比仿真时保持削角宽度 $b = b _ { 0 }$ 不变，只改变削角高度 $h$ ， $h = 0$ 为未削角时对应的情况。图2a为不同削角高度情况下电机的一个周期内的气隙磁密

图3为30槽10极表贴式永磁同步电机齿槽转矩随削角高度的变化曲线，其中 $h$ 为削角高度。由图可以看出，永磁体未削角时齿槽转矩为 $2 . 6 \mathrm { N } \cdot \mathrm { m }$ ，削角高度为 $0 . 5 h _ { 0 }$ 时齿槽转矩为 $2 . 1 \mathrm { N } \cdot \mathrm { m }$ ，较未削角时减小 $1 9 \%$ 。削角高度为 $0 . 7 5 h _ { 0 }$ 时齿槽转矩为$1 . 5 \mathrm { N } \cdot \mathrm { m }$ ，较未削角时减小 $42 \%$ 。由此可见，削角高度不同时对齿槽转矩的影响较大，这也与以上对气隙磁密傅里叶分解结果相吻合。

为了使电机输出的平均转矩不至于过小，同时电机的转矩脉动又得到减小，需要引入转矩脉动系数 $T _ { \mathrm { t r } }$ 评价各个方案的好坏，转矩脉动系数的表达式如式（8）所示，分子为电机输出的最大转矩与最小转矩之差，分母为最大转矩与最小转矩之和。由此,$T _ { \mathrm { t r } }$ 的值越小，表明输出的平均转矩越大，转矩脉动越小。

![](images/f07a544be55d54ad1f5789eda3a982b73597f831c188037a5e01d3cf057d8ef5.jpg)  
图3不同削角高度时的齿槽转矩

$$
T _ { \mathrm { t r } } = \frac { T _ { \mathrm { m a x } } - T _ { \mathrm { m i n } } } { T _ { \mathrm { m a x } } + T _ { \mathrm { m i n } } }
$$

表2为永磁体不同削角高度时电机输出的转矩情况，随着削角高度的增大电机的输出平均转矩也会减小，当 $h = 0 . 7 5 h _ { 0 }$ 时电机输出的平均转矩减少至 $7 . 4 7 \mathrm { N \cdot m }$ ，与未削角时的平均值 $8 . 8 7 \mathrm { N \cdot m }$ 相差较大，此外转矩脉动系数也随着削角程度增大得到减小。

# 表2不同削角高度时的转矩

Tab.2Torque at different chamfer height   
（单位： $\mathbf { N } \cdot \mathbf { m } $ ）  

<html><body><table><tr><td></td><td>h=0</td><td>h=0.5ho</td><td>h=0.75ho</td></tr><tr><td>Tmax</td><td>11.76</td><td>9.98</td><td>9.01</td></tr><tr><td>Tmin</td><td>5.98</td><td>6.06</td><td>5.94</td></tr><tr><td>Tavg</td><td>8.87</td><td>8.02</td><td>7.47</td></tr><tr><td>T</td><td>0.326</td><td>0.244</td><td>0.205</td></tr></table></body></html>

根据以上数据可知，当削角高度为 $h = 0 . 7 5 h _ { 0 }$ 时$T _ { \mathrm { t r } }$ 值最小，但考虑到此时电机输出的平均转矩减小过大，不利于电机的实际应用，因此取 $h = 0 . 5 h _ { 0 }$ 为最优选择。

# 3.3不同削角宽度对齿槽转矩的影响

此节主要研究削角宽度对于电机齿槽转矩的抑制作用。利用有限元软件对不同削角宽度 $b$ 时电机的转矩变化情况进行有限元仿真计算，在进行仿真时保持永磁体的削角高度 $h = 0$ ： $5 h _ { 0 }$ 不变。经过仿真后可得如图4所示的电机齿槽转矩，可以看出齿槽转矩随着削角宽度的增加呈现先减小后增大的趋势，当 $b = 0 . 7 5 b _ { 0 }$ 时电机的齿槽转矩最小。

![](images/0862851b517ea91e3d1d52f6778264611c42bf1d52ef9ed924462505a2d4985c.jpg)  
Fig.3Cogging torque at different chamfer height   
图4不同削角宽度时的齿槽转矩

图5为不同削角宽度时电机的平均转矩，由图中数据可知，平均转矩随着削角宽度的增加而逐渐减小，但减小的幅值并不大。综合图4数据可以看出，当 $b = 0 . 7 5 b _ { 0 }$ 时，能够在最大程度上削弱了齿槽转矩，而不会使电机输出的平均转矩减小过大。

![](images/6f143e5ffa620e80caae37f6a2ea9b438920491fd61a5195740d4176b65b45f1.jpg)  
Fig.4Cogging torque at different chamfer width   
图5不同削角宽度时电机的平均转矩Fig.5Average torque at different chamfer width

通过上文分析可以得出当永磁体的削角高度为$h = 0 . 7 5 h _ { 0 }$ ，削角宽度为 $b = 0 . 7 5 b _ { 0 }$ 时电机的转矩脉动得到减小，同时电机输出的平均转矩又不至于减小过大，为最优选择。

# 4结论

本文研究了永磁体底部削角对表贴式永磁同步电机齿槽转矩的影响。通过削角方法使永磁体的厚度改变，削角后加上的硅钢片使气隙变得不均匀，这使得电机的气隙磁导以及气隙磁密分布发生改变。本文首先运用能量法和傅里叶分解法对齿槽转矩进行解析分析，推导出齿槽转矩的表达式，确定可以通过改变磁极形状的方法来减小齿槽转矩，抑制转矩脉动。然后以一台表贴式30槽10极永磁同步电机样机为例，利用有限元软件，研究了削角对齿槽转矩影响的有限元仿真分析。以不同削角高度和削角宽度为变量，对不同削角高度 $h$ 和削角宽度 $b$ 时电机的齿槽转矩的变化情况进行仿真分析，仿真结果表明，不同削角高度及宽度会对齿槽转矩产生较大影响。综合考虑输出转矩的平均值与脉动的减小情况，得出在削角高度为 $h = 0 . 5 h _ { 0 }$ 时齿槽转矩明显减小，输出转矩变化不大，为最优选择；削角宽度为 $0 . 5 b _ { 0 }$ 时齿槽转矩最小，为最优削角方案。从以上研究可以看出，合理地选择削角方案能够减小电机的齿槽转矩进而使输出转矩的脉动得以减小，并且电机的输出转矩不至于减小过多。

致谢：感谢吴长江学长在论文规范和专业知识方面给予我很多建议，最后感谢安徽明腾永磁机电设备有限公司为我们提供的设备支持。

致谢：感谢吴长江学长在论文规范和专业知识方面给予很多建议；感谢安徽明腾永磁机电设备有限公司提供的设备支持。

# 参考文献

[1] 黄允凯，周涛，董剑宁，等．轴向永磁电机及 其研究发展综述[J]．中国电机工程学报，2015， 35(1):192-205. Huang Yunkai,Zhou Tao,Dong Jianlin,et al.An overview on developments and researches of axial flux permanent magnet machines[J]. Proceedings of the Chinese Society of Electrical Engineering,2015, 35(1):192-205.   
[2] 邓秋玲，黄守道，刘婷，等．永磁电机齿槽转矩 的研究分析[J]．湖南大学学报（自科版)，2011, 38(3):56-59. Deng Qiuling,Huang Shoudao,Liu Ting,et al. Study of cogging torque in permanent-magnet machines[J]. Journal of Hunan University (Natural Science),2011, 38(3):56-59.   
[3] 井立兵，柳霖，高起兴，等．削弱模块化永磁电 机齿槽转矩的新方法[J]．电气工程学报，2017， 12(2): 15-19. Jing Libing,Liu Lin,Gao Qixing,et al.A novel method of weakening the cogging torque of modular permanent magnet motor[J]. Journal of Electrical Engineering,2017,12(2): 15-19.   
[4] 黄燕涛，郭新华，项雷军．内置式永磁电机齿槽 转矩的优化设计[J].华侨大学学报（自然科学版）, 2016，37(5): 536-540. Huang Yantao,Guo Xinhua, Xiang Leijun. Optimal design of cogging torque of interior permanent magnet motor[J]. Journal of Huaqiao University (Natural Science), 2016, 37(5): 536-540.   
[5] 曹翼，李光耀．不同极槽配合永磁伺服电机的电 磁性能分析和比较[J]．电机与控制应用，2015, 42(11): 21-25. Cao Yi, Li Guangyao.Different pole/slot with permanent magnet sevo motor electromagnetic performance analysis and comparison[J]. Electric Machines & Control Application,2015,42(11): 21-25.   
[6] 廖勇，甄帅，刘刃，等．用谐波注入抑制永磁同 步电机转矩脉动[J]．中国电机工程学报，2011, 31(21): 119-127. Liao Yong, Zhen Shuai, Liu Ren, et al. Torque ripple suppression of permanent magnet synchronous motor by the harmonic injection[J]. Proceeding of the CSEE,2011, 31(21): 119-127.   
[7] 沈风顺，任雷，刘晋平．表面式永磁电机齿槽 转矩物理学解读及削弱方法[J]．微电机，2012, 45(6): 73-77. Shen Fengshun,Ren Lei, Liu Jinping. Physics explanation on cogging torque of surface permanent magnet motor and introduction of reducing methods[J]. Micromotors,2012, 45(6): 73-77.   
[8] 李延升，窦满峰，樊鑫．表贴式永磁电动机气隙 磁场及齿槽转矩解析计算[J]．微特电机，2012, 40(12): 10-15. Li Yansheng, Dou Manfeng, Fan Xin. Analytical calculation of air gap magnetic field and cogging torque in surface-mounted PM motor[J]. Small & Special Electrical Machines, 2012,40(12): 10-15.