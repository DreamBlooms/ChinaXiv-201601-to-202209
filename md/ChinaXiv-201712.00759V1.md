# 技术方法

# 一种结合低秩与稀疏惩罚的PET动态图像重建方法

魏夏平1,3,江学文²,马晓勉'，路利军1  
1南方医科大学生物医学工程学院,广东广州 510515;烟台毓璜顶医院核医学科,山东 烟台 26400；广东省  
人民医院//广东省医学科学院肿瘤中心放疗科，广东广州510080

摘要：目的 提出一种结合低秩与稀疏惩罚的PET动态图像重建方法(L&S)。方法 建立L&S重建模型,利用split Bregman法来最优化求解代价函数。采用单房室模型仿真一套PET心肌82Rb灌注图像，将L&S重建方法与最大似然期望值法(MLEM)、低秩惩罚和稀疏惩罚重建方法比较。结果L&S方法重建的图像的均方误差(MSE)最小，并且保留了更多图像特征。另外L&S重建得到的靶心图和参考组的靶心图最相近。结论L&S重建方法无论是在直观视觉上，还是定量分析上都优于另外3种方法。

关键词：低秩；稀疏；重建；心肌灌注

# Reconstruction of dynamic positron emission tomographic images by exploiting low rank and sparse penalty

WEI Xiaping1³, JIANG Xuewen²,MA Xiaomian1,LULijun   
1Schoolofomedicalgineeingouedicalesityangzouin;epartmentofucleareicit YuhuangdingHspitalntaina;epamntofdioogyCcerenteagdogenralHspitalangdoe of Medical Science, Guangzhou 510080,China

Abstract: Objective To propose a new method fordynamic positron emision tomographic (PET) image reconstruction using lowrank and sparse penalty(L&S).Methods TheL&Sreconstruction model was establishedandthesplit Bregmanmethod was used to solve the optimal cost function.The one-tissue compartment model was used to simulatea setof PET 82Rb myocardial perfusion image. The L&S reconstruction method was compared with maximum likelihood expectation maximization (MLEM) method,low-rank penalty method and sparse penalty method.Results The L&S reconstruction method had the smalest MSE and well maintained the feature information.The polar map created by L&S method was the most similar with the reference actual polar map.Conclusion L&S reconstruction method is better than theother three methods in both visual and quantitative analysis of the PET images.

Key words: low rank; sparse; reconstruction; myocardial perfusion

与传统的SPECT心肌成像相比，PET心肌灌注成像可以提高诊断准确性，更好地确认病灶位置，还能定量分析心脏血流[1-2]。尤其是PET动态心肌灌注成像还能测量心肌区域放射性药物的生物分布[3-4]，这就使得估计动力学参数例如示踪剂输送速率参数 $\mathbf { K } _ { 1 }$ 和心肌血流量(MBF)变得非常有意义。然而，PET动态心肌灌注成像主要还处于研究阶段，临床上还缺乏应用。主要的问题是将数据细分到短帧时，会带入噪声，从而影响心肌绝对血流的定量。传统上，标准的动态PET成像由单独的帧独立重建得到，然后在体素或ROI水平上运用动力学模型得到时间活度曲线(TAC)。独立图像重建主要靠统计图像重建方法实现，例如最大似然期望值法(MLEM)[5。然而，当在低计数情况下，直接采用MLEM算法方差很大。而且方差还会随着采样间隔的增大而增大。有人提出利用PET图像的稀疏特性的重建算法[。例如在PET动态图像重建中加入全变分正则约束。这种方法不论是在图像空间8，还是在测度空间上都得到了应用。另外多维小波去噪可以恢复隐藏在动态PET图像中的生物信号保真度，从而准确的定量心肌灌注。学者Su和Shoghi在2008提出小波降噪技术[],它对噪声敏感度低,在高噪声水平下可以提供更加准确的参数估计。

最近，有研究者提出了利用矩阵的低秩性质恢复图像。该研究首先在动态核磁共振成像[12-13]上受到关注，学者Lingala等[14-15]将其与稀疏先验结合分别运用到磁共振图像的恢复和重建上。在动态PET心肌灌注成像上，连续的图像之间有高度相关的冗余信息，这使得图像矩阵有很好的低秩性。另外在图像某些部分，含有血流灌注信息，这部分是稀疏的。因此，本文在动态PET心肌灌注成像上提出一种结合低秩与稀疏惩罚的重建方法(L&S)。我们利用splitBregman算法求解凸最优化问题，并利用真实的PET心肌 $^ { 8 2 } \mathrm { R b }$ 灌注成像来最优化正则化参数。我们在成像视觉上和信噪比上对L&S方法做了评估。同时我们将该算法与传统的MLEM算法以及单独利用稀疏或低秩惩罚的算法进行了比较。

# 1材料和方法

# 1.1 动态 $^ { 8 2 } R b \mathrm { P E T } \cdots$ 肌灌注仿真数据

在我们的仿真研究中，我们选用单房室模型，如图1所示,其中 $\mathbf { K } _ { 1 } ( \mathrm { m L / m i n / g } )$ ） $\mathbf k _ { 2 } ( 1 / \mathrm { m i n } )$ 为2个标准的动力学参数。左边红色框内的是动脉血，右边蓝色框内的是心肌组织，放射示踪物以 $\mathsf { K } _ { 1 }$ 的速率从动脉血进入心肌组织,并以反馈速率 $\mathbf { k } _ { 2 }$ 从心肌组织流回动脉血[16-17]。

![](images/60675fa9fae48292e5507bb2ace27675c39238b96ab0ee842fff09a422c45dc8.jpg)  
图1动态 $^ { 8 2 } \mathrm { R b }$ PET心肌灌注单房室模型  
Fig.1 One-tissue compartment model for kinetic modeling of 82Rb MPPET imaging.

这两个速率常数与动脉和心肌组织中的放射性活度成线性相关。动态过程可以通过如下方程描述：

$$
\frac { d C _ { m } ( t ) } { d t } = K _ { 1 } C _ { a } ( t ) \cdot k _ { 2 } C _ { m } ( t )
$$

其中 $C _ { a } ( t )$ 和 $| C _ { m } ( t )$ 分别是动脉血和心肌中 $^ { 8 2 } \mathrm { R b }$ 的浓度。通过测定左心室(LV)中心一小区域的 $^ { 8 2 } \mathrm { R b }$ 的浓度获得$C _ { L V } ( t )$ ，这是一种非侵入方法，几乎可以完全恢复动脉输入曲线,并最大限度减少心肌溢出 $\left( C _ { a } ( t ) = C _ { L V } ( t ) \right)$ 。而且，如果定义 $F _ { a }$ 为组织中的血浆体积分数，那么心肌中的放射示踪物浓度可以表示成：

$$
C ( t ) { = } F _ { a } C _ { a } ( t ) { + } ( 1 { - } F _ { a } ) C _ { m } ( t )
$$

其中， $F _ { a }$ 是0至1之间的实数，代表整个血液中的体积分数,包括：

(a)由于PET采样时的部分容积效应从血池进入心肌的

(b)肌肉中的动脉血

对方程(1)和(2)求解可以得到如下结果：

$C ( t ) = F _ { a } C _ { a } ( t ) + ( 1 - F _ { a } ) K _ { 1 } e ^ { - k _ { 2 } t } \otimes C _ { a } ( t )$ 其中， $\bigotimes$ 是卷积算子。

首先为多个区域(心肌，肺等)各自估计 $\mathbf { K } _ { 1 } , \mathbf { k } _ { 2 }$ 常数和 $| F _ { a }$ ，然后求其平均值。动脉血放射示踪物浓度 $C _ { a } ( t$ 通过计算动脉血采样的平均值得到。利用XCAT体模[18]，根据(3)式便可以生成一套动态PET心肌灌注图像。如图2所示，图2A给出了 $\mathbf { K } _ { 1 }$ 参数图像，图2B为采用单房室模型产生的时间活度曲线(TAC)。我们在 $2 \mathrm { m i n }$ 内采样10帧( $\lvert 1 0 \times 1 2 \mathrm { ~ s ~ } \rangle$ ,这是心肌灌注PET成像的常规采样协议。

# 1.2PET仿真断层成像

我们仿真了GE的RXPET/CTscanner型号扫描器[19]。仿真器产生无噪声投影数据,该数据经过放大，添加泊松噪声达到真实的临床噪声水平。仿真过程考虑了衰减，正则化的影响，这些影响都包含入了再重建过程。将得到的数据分别采用MLEM、低秩惩罚、稀疏惩罚和L&S四种方法重建。其中MLEM算法，经过63次迭代得到(等于用OSME算法，21个子集，3次迭代重建[的动态图像是 $1 2 8 \times 1 2 8 \times 4 7$ 的三维矩阵，体像素大小为 $3 . 2 7 \ : \mathrm { m m } \times 3 . 2 7 \ : \mathrm { m m } \times 3 . 2 7 \ : \mathrm { m m }$ 0

# 1.3低秩矩阵的恢复

将低秩矩阵 $X$ 从观测矩阵 $M$ 恢复的问题，如(4)式所示，其中 $M$ 是包含误差 $E$ 的矩阵 $\scriptstyle { M = X + E } )$ 。

$$
\operatorname* { m i n } _ { x } { \frac { 1 } { 2 } } / / X - M / / { \overset { 2 } { \underset { r } { } } } + \lambda r a n k ( X )
$$

其中rank( $\left. { X } \right.$ 代表矩阵 $X$ 的秩， $/ / \cdot / / _ { F }$ 为F-范数，是超参数，用来平衡第一项(保真项)和第二项(惩罚项)。直接求(4)式中目标函数的极小值是很困难的，因为里面包含秩惩罚。为了简化计算,将秩惩罚用核范数/ $X / /$ ”表示，

$$
\mathcal { M } X \mathcal { M } _ { * } = \sum _ { i } \sigma _ { i }
$$

其中 $\sigma _ { i }$ 是矩阵 $X$ 的奇异值。经过这样的松弛处理，低秩矩阵 $X$ 的恢复可以简化为：

$$
\operatorname* { m i n } _ { x } { \frac { 1 } { 2 } } / / X - M / / \sp 2 _ { _ { F } } + \lambda / / X / / _ { * }
$$

# 1.4L&S模型重建PET动态灌注图像

对于PET动态心肌灌注成像,令 $\cdot x ^ { t }$ 表示第帧图像的示踪剂活度， $\ t = 1 , 2 , . . . T , T$ 是动态图像总帧数， $\ v { x } _ { j \bar { \ v { j } } } ^ { t : }$ 表示第t帧第j个体素的示踪剂活度， $j = 1 , 2 , . . . N , N$ 为体素的总个数。由此，我们可以构造矩阵：

$$
X = \left( \begin{array} { l l l l } { x _ { 1 } ^ { 1 } } & { x _ { 1 } ^ { 2 } } & { \cdots } & { x _ { 1 } ^ { T } } \\ { x _ { 2 } ^ { 1 } } & { x _ { 2 } ^ { 2 } } & { \cdots } & { x _ { 2 } ^ { T } } \\ { \vdots } & { \vdots } & { \ddots } & { \vdots } \\ { x _ { N } ^ { 1 } } & { x _ { N } ^ { 2 } } & { \cdots } & { x _ { N } ^ { T } } \end{array} \right)
$$

其中， $\boldsymbol { X } \in \boldsymbol { R } ^ { N \times T } ,$ 代表所有的动态帧图像。矩阵 $X$ 的每一列表示相应帧图像的示踪剂活度，每一行表示对应体素的时间活度曲线(TAC)。矩阵 $X$ 实际上是背景部分和动态部分的叠加。背景部分代表帧或区域之间高度相关的部分(例如肌肉组织和肺)，这部分的示踪剂活度随时间变化缓慢，可以将其看作低秩部分(L)。动态部分代表帧或区域之间变化的部分(例如心肌和血池)，这部分的示踪剂活度随时间快速变化，是稀疏的(S)。因此我们在动态PET心肌灌注成像上同时引入低秩和稀疏惩罚，即L&S模型。求解过程可以表示成对一个凸优化问题的求解[14-15]

![](images/47904ed3106578db470cd7ef2ffda57d0f13f27df68a3e2f4c7e94109fd6d2ff.jpg)  
图2K参数图像和采用单房室模型产生的时间活度曲线(TAC)Fig.2 $\mathrm { K } _ { 1 }$ parametric image(A）and TACs generated using one-tissue compartmental model $\mathbf { \eta } ( B )$

$$
\displaystyle \operatorname* { m i n } _ { X } \frac { 1 } { 2 } \smash { \big / \smash { X - M \big / \smash { L _ { \varepsilon } ^ { 2 } } + \mu _ { L } \phi ( X ) + \mu _ { s } \varphi ( X ) } }
$$

其中， $\mu _ { L }$ 和 $\mu _ { s }$ 是相关的正则化参数， $\phi ( X )$ 是是谱惩罚项,将其用p-范数表示,定义为 $\wp ( X ) { = } ( \sum _ { i } \sigma _ { i } ^ { \ p } ) ^ { \frac { 1 } { p } }$ ,用来惩罚小的奇异值。当 $p <$ 1时，该惩罚项为非凸的范数，例如Lingala选择 $\scriptstyle \mathrm { p = 0 . 1 }$ 的谱惩罚[14]。这里，我们选择$p = 1$ ,将其简化为核范数。 $\varphi ( X ) ,$ 定义表示时间空间的全变分项，也就是矩阵在 $\mathbf { x } , \mathbf { y } , \mathbf { t }$ 方向的梯度的1-范数,通过有限差分估计，定义如下：

$$
\varphi ( X ) = \left\| { \bigl ( } \sum _ { i = 0 } ^ { 2 } { \Bigr | } \Phi _ { i } ^ { T } X \Psi _ { i } { \bigr | } ^ { 2 } { \bigr ) } ^ { \frac { 1 } { 2 } } \right\| _ { 1 }
$$

其中， $\Phi _ { 0 } = D _ { x }$ ， $\Phi _ { 1 } = D _ { \mathrm { y } }$ ， $\Phi _ { 2 } = I$ $\Psi _ { 0 } = I$ ， $\Psi _ { 2 } = D _ { t }$ ， $I$ 是单位矩阵， $D _ { x } , D _ { y } , D$ 是分别沿x,y,t方向的有限差分。

# 1.5最优化方法

本文采用splitBregman法[20-21]来最优化(8)式中的代价函数，它本质上来说是一种增广拉格朗日法。(8)式中代价函数的求解可以通过下列迭代实现：

$$
\begin{array} { r l } & { X ^ { \mathrm { K H } } = \operatorname { a r g m i n } \left\| X - M + Z ^ { * } \right\| _ { \gamma } ^ { 2 } + \beta \left\| { \boldsymbol { J } } \right\| _ { \gamma } ^ { 2 } + \beta \left\| { \boldsymbol { J } } \right\| _ { \gamma } ^ { 2 } } \\ & { \beta _ { z } \sum _ { i = 1 } ^ { K } \biggl \| \Phi _ { i } ^ { \prime } X ^ { \dagger } - S _ { i } ^ { * } + V _ { i } ^ { * } \biggr \| _ { \gamma } ^ { 2 } } \\ & { E ^ { * + 1 } = \operatorname { a r g m i n } \left\| X ^ { 1 + 1 } + L ^ { K } - L \right\| _ { \gamma } ^ { 2 } + 2 \mu _ { i } \mathcal { L } / \beta _ { i } \| { \boldsymbol { E } } \| . } \\ & { S ^ { * + 1 } = \operatorname { a r g m i n } \sum _ { i = 1 } ^ { K } \biggl \| \Phi _ { i } ^ { \prime } X ^ { * + 1 } \Psi _ { i } - S _ { i } ^ { * } + V _ { i } ^ { * } \biggr \| _ { \gamma } ^ { 2 } } \\ & { + 2 \mu _ { i } \beta _ { i } \biggl \| \biggl ( \sum _ { i = 1 } ^ { K } \left\| S _ { i } \right\| _ { \gamma } ^ { 2 } \biggr ) \biggr \| _ { \gamma } ^ { 2 } \biggr \| _ { \gamma } = 0 . 1 , 1 , 2 } \\ & { L ^ { * + 1 } = L ^ { K } + X ^ { * - 1 } + E ^ { * + 1 } } \\ & { V _ { i } ^ { * + 1 } = V _ { i } ^ { * } + \Phi _ { i } ^ { \prime } X ^ { * + 1 } \Psi _ { i } - S _ { i } ^ { * - 1 } \zeta _ { i } = 0 , 1 , 2 . } \end{array}
$$

# 2结果

为比较前面提到的不同重建方法的效果，我们比较了定量评价标准。均方误差定义为：

$$
M S E _ { R O I } = B i a s _ { R O I } ^ { 2 } + \mathrm { V a r } _ { R O I }
$$

其中,

$$
B i a s _ { R O I } ^ { 2 } = \frac { \sum _ { j = 1 } ^ { N } ( \overline { { x _ { j } } } - x _ { j } ^ { \mathrm { t r } u e } ) ^ { 2 } } { \sum _ { j = 1 } ^ { N } ( x _ { j } ^ { \mathrm { t r } u e } ) ^ { 2 } }
$$

$$
\operatorname { V a r } _ { R O I } = \frac { 1 } { R } \frac { \sum _ { r = 1 } ^ { R } \sum _ { j = 1 } ^ { N } ( x _ { j } ^ { r } - \overline { { x } } _ { j } ) ^ { 2 } } { \sum _ { j = 1 } ^ { N } ( x _ { j } ^ { \mathrm { t r } u e } ) ^ { 2 } }
$$

R是方差实现的总数(我们的仿真中 $\scriptstyle \mathrm { R = } 3 0$ ，N是ROI中的体素个数, $\begin{array} { r } { \overline { { \mathcal { X } } } _ { j } = \frac { 1 } { R } \sum _ { r = 1 } ^ { R } { x _ { j } ^ { r } } } \end{array}$ 代表PET图像在第 $j$ 个体素点的总平均值， $\boldsymbol { x } _ { j } ^ { r }$ 代表在指定ROI第 $j$ 个体素经过r次重建， $x _ { j } ^ { \mathrm { t r } u e }$ 代表参考组中第 $j$ 个体素点的真实的PET图像值。为了比较不同重建算法的性能，对每一帧动态图像计算其均方误差(MSE)，如图3所示，横坐标是帧，纵坐标是每个重建算法对应的帧的MSE。从图中可以明显地看出MLEM方法每一帧图像的MSE值都明显大于其它3种算法。采用低秩惩罚(L)重建的图像的MSE要小于采用稀疏惩罚(S)重建的图像的MSE。我们提出的L&S方法重建的图像的MSE是所有方法中最小的。

为了提供直接视觉比较，图4是给出了上述4种算法重建的图像。这些图像是4D动态PET心肌图像第26层断层图像的第10帧。从图中可以清楚地看到MLEM算法与稀疏惩罚(S)大幅增加了噪声水平，低秩惩罚(L)和L&S方法明显降低了噪声水平。与低秩惩罚(L)重建相比，L&S重建保留了更多图像特征。

此外，为了评价心肌缺损，我们还生成了左心室靶心图[22]。我们采用美国心脏协会的17段模型，它更适合评价室壁运动和心肌灌注[23]。图5显示了不同重建算法得到的第10帧图像的17段靶心图。通过比较，我们可以发现L&S方法生成的靶心图的和参考组的真实靶心图最相近。我们可以清楚地看到与其它重建方法相比，L&S重建图像的靶心图无论是在正常心肌区域的还是缺损部分，与参考靶心图的偏差都最小。

![](images/4baf6152795c681b0d92051ab245a7bda0ed35c1fb9f783159a06c811b225a38.jpg)  
图3不同重建算法对应帧的MSE Fig.3Plots of MSEvs frame number for reconstructed images by MLEM (black),sparse penalty(green),Low rank penalty (blue) and L&S (red) algorithm.

# 3讨论

本文提出了一种结合低秩与稀疏惩罚的(L&S)动态PET心肌灌注图像的重建方法。该方法可以表述为一个凸最优化问题。我们采用splitBregman 算法求解这个问题。我们用单房室模型仿真了一套动态PET心肌灌注图像，利用真实的动态PET心肌灌注成像来最优化正则化参数。本文提出的L&S重建算法得到的每帧动态图像的MSE是前面提到的算法中最小的。L&S重建不仅降低了图像噪声，而且保留了更多图像特征。此外比较不同算法重建的图像的靶心图，可以发现L&S方法生成的靶心图的灰度值和参考组的真实靶心图最相近，无论是在正常心肌区域的还是缺损部分，与参考靶心图的偏差都最小。

总之，我们提出的L&S重建算法得到的图像，无论是在直观视觉上，还是定量分析上都优于另外3种方法。

![](images/5c177cfb9d438bd24567313918d9fb189195cd49406bc49c244bc14ddf5ea77f.jpg)  
图4从左到右依次是真实图像(True)以及通过MLEM,稀疏惩罚(S)、低秩惩罚(L)和L&S重建得到的图像Fig.4Raw image and reconstructed images byMLEM,sparse penalty,lowrank penaltyand L&S algorithm.

![](images/ff6eab29d3bb48e0b37617b9e953bed37394ff593dcfbc8d25ce8f618ad1d7d2.jpg)  
图5从左到右依次是真实图像(True)的靶心图以及通过MLEM,稀疏惩罚(S)、低秩惩罚(L)和L&S算法重建得到的图像的靶心图

Fig.5Polar mapof theraw imageand reconstructed images byMLEM,sparse penalty,Lowrank penaltyand L&S algorithm.All the polar maps were shown in the same color bar.

# 参考文献：

[1]Sampson UK,Dorbala S,Limaye A,et al.Diagnostic accuracy of rubidium-82 myocardial perfusion imaging with hybrid positron emission tomography/computed tomography in the detection of coronary artery disease[J].JAm Coll Cardiol,2007,49(10):1052-8.   
[2]Bateman TM,Heller GV,Mcghie AI, et al. Diagnostic accuracy of rest/stressECG-gatedRb-82myocardialperfusionPET: comparison with ECG-gated Tc-99m sestamibi SPECT[J].JNucl Cardiol,2006,13(1): 24-33.   
[3]Coxson PG,Huesman RH,Borland L.Consequences of using a simplified kinetic model for dynamic PET data[J].J Nucl Med, 1997,38(4): 660-7.   
[4]El Fakhri G,Sitek A,Guérin B,et al. Quantitative dynamic cardiac 82Rb PET using generalized factor and compartment analyses[J]. J Nucl Med,2005,46(8): 1264-71.   
[5]Mumcuoglu EU,Leahy RM,Cherry SR.Bayesian Reconstruction of PET images: methodology and performance analysis [J].Phys Med Biol,1996,41(9): 1777-807.   
[6]Reader AJ, Zaidi H.Advances in PET image Reconstruction[J]. PET Clin,2007,2(2):173-90.   
[7]Shidahara M, Ikoma Y,Kershaw J,et al.PET kinetic analysis: wavelet denoising of dynamic PET data with application to parametric imaging[J].Ann Nucl Med,2007,21(7): 379-86.   
[8] Wang CY,Hu ZH, Shi PC,et al. Low dose PET Reconstruction with total variation regularization[C]//2O14 36TH Annual international conference of the ieee engineering in medicine and biology society (EMBC),2014: 1917-20.   
[9]Mehranian A,Rahmim A,Ay MR,et al.An ordered-subsets proximal preconditioned gradient algorithm for total variation regularized PET imageReconstruction [C]//NuclearScience Symposium and Medical Imaging Conference,2012: 3375-82.   
[10]Burger M,Mueller J,Papoutsellis E,et al．Total variation regularization inmeasurementand imagespaceforPET Reconstruction[J].Inverse Probl,2014,30(10):105003.   
[11] Su Y, Shoghi KI.Wavelet denoising in voxel-based parametric estimation of small animal PET images: a systematic evaluation of spatial constraints and noise reduction algorithms[J].Phys Med Biol,2008,53(21): 5899-915.   
[12] Zhao B,Haldar JP,Brinegar C,et al.Low rank matrix recovery for real-time cardiac mri[C]/2010 7TH ieee international symposium on biomedical imaging: From Nano To Macro,201O: 996-9.   
[13]Haldar JP,Liang ZP. Spatiotemporal imaging with partially separable functions: a matrix recovery approach[C]/2O1o 7TH ieee international symposium on biomedical imaging:From Nano To Macro,2010: 716-9.   
[14]Lingala SG,Hu Y,Dibella E,et al.Accelerated dynamic MRI exploiting sparsity and low-rank structure:k-t SLR[J].IEEE Trans Med Imaging,2011,30(5): 1042-54.   
[15] Zhao B,Haldar JP,Christodoulou AG,et al. Image Reconstruction from highly undersampled (k,t)-space data with joint partial separability and sparsity constraints[J]. IEEE Trans Med Imaging, 2012,31(9): 1809-20.   
[16]Rahmim A，Tang J,Mohy-Ud-Din H. Direct 4D parametric imaging in dynamic myocardial perfusion PET[J].Frontiers in Biomedical Technologies,2014,1(1): 4-13.   
[17]Mohy-Ud-Din H,Karakatsanis NA,Lodge MA,et al. Parametric myocardial perfusion PET imaging using physiological clustering [C]. Proc of Spie,2014,9038: 1-11.   
[18] Segars WP,Mahesh M,Beck TJ,et al.Realistic CT simulation using the 4D XCAT phantom[J].Med Phys,2008,35(8): 3800-8.   
[19]Kemp BJ,Kim C，Williams JJ，et al.NEMA NU 2-2001 performance measurements of an LYSO-based PET/CT system in 2D and 3D acquisition modes[J].JNucl Med,2006,47(12): 1960-7.   
[20] Osher S,Burger M,Goldfarb D,et al.An iterative regularization method for total variation-based image restoration[J].Multiscale Modeling Simulation,2005,4(2): 460-89.   
[21]Goldstein T, Osher S.The split bregman method for L1-Regularized problems[J]. SIAMJImaging Sci,2009,2(2): 323-43.   
[22] Cerqueira MD,Weissman NJ,Dilsizian V,et al. Standardized myocardial segmentation and nomenclature for tomographic imaging of the heart.A statement for healthcare professionals from the Cardiac Imaging Committee of the Council on Clinical Cardiology of the American Heart Association [J].Circulation, 2002,105(4): 539-42.   
[23]Lin GS,Hines HH, Grant G,et al.Automated quantification of myocardial ischemia and wall motion defects by use of cardiac SPECT polar mapping and 4-dimensional surface rendering[J].J Nucl Med Technol,2006,34(1): 3-17. (编辑·孙昌胆)