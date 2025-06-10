# 叶栅安装角对无阻流板式叶栅反推装置性能影响的研究

周　莉　王占学　任亚强　刘增文(西北工业大学 动力与能源学院，西安 710072)

摘要对某一无阻流门叶栅式反推装置的流场进行了数值研究，详细分析了不同叶栅安装角对反推性能的影响。结果表明叶栅安装角对流出反推窗口气流的质量流量、气流速度以及气流的流动方向产生影响，进而对反推效果产生影响。对于不同风扇进口压比，存在不同的最佳的叶栅安装角度，能使得反推效果最好。由于风扇压比不同，气流所具有的能量不同，风扇进口压比越低，其具有能量越小，进入反推窗口偏转角越大，最佳安装角越大。

关键词无阻流门叶栅式反推装置；二次流喷射；叶栅进口安装角；反推效率中图分类号：V235.13 文献标识码：A

# Influence of Cascade Inlet Installation Angle on Performance of Blockerless Thrust

# Reverser

# ZHOU Li WANG Zhanxue REN Yaqiang LIU Zengwen

（School of Power and Energy, Northwestern Polytechnical University,Xi'an 710o72, China

Abstract:Tefwfloftcksthustveisivtgdumecalltofadetisallogest reverseefectivenessisdiscussd.Resultshowthatthemassflowflowvelocityandflowdirectionthroughthecascadeslotareotably influencedbyadeisalatiletheeeisngdorspongloritipe ratioanoptialasadeistalltionangleexists,ichakesththrustrevseeenybstTefoasdienteeyduetote differentvalueofthefninletpressureratioTelowerthefaninletpressureis,tesmalereertefowasthefowdeflctiofte bypassflowfdodoeosoendospongfgleiadestisg a larger optimal cascade installation angle.

# 0前言

KeyWords: blockerlessthrust reverser;secondary flow injection; cascade installtion angle; thrust reverse efficiency 生影响。

目前，大型客机和运输机常用的减速装置为发动机反推力装置，传统的发动机反推力装置包括哈壳形折流门式、抓斗式折流板式、叶栅式反推装置[1-4]。这几类机械式结构存在的最大缺点是短舱重量明显增加、机械运动部件增多、对密封性要求较高。而基于核心二次流喷射的流体反推技术以“气动阻流板”替代传统的机械式阻流板，大幅减轻了反推装置的重量，明显降低了作动机构的复杂性。国内外研究学者对基于二次流喷射的无阻流板式反推力装置进行了大量研究，结果显示二次流喷射位置、喷射角度对反推效率有很大影响[5-7]。此外，研究者们对带阻流门叶栅反推力装置的气流几何进气角进行的研究中，发现存在一个比较好的几何进气角，能取得较高的空气流量和轴向反推力[8-11]。可见反推窗口的叶栅安装角影响对反推装置的反推效率会产

本文利用数值模拟手段，对无阻流板式反推装置进行研究，着重研究不同叶栅安装角对反推效率的影响，以期深入认识无阻流板式反推力装置内部的流动机理。

# 1几何模型

本文所研究的反推装置构型见图 $1 ^ { [ 5 - 7 ] }$ 。该模型是基于CFM56-2（涵道比5:1）发动机的1/10缩比模型。图中曲线A-B代表风扇涵道下壁面，二次流入口在A-B上如图。曲线C-D-E-F代表风扇涵道上壁面，曲线G-H-F代表机舱外表面，曲线D-E-H-G-D表示在外涵上壁面和机舱表面反推窗口的边界，而F点代表整流罩的后缘位置。气流边界被限制在A-B、C-D-G、H-E-F。反推窗口的导流叶片等间距排列，叶栅安装角如图2所示。在计算中，以叶栅下端圆弧的中心为基准点进行旋转以实现安装角的变化，间隔为 $5 ^ { \circ }$ 。

![](images/a8b47f8a44267de7fe6da4fe6cfa05d6de4e1218b3f9b4b550ced58e226ca929.jpg)  
图1计算采用的几何构型（单位为mm）

![](images/975ca8e37767261ed24a1dbcb710cbfbc5f38e15ae3033ab02cf356c58c1cd8a.jpg)  
Fig.1computational geometry model （unit in mm）

# 2计算及性能评估方法

计算采用了商用软件Fluent。控制方程为直角坐标系下的雷诺平均方程。控制方程的离散采用控制容积法，空间上采用二阶迎风格式，定常的耦合隐式算法。湍流模型选取了标准k-ε模型。

计算所采用的几何模型和边界条件如图4所示，风扇主流和二次喷射流入口采用压力进口边界条件，给定总压、总温及速度方向。其他外边界为压力远场边界条件。计算网格在壁面附近加密。网格及边界条件如图3：

![](images/0dc253f63b8e8e73b9cd6e3bd4345e3dade3426c32658bc462f718552a61b857.jpg)  
Fig.2installation angle of the cascade   
Fig.3Grid and boundary conditions

本文采用两种方法来衡量反推装置的反推效果：

1、反推流量比CFR（流经反推窗口的流量与总流量之比)，即：

$$
C F R = W _ { c a s } \ / ( W _ { f a n } + W _ { j e t } )
$$

其中 $W _ { \mathrm { c a s } }$ 为反推出口流量； $W _ { \mathrm { f a n } }$ 为风扇进口流量； $W _ { \mathrm { j e t } }$ 为二次流喷射流量。

2、反推力比 $\eta _ { r e \nu }$ ，即

$$
\eta _ { _ { r e \nu } } = F _ { _ { r e \nu } } / F _ { _ { i , f a n } } ^ { \mathrm { ~ ~ } } ,
$$

# C hinaXiv合作期刊

$$
F _ { _ { r e \nu } } = \int \rho V _ { _ { y } } \cdot V _ { _ x } d A
$$

$$
F _ { i , f a n } ^ { \mathrm { } } = W _ { p , f a n } ^ { \mathrm { } } \sqrt { R _ { j } ^ { \mathrm { } } T _ { t , f a n } ^ { \mathrm { } } \frac { 2 \gamma } { \gamma - 1 } [ 1 - ( \frac { 1 } { R N P R } ) ^ { \frac { \gamma - 1 } { \gamma } } ] } \ ;
$$

其中 $\mathrm { ~ \bf ~ \underline { ~ } { ~ \boldsymbol ~ \rho ~ } ~ }$ 表示密度； $\boldsymbol { V _ { y } } \setminus \boldsymbol { V _ { x } }$ 表示反推窗口出口处流体的速度分量； $W _ { p , f a n }$ 风扇进口流量； $T _ { t , f a n }$ 表示进口总温；FNPR风扇进口压比。

反推力 $F _ { r e \nu }$ 为反推窗口处动量沿X方向的积分如图3， $F _ { i , f a n }$ 为外涵理想推力。

反推出口

![](images/a6c81090032fc877730b3486c988981efc2bd7d7c9d61da379ab433c96511dd8.jpg)  
图2叶栅安装角示意图  
图4反推窗口示意图  
Fig.4sketch of the thrust reverse window

# 3计算结果与分析

# 3.1数值计算方法验证

为了验证本文计算方法的正确性，对文献6的计算模型进行了计算，得到了反推流量比随风扇压比的变化曲线，计算结果与实验结果对比图如图5，由图5可见，计算所得反推流量比的分布趋势同试验测量结果一致，计算结果比试验测量值略高一些，说明本文的计算方法是可行的，可以比较精确地预测无阻流板式反推力装置的性能。

![](images/a5507e5dd708a0662a83b15616a976f072e36bbc5f4e2853fd3c68704cbae46b.jpg)  
图3网格以及边界条件  
图5反推流量比随风扇压比的变化  
Fig.5Reverse flow ratio changes with fan pressure ratio

# 3.2数值计算结果

图6给出了不同风扇进口压比条件下，不同叶栅安装角时反推流量比和反推力比的变化图。计算时，采用的二次流压比为6，风扇压比分别为1.3,1.4,1.5,1.6。由图可见，在较低压比时，随着安装角的增大，反推力比以及反推流量比都呈现先增大后减小的趋势，即存在最佳喷射位置，使反推力比以及反推流量比达到最大。随着风扇压比的增大，反推力比随着安装角的增大而减小，总的趋势为在较小安装角下时基本保持不变，随着安装角的进一步增大，反推力比迅速降低。而对于反推质量比来说，随着安装角的变化，反推流量比基本保持不变。

对于上述现象可以作如下简单解释。在风扇压比较小时（1.3)，外涵气流具有较小的能量，在相同的二次流压比情况下，其进入叶栅通道时偏转的角度也比较大。因此其最佳反推效率在较大的安装角时得到。在风扇压比较大的情况下（1.7)，外涵气流就较大的能量，在相同的二次流压比下，其进入叶栅通道的偏转角也比较小，因此其最佳安装角会比较小。

在 $4 5 ^ { \circ } - 6 0 ^ { \circ }$ 之间时，随着安装角的增大，外涵气流进入反推窗口的角度与叶栅通道的流路越来越吻合，气流流动越来越顺畅，同时由于安装角的增大，叶栅出口面积增大，前面叶栅通道的堵塞度降低，因此更多的气流可以流出叶栅通道，所以其反推效率会增加。在 $6 0 ^ { \circ } - 7 0 ^ { \circ }$ 之间，由于叶栅安装角增加，气流进入反推窗口角度偏离叶栅通道，使得气流在叶背处分离大大增加导致反推效率降低。同时，由于安装角的增加，叶栅通道出口面积增大，叶栅通道变成扩张形式，叶栅通道对流动的约束能力降低，所以其反推效率降低。

![](images/25bb6b52d2677f53e17b29ac23a317f0cb63796291f2cd9d1d938125502d2396.jpg)  
Fig.6thrust reverser performance changes with installation angle

为了进一步分析安装角对反推效率的影响，图7给出了低的风扇压比为1.3时，不同安装角下的马赫数和流线分布图。

对于风扇压比为1.3的情况，从图中可以看出，当二次流喷射时，高速射出的二次流会使外涵道主流发生偏转，并通过叶栅窗口迎着来流方向流出。在 $4 5 ^ { \circ } - 6 0 ^ { \circ }$ 之间，随着安装角的增大，各个叶栅通道的低速区都在减小，这就导致反推效率不断升高。在 $: 6 0 ^ { \circ } - 7 0 ^ { \circ }$ 之间，随着安装角的增大第一个叶栅通道的低速区迅速增大，第二三四叶片叶背分离去明显增大，这就导致随着安装角的增大，反推效率随之减小。

![](images/700df61d6544bab26f74d20c7e283eb26777795ea2f7a1f98408a07eaf9fe729.jpg)  
图7风扇压比1.3时不同安装角下的马赫数及流线分布图 Fig.7Mach number and streamline distribution under diferent installation angles at the fan pressure ratio of1.3

图8给出了风扇压比为1.6时的马赫数和流线分布图。从图中可以看出，第一个通道完全为回流区，即完全堵塞。随着安装角的不断增加，后面几个通道的低速区迅速增加，尤其是叶栅吸力面的分离区大大增加，叶栅通道面积大大减小，因此随安装角的增大反推效率大大减小。从图中可以看出，在较小的安装角下，叶栅通道对流动的约束更为强，因此流动更加顺畅，但随着安装角的进一步降低，叶栅通道会变得很窄，轻微的低速区就可能导致叶栅通道堵塞，因此，可以推测在较大风扇压比下，随着安装角的进一步减小，反推效率会有所降低，因此，再高的风扇压比下存在一个较小的最佳安装角，可以使反推效率达到最大。

随着风扇压比的增加，风扇流具有的能量增加，而二次流的能量未能增加，这就导致进入反推窗口的气流角比较小，随着安装角的增加，气流进入叶栅的攻角增加，导致叶背分离区增加，流动阻塞，因此反推效率减小。但如果叶栅安装角太小，叶背轻微的分离就可能导致整个叶栅通道完全堵塞，因此在较大压比下，存在较小的最佳安装角使反推效率达到最大。

![](images/cefaedda52734333366f5a52368564e9aa17cb7208c5ca20f3bc63944c9d36b2.jpg)  
图8风扇压比为1.6时不同安装角下的马赫数分布图 Fig.8 Mach number and streamline distribution under different installation angles at the fan pressure ratio of 1.6

# 4结论

本文对一无阻流门叶栅式反推装置的流场进行了数值模拟，详细分析了不同叶栅安装角对反推性能参数的影响。主要结论如下：

1）由于叶栅安装角影响气流进入叶栅通道相对角度，即影响气流在叶栅通道流动的顺畅度，同时影响叶栅出口气流方向，因此对反推效率有影响。

2）对于不同的风扇压比，存在最佳安装角使反推效率达到最大，而且压比不同，最佳安装角不同。

3）由于风扇压比较小时，气流所具有的能量较小，进入反推窗口的偏转角较大，所以在较小的风扇压比情况下，最佳安装角比较大。随着风扇压比的增加，气流具有的能量增加，其进入反推窗口的角度减小，因此，最佳安装角减小。

# ChinaXiv合作期刊

# 参考文献：

[1] Gilbert B, Marconi F, Kalkhoran I. Innovative Concept for Cascade Thrust Reverser Without Blocker Doors[C]. AIAA 1997-0823,1997   
[2] Nobel T P. Experimental Thrust Reverser Design with Computational Analysis[C].AIAA 94-0021,1994   
[3] Ferreira S B. Study of the Influence of Aircraft Geometry onthe Computed Flowfield During Thrust Reverser Operation[C]. AIAA 2006-3673,2006   
[4] Gilbert B. Innovative Concept for Cascade Thrust Reverser without Blocker Doors[C]. AIAA 97-823,1997   
[5] Marconi F. Computational Fluid Dynamics Support of the Development of a Blockerless Engine Thrust Reverser Concept[C]. AIAA 97-3151,1997   
[6] Asbury S C，Yetter J A. Static Performance of Six Innovative Thrust Reverser Conceptsfor Subsonic Transport Applications[R]. NASA TM-2000-210300,2000   
[7] Flamm JD. Experimental Study of a Nozzle Using Fluidic Counterflow for Thrust Vectoring[R]. AIAA98-3255,1998   
[8] 何艳，刘友宏．叶栅反推器出口安装角、压比对反推性能 的影响．科学技术与工程[J],2012,12(1):89-95 HE Yan, LIU Youhong. Efect of Blade Entrance Angle andPressure Ratio on Cascade Thrust Reverser Performance[J]. Science Technology and Enginering, 2010,12(1): 89\~95   
[9] 何艳，刘友宏．叶栅反推器几何进气角、压比对反推性能 的影响．科学技术与工程[J],2010,10(2):458-465 HE Yan,LIU Youhong. Effect of Blade Exit Angle and Pressure Ratio on Cascade Thrust Reverser Performance[J]. Science Technology and Engineering, 2010,10(2): 458-465   
[10]张国栋，王强．主要几何参数对叶栅式反推力装置性能 的影响．航空动力学报[J],2012,27(1):145\~151 ZHANG Guodong,WANG Qiang. Influence of Cascade Configuration on Aerodynamic Performance of a Cascade Thrust Reverser[J]. Journal of Aerospace power， 2012, 27(1): 145\~151   
[11]张国栋，王强．叶栅稠密度及进出口气流角对反推性能 的影响．飞机设计[J],2010,30(2):51\~56 ZHANG Guodong，WANG Qiang. The Influence of Cascade Solidity and Flow Angle of Inlet and Outlet on Aerodynamic Performance of Cascade Thrust Reverser[J]. Aircraft Design,2010, 30(2): 51\~56