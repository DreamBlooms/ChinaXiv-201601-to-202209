# MSMA传感器多参数变化时特性研究

鲁　军　于庆洋　苏超锋（沈阳理工大学自动化与电气工程学院沈阳110159）

![](images/0cd4dc268308d5605340ca81ae6428c68effb866cb623cb5099537710f7a031b.jpg)

鲁军男1965年生，博士，教授，研究方向为智能材料与智能控制系统。

摘要：磁控形状记忆合金（MSMA）在磁场作用下产生形变，施加外部激振力时会引发材料本身磁感应强度变化，进而表现为电信号变化。本文基于该特性设计和制作了MSMA传感器样机，并搭建了实验系统，建立了基于马氏体变体体积分数变化的感应电压模型，研究了偏置磁场、预压力和激振力（幅值和频率）多参数变化时的MSMA传感器输出特性。通过传感器实验值与计算值的比较，验证了多个参数变化时传感器模型的通用性和正确性，为MSMA传感器在复杂条件下的应用奠定了理论和技术基础。

关键词：MSMA 传感器 多参数模型感应电压中图分类号：TM315

# Characteristics Study of Multi-Parameter Change ofMSMA Sensor

Lu Jun Yu Qingyang Su Chaofeng (Shenyang Ligong UniversityShenyang110159 China )

![](images/f52bdebfd960a08a06e70337cbc2cfea1e705580fb477b1f0f8c0371dcc89dc4.jpg)

于庆洋男1989年生，硕士研究生，研究方向为智能检测与信息处理。

Abstract: Magnetic controlled shape memory alloy (MSMA) produces deformation under the action of magnetic field, the magnetic flux density of the material itself can change when the external exciting force is applied,and then manifest as an electric signal change. Based on the characteristics,a MSMA sensor prototype is designed and produced in this paper,and the experimental system is built. Induced voltage model is established based on the change of Martensitic variants volume fraction. The output properties of MSMA sensor are studied under the multi-parameter change of bias magnetic field, prepressure and exciting force (frequency and amplitude).By compared of experimental values and calculated values of sensor, the universality and validity is proved on sensor model at multi-parameter change,the research work gives a foundation in theory and technology both for the application of MSMA sensor in complex condition.

Keywords: MSMA, sensor, multi-parameter, model, induced voltage

# 1 引言

磁控形状记忆合金（Magnetic ControlledShapeMemoryAlloy，MSMA）是一种新型功能材料，室温下可表现为由磁场或者力诱导马氏体重取向，其马氏体重取向宏观应变可达到 $10 \%$ 。 $\mathrm { \Delta N i _ { 2 } M n G a }$ 是研究最为广泛的一种MSMA，它响应快，性价比高，同时具有磁致伸缩和压电陶瓷的优势[1-5]。根据MSMA马氏体变体重取向种类的不同，可以分为正效应和逆效应。正效应是在磁场作用下诱发磁有利取向变体，元件长度伸长，之后撤去磁场在力的作用下形变恢复；逆效应是在元件产生形变后，在偏置磁场条件下，机械力作用于MSMA材料，力有利取向增多，磁场有利取向变体减少，元件内部磁通改变，对外表现为电信号变化[。基于MSMA正效应的执行器应用已有研究，而可以用于传感器的逆效应则报道较少。此前的传感器模型大多是关于感应电压的经验公式，不具有通用性[7-8]。因此本文的目的是从实际应用情况出发，考虑传感器在复杂外部条件下感应线圈中的电压变化，提出了一种新的感应电压模型，并设计制作了MSMA传感器。将感应电压理论值与实验结果作对比，验证了多个参数改变时传感器输出的变化规律和模型适应性。

# 2 MSMA传感器工作原理

MSMA材料以传感器方式工作时其变化过程如图1所示。由图1可以看出：预压力 $F _ { 0 }$ 作用下，MSMA元件初始长度为 $l _ { 0 }$ ；当对其施加磁场时，MSMA元件长度为 $l _ { 1 }$ ，此时施加与预压力同向的激振力，元件的长度再次减小到 $l _ { 2 }$ ，元件内部磁通改变，对外表现为电信号变化。撤去激振力，元件恢复到长度 $l _ { 1 }$ 。

![](images/a817d2b0d8bc01cd4fffe7a5decf36bfde51cc2a8b861569ee631e14d47cfe18.jpg)  
图1MSMA逆效应原理图

此过程中MSMA材料内部孪晶界变化如图2所示，阶段1时力有利取向变体为主要组成部分，此时无明显的李晶界移动；阶段2由力有利取向变体和磁有利取向变体共同构成，出现了明显的孪晶界；阶段3力有利取向变体继续增多。图2中，加粗的箭头表示激振力和预压力的叠加作用。

![](images/9059858082a413bd31e3f9df2018b8f4d9a3050e632e6a67c02d7e957e556616.jpg)  
图2MSMA材料受力过程和微观变化 Fig.2Loading process and microscopic change of MSMA materials

# 3 传感器实验系统

传感器实验系统如图3所示，实验使用尺寸为 $2 . 5 \mathrm { m m } \times 5 \mathrm { m m } \times 2 0 \mathrm { m m }$ 、主要成份为 $\mathrm { N i } _ { 2 } \mathrm { M n G a }$ 的MSMA元件。本文利用MSMA逆效应研制了一种传感器样机，由励磁线圈、感应线圈、可动顶杆、挡板、弹簧、调整螺母和MSMA元件组成。为恢复

![](images/a7a6f9a96248ac8ae9eeede567304f256924b2b547864a3bc97ea379a2637e60.jpg)  
Fig.1Principle diagram ofMSMA inverse effect   
图3MSMA传感器实验系统  
Fig.3Experiment system of MSMA sensor

MSMA元件形变，采用弹簧施加轴向预压力。信号发生器产生一个正弦信号后经过放大器作为激振器的输入信号，激振器对MSMA元件施加变化的力信号，感应线圈上的电压信号可以输入到示波器中，力、霍尔和涡流传感器分别检测激振力、磁通密度和 $\mathrm { N i } _ { 2 } \mathrm { M n G a }$ 元件位移。

# 4 MSMA传感器模型

由于力和磁场共同施加于MSMA元件，每个单晶的总磁化强度由 $M _ { 3 }$ 和 $M _ { 4 }$ 叠加得到。微观上，MSMA每个单晶中磁畴是任意分布的，具有磁各向异性的特点。磁化矢量与易磁化轴间存在角度，称为磁化旋转角，用 $\theta$ 表示。在施加磁场时，磁化矢量沿着磁场方向以使磁能最小化引起磁化旋转角改变，其示意图4所示。

![](images/9b5283f0967b19704f133327af64c4021bc02f75931a28722cd185583c6fb434.jpg)  
图4磁化旋转角变化过程

Fig.4Change process of magnetization rotation angle

图4中箭头表示磁化矢量，虚线表示易磁化轴方向。在外部磁场作用下，磁化矢量会向易磁化轴旋转一个角度。假定室温下每个马氏体变体含有两种磁畴， $_ { 1 - \alpha }$ 代表第一类磁畴的体积分数， $\alpha$ 代表第二类磁畴的体积分数。两个变体和两个磁畴联系共有四个不同的磁化区域。实验表明，即使在很小的磁场作用下，也有一种磁畴区域消失（因为 $\alpha =$ 1)，故两种磁畴区域仅剩一种。

假设 $\alpha$ 总是为 $1 ^ { [ 9 ] }$ 。四个磁域的磁化旋转角分别是 $\theta _ { 1 }$ ， $\theta _ { 2 }$ ， $\theta _ { 3 }$ ， $\theta _ { 4 }$ ，且 $\theta _ { 1 } = \theta _ { 4 }$ 。然而，由于只有第二类磁畴存在，所以只有角度 $\theta _ { 3 }$ 和 $\theta _ { 4 }$ （两者方向垂直）出现在材料中。

磁化强度的改变导致磁通密度随时间改变，磁通密度的改变与电压成正比。 $M _ { 3 }$ ， ${ \bf \nabla } { M _ { 4 } }$ 与 $M _ { x } , \ M _ { y }$ (磁化矢量在 $x$ 和 $y$ 轴上的分量）的关系式为

$$
{ \left( \begin{array} { l } { M _ { 3 } } \\ { M _ { 4 } } \end{array} \right) } = M _ { \mathrm { s } } { \left( \begin{array} { l l } { - \sin \theta _ { 3 } \ \cos \theta _ { 3 } } \\ { \cos \theta _ { 4 } \ \sin \theta _ { 4 } } \end{array} \right) } { \left( \begin{array} { l } { M _ { x } } \\ { M _ { y } } \end{array} \right) }
$$

式中， $M _ { \mathrm { s } }$ 为磁畴的饱和磁化强度； $M _ { x }$ 和 $M _ { y }$ 为磁化矢量在 $x$ 和 $y$ 轴上的分量。

由于轴向作用力只产生轴向内部磁场，则只有一种磁晶各向异性能且磁化矢量的旋转是可逆过程。Kiefer和Lagoiudas推出内部磁化旋转的表达式[10]为

$$
\sin \theta _ { 3 } = \frac { \mu _ { 0 } M _ { \mathrm { s } } H } { 2 K _ { \mathrm { u } } }
$$

$$
\theta _ { 4 } = 0
$$

式中， $H$ 为施加的磁场强度； $K _ { \mathrm { u } }$ 为磁晶各向异性能，因为磁域4的易磁化轴与外部磁场一致，其相对于易磁化轴的磁化旋转为0。在力和磁场作用下，每个单晶的总磁化强度由 $M _ { 3 }$ 和 $M _ { 4 }$ 叠加得到，关系式为

$$
M _ { \varkappa } = ( 1 - \xi ) M _ { 3 } + \xi M _ { 4 }
$$

将式（2）和式（3）代入式（4)，假设 $\alpha = 1$ 且只有 $H$ 场存在，则

$$
M _ { ☉ } = ( 1 - \xi ) M _ { \mathrm { s } } \sqrt { 1 - \left( \frac { \mu _ { 0 } M _ { \mathrm { s } } H } { 2 K _ { \mathrm { u } } } \right) ^ { 2 } }
$$

$$
M _ { \mathfrak { H } } = \xi M _ { \mathrm { s } } + ( 1 - \xi ) \frac { \mu _ { 0 } ( M _ { \mathrm { s } } ) ^ { 2 } H } { 2 K _ { \mathrm { u } } }
$$

其中， $H$ 沿着纵轴，即 $H _ { \mathfrak { s } \backslash \lambda } = H$ ，横轴方向上磁场强度为0，即 $H _ { \ast \ast } = 0$ 。

不同变体的体积分数 $\xi$ 为[11]

$$
\xi = \frac { 1 } { 2 } \cos \left[ - \frac { 1 } { C } ( - \sigma \varepsilon _ { \mathrm { m } } - \mu _ { 0 } M _ { \mathrm { s } } H + b _ { 1 } - b _ { 2 } - Y ) + \pi \right] + \frac { 1 } { 2 }
$$

其中， $\sigma = F _ { \mathrm { m } } \mathrm { s i n } \ \omega t / S _ { \mathrm { M S M A } }$ ，为元件截面受到的激振应力； $\varepsilon _ { \mathrm { m } }$ 为元件的最大轴向应变； $S _ { \mathrm { M S M A } }$ 是元件的横截面积； $b _ { 1 }$ ， $b _ { 2 }$ 、 $C$ 和 $Y$ 都是本构模型的修正参数，为常数。且

$$
B = \mu _ { \mathrm { 0 } } ( H + M _ { ☉ } )
$$

元件变体体积分数改变导致磁化强度的改变，使得磁通密度随时间改变，由法拉第感应定律可得

$$
u = - \frac { \partial B } { \partial t } N S
$$

式中， $N$ 为线圈匝数； $B$ 为样品磁化导致的磁感应强度； $s$ 为元件垂直于磁场方向的面积。

将式（6）代入式（8）计算得到磁感应强度，

再代入式（9）得到力和磁共同作用下的感应电压表达式为

$$
u = R \varepsilon _ { \mathrm { m } } F _ { \mathrm { m } } f \sin [ \frac { 1 } { C } ( \varepsilon _ { \mathrm { n } } ^ { \prime } F _ { \mathrm { m } } \sin 2 \pi f t - \mu _ { 0 } M _ { \mathrm { s } } H +
$$

$$
b _ { 1 } - b _ { 2 } - Y ) + \pi \Biggr ] \times \cos 2 \pi f
$$

其中

$$
R = \frac { 1 } { C } N S \pi \frac { \mu _ { 0 } ^ { 2 } M _ { \mathrm { s } } ^ { 2 } H } { 2 K _ { \mathrm { u } } }
$$

最大应变 $\varepsilon _ { \mathrm { m } }$ 与预压力 $F _ { 0 }$ 有关，即

$$
\begin{array} { c } { { \varepsilon _ { \mathrm { m } } = 0 . 0 6 - 0 . 7 7 / 1 0 ^ { 2 } \times F _ { \mathrm { 0 } } - 0 . 5 2 / 1 0 ^ { 2 } \times F _ { \mathrm { 0 } } ^ { 2 } - } } \\ { { 0 . 8 1 / 1 0 ^ { 3 } \times F _ { \mathrm { 0 } } ^ { 3 } - 0 . 3 9 / 1 0 ^ { 4 } \times F _ { \mathrm { 0 } } ^ { 4 } } } \end{array}
$$

# 5 实验结果分析

实验中以力和磁场的参数为变量，各个常量参数取值分别为： $M _ { \mathrm { s } } = 4 . 8 5 \times 1 0 ^ { 5 } \mathrm { k A / m }$ ， $\mu _ { 0 } = 4 \pi \times$ $1 0 ^ { - 7 } \mathrm { H / m }$ ， $K _ { \mathrm { u } } { = } 1 . 5 6 \times 1 0 ^ { 5 } \mathrm { J } / \mathrm { m } ^ { 3 }$ ， $S = 1 2 . 5 \mathrm { m m } ^ { 2 }$ ， $N = 1 \ 5 0 0$ ，$C = 4 . 5$ ， $b _ { 1 } = 1 . 9 5 6$ ， $b _ { 2 } = 7 . 6 2$ ， $Y = 5 6 . 4 2$ 。为了验证模型的通用性，同时改变多个参数来观察感应电压的变化规律。由于实际应用中预压力很少改变，所以在实验中预压力保持不变（ $\mathrm { ^ { \prime } 0 . 4 8 \ M P a } ,$ ，且以下实验都是在室温下进行。

# 5.1幅值和频率同时变化的感应电压变化规律

保持偏置磁场为 $0 . 4 8 \mathrm { T }$ ，同时改变激振力的幅值和频率，计算传感器输出的感应电压瞬时值如图5所示。

![](images/bd3b357141dd66316051d3ab344fdadd917a6a739ec95baf6e58c720cdeeea30.jpg)  
图5幅值和频率同时变化

感应电压峰-峰值计算值与实验结果对比如图6所示。比较序号3、4和5可以看出，频率和幅值同时增大时，感应电压增大。这是因为频率的增加能使变体的生长和消失速度变快，幅值的增加能使变体1的含量增多，二者的叠加作用使得感应电压增大。比较序号5、6和7可以知道，虽然频率增大，但是感应电压值仍然减小，所以幅值增大对感应电压的作用更为明显。

![](images/3157b13cd9f3fb69fc03bed7f51e2f2d6904ff973606ad41a478c365e5b17e03.jpg)  
图6幅值和频率同时变化下的感应电压峰-峰值 Fig.6Peak-peak value of the induced voltage under amplitude and frequency simultaneously

# 5.2幅值和偏置磁场同时变化时的感应电压变化规律

保持激振力频率为 $7 0 0 \mathrm { H z }$ 不变，同时改变激振力的幅值和偏置磁场，由模型计算出的感应电压如图7所示。感应电压峰－峰值计算值与实验结果对比如图8所示。

![](images/f3e3539d8c452c6aa864b6395967372ce9fc4b36b41528e0f243098ce8867af7.jpg)  
Fig.5Amplitude and frequency change at the same time   
图7幅值和偏置磁场同时变化  
Fig.7Amplitude and biased magnetic field change at the same time

比较序号3、4和8可知，偏置磁场增大的同时幅值减小，虽然偏置磁场和幅值变化相对较小，但感应电压变化较大。这是因为在较小幅值和偏置磁场下，力的作用相对于磁场而言更明显。磁化旋转开始的难度要大于变体增加的难度。比较序号2和7可知，虽然幅值和偏置磁场都增大，但是感应电压的增加并不明显。这是因为力和磁场之间需要较大变化才能有明显的磁化角度旋转和较多的新马氏体生成，从而对外表现出较大的感应电压信号变化。

![](images/db871ade8a93b728f39802660c2cdeb1e5f677b7a1a6ed05a655140430ccc30b.jpg)  
图8幅值和偏置磁场同时改变下的感应电压峰-峰值 Fig.8Peak-peak value of the induced voltage under amplitude and bias magnetic field change simultaneously

# 5.3频率和偏置磁场同时变化时的感应电压变化规律

保持激振力幅值为1N不变，同时改变激振力的频率和偏置磁场大小，模型计算结果如图9所示。感应电压峰－峰值计算值与实验结果对比如图10所示。

![](images/92fe6ea078237ce2b254d34178805f0df5288bf91ae3c9c5e3f0907e60acb622.jpg)  
图9激振器频率和偏置磁场同时变化

![](images/2151c0508f169ccf88cdcecce1563e752cfc137fcff130baf7beb9384ae9bebb.jpg)  
Fig.9Frequency and biased magnetic field change at the same time   
图10频率和偏置磁场同时改变下的感应电压峰－峰值 Fig.1OPeak-peak value of the induced voltage under frequency and bias magnetic field change simultaneously

通过序号3和序号4可以看出，虽然频率不是所有序号中最大的，但是感应电压最大，表明此时偏置磁场比频率的作用更为明显。比较序号5和8、6和7，偏置磁场增大的同时频率减小，虽然偏置磁场只增大了 $0 . 0 6 \mathrm { T }$ ，感应电压却呈倍数增大。表明相较于频率，偏置磁场对于感应电压的作用更为明显。这是因为当偏置磁场较大时，虽然频率会改变马氏体的生长和消失，但是磁场会使得大部分马氏体保持磁场有利变体不变，而频率的作用则不明显。

# 6 结束语

从微观马氏体变体体积分数变化和磁化旋转角变化出发推导出MSMA在偏置磁场和力作用下的感应电压变化，建立了一种在复杂条件下具有通用性的MSMA传感器模型。保持预压力不变，由研制的传感器样机进行了实验研究，结果表明：感应电压峰-峰值的实验数据和计算值基本一致；同时改变幅值和频率，二者都与感应电压正相关，且幅值对于感应电压的影响更大；在较小的激振力幅值和偏置磁场下，幅值的作用更明显且二者必须有较大的变化才能对外表现出明显的感应电压信号变化；以频率和偏置磁场为变量时，偏置磁场的作用更为明显。

# 参考文献

[1] Sozinov A,Likhachev AA,Ullakko K.Crystal structures and magnetic anisotropy properties of $\mathrm { N i } _ { 2 }$ MnGa martensitic phases with giant magnetic-fieldinduced strain[J]. IEEE Trans.Magn.,2002,38(9): 281-284.   
[2] 曾建斌，白保东，曾庚鑫，等．考虑压力变化的 超磁致伸缩超声换能器动态模型[J]．电工技术学 报，2012，27(10)：215-219. Zeng Jianbin,Bai Baodong,Zeng Gengxin,et al. Dynamic models of giant magnetostrictive ultrasonic transducer taking account into variable pressure[J]. Transactions of China Electrotechnical Society, 2012,27(10): 215-219.   
[3] Ullakko K,et al. Magnetically controlled shape memory alloys:a new class of actuator materials[J]. Journal of Materials Engineering and Performance, 1996,15(3): 405-409.