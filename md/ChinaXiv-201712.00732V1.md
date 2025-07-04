# 技术方法

# 基于高维全变分正则化的鲁棒低剂量CT心肌灌注去卷积方法

龚长飞}²,曾 栋}²,边兆英}²,张 华}²,张 璋³,张 敬³,黄 静}²,马建华1,2  
南方医科大学'生物医学工程学院，2广东省医学图像处理重点实验实,广东广州 510515;天津医科大学总医  
院放射科，天津 300052

摘要：目的 研发一种基于高维全变分(high dimension total variation,HDTV)先验的CT心肌灌注(computed tomographymyocardialperfusion,CT-MP)去卷积方法。方法 首先对低剂量CT-MP数据进行灌注去卷积建模,其后通过引入HDTV正则化修正模型最小化解的一致性。其中,HDTV利用心肌血管空间结构相似性和心肌血流信号时间连续性。结果XCAT心肌灌注仿真数据和猪心肌灌注数据实验表明，同已有的方法相比，本方法能更有效地抑制低剂量血流动力学参数图中的噪声和伪影，同时较好地保持具有诊断意义的结构信息。结论 本文方法可实现低剂量CT-MPI血流动力学参数图的优质成像。

关键词：CT;心肌灌注成像;低剂量;高维全变分正则化；去卷积

# Robust low-dose CT myocardial perfusion deconvolution via high-dimension total variation regularization

GONGChangfei,ZENGDong,AZhaoying,ZHANGHuad,ZHANGZhang,ZHANGJing,HUANGJing2,J 1SchoolofiomedicalEngineingGuangdongroncalKeyboatoryfedicalgerocsingoutheedicalesit Guangzhou5,;eprtmtfioloalspal,jicaleityin

Abstract: Objective To develop a computed tomography myocardial perfusion (CT-MP) deconvolution algorithm by incorporating high-dimension total variation (HDTV)regularization. Methods A perfusion deconvolution model was formulatedforthelow-dose CT-MPIdata,follwed by HDTVregularization toregularize theconsistencyof thesolution by fusingthespatialcorelationof the vascular structureand the temporal continuationof the blood flow signal. Results Both qualitative and quantitative studies were conducted using XCAT and pig myocardial perfusion data to evaluate the present algorithm.Theexperimental resultsshowed that thisalgorithmachieved hemodynamic parameter maps with better performances thantheexistingmethodsintermsofstreak-artifactsspprsion,noise-resolutiontradeof,anddigosis structure preservation. Conclusion The proposed algorithmcan achieve high-quality hemodynamic parameter maps in low-dose CT-MPI.

Key words: CT; myocardial perfusion imaging; low dose; high dimension total variation regularization; deconvolution

CT心肌灌注成像(CT-MPI)作为一种有效的非侵入功能成像方法，其在冠状动脉疾病(CAD)的诊断和危险分级方面有显著的优势[]。在CT-MPI的研究中，可以通过心肌灌注数据估计血流动力学参数图，比如心肌血流量(MBF)，心肌血容量(MBV)和平均通过时间(MTT)，这些血流动力学参数图可以为临床医生诊断提供重要辅助信息。CT血管造影技术和CT-MPI技术联合使用，不仅能提供冠状动脉狭窄的功能信息而且还能获得其狭窄部位的解剖结构信息[3]。根据扫描协议，CT-MPI对感兴趣层面连续多次增强扫描，和传统的CT扫描相比，这大大增加了病人所受的辐射剂量。大量研究表明，过高的X射线照射会诱发癌症，白血病或其他遗传性疾病[4。当前，临床上采用的低剂量扫描方案虽然是一种降低辐射剂量简单易行的手段，但常常会导致所采集的投影数据受到量子噪声的影响，使得重建CT心肌灌注图像质量出现严重退化，从而影响诊断的精确度。因此，在保证一定图像质量的条件下，如何降低CT-MPI中X射线辐射剂量已成为当前CT成像尤其是CT-MPI领域最为重要的课题之一。

当前，针对CT-MPI剂量降低问题，除了采用心电门控技术和优化扫描模式，许多抑制图像噪声的方法相继被提出[5-8]。如Speidel等[5]在不考虑运动伪影的条件下采用HYPR技术恢复低剂量心肌灌注图像，该技术能在一定程度上抑制CT心肌灌注图像噪声。Ritman等[6]考虑了由心脏运动带来的运动伪影影响，利用多排探测器CT进行部分扫描重建的MPI研究，提出了一种基于目标的空间频率滤波策略，该策略能够减少因部分扫描引入的重建伪影。Tao等将统计迭代(statisticaliterativereconstruction,SIR)方法应用于CT-MPI,这种直接作用于投影数据的CT迭代重建方法能有效的抑制噪声和条行伪影；Bian等8提出了基于SIR的运动自适应稀疏先验算法应用于低剂量CT心肌灌注图像重建，该方法利用了CT心肌灌注图像的空间及时间结构的稀疏特性并将运动校正过程引入到迭代重建过程中，该方法在噪声消除，伪影抑制和细节保持方面均有良好效果。虽然上述方法能够获得优质的CT心肌灌注图像，但是这些方法在利用得到的CT心肌灌注图像估计血流动力学参数图时采用不稳定的截断奇异值分解去卷积方法。根据文献[9,10」,若要获得具有诊断意义的血流动力学参数图，必须采用鲁棒的灌注去卷积方法。因此，为了提高血流动力学参数图的估计精度，近年来许多灌注去卷积方法相继被提出[9.10],Frindel等[9]构建了基于时空正则化去卷积模型应用于脑灌注加权MRI(perfusion-weightedmagneticresonanceimaging,PW-MRI),并提出了全局收敛算法求解相应的目标函数。Fang等[1]提出基于全变分(TV)正则化去卷积方法应用于低剂量CT脑灌注成像，该方法能够有效改善脑血流动力学参数图。

受基于TV正则化去卷积模型启发，本文提出一种基于高 维全变分（High dimension total variation,HDTV)正则化的CT心肌灌注去卷积方法。其中，HDTV正则化利用了心肌血管空间结构相似性和心肌血流信号时间连续性。同时，针对新构建的CT-MPI去卷积目标函数的求解，本文提出一种改进的交替方向法优化策略。心肌灌注仿真数据和猪心肌灌注数据实验表明，与传统的去卷积方法[-14]相比，本文方法能更有效地抑制低剂量血流动力学参数图中的噪声和伪影，同时较好地保持具有诊断意义的结构信息。

# 1方法

1.1CT灌注参数估计的去卷积法

基于示踪剂稀释理论[13]和CT灌注参数的计算模型[14-16],组织剩余函数 $R ( t )$ 计算方式如下：

$$
C \left( t \right) = \mathrm { M B F } \cdot C _ { a } \left( t \right) \ast R \left( t \right) = C _ { a } \left( t \right) \ast k \left( t \right)
$$

其中， $\divideontimes$ 为卷积算子符号， $C _ { a } ( t )$ 表示动脉对比剂浓度，也称之为动脉输入函数(arterialinput function,AIF)， $C ( t )$ 表示组织内的对比剂浓度， $k ( t ) = M B F \cdot R ( t )$ ；(1)式中$C ( t ) \bar { \mathcal { F } } \mathbb { H } C _ { a } ( t )$ 可从灌注数据直接测量获得， $k ( t )$ 是未知的中间变量,MBF,MBV和MTT等灌注参数可以通过 $k ( t )$ 求得。根据文献[10,14]，卷积方程式(1)可被离散化为矩阵形式，对于感兴趣层面单个像素的卷积离散化矩阵表达式为：

$$
A k = c
$$

此时 $\cdot _ { A } \in \mathbb { R } ^ { N \times N }$ $N$ 是采样次数， $\boldsymbol { c } \in \mathbb { R } ^ { N }$ 和 $\boldsymbol { k } \in \mathbb { R } ^ { N }$ 。相对于(2)式，整个感兴趣层面的卷积离散化矩阵表达式为：

$$
A K = C
$$

其中 $\boldsymbol { C } = \left[ c _ { 1 } { \cdots } , c _ { L } \right] \in \mathbb { R } ^ { N \times L }$ ， $K = \left[ k _ { 1 } \cdots , k _ { L } \right] \in \mathbb { R } ^ { N \times L }$ $L$ 表示感兴趣层面的像素个数 $\mathbf { \Sigma } _ { \circ } ( 1 )$ 式是基于这样的假设：对比剂到达AIF的时间不小于到达感兴趣层面组织的时间；实际中，我们测得的AIF并不一定是该组织的AIF，一般情况下AIF都会延迟于 $\dot { \mathbf { } } C ( t )$ ,AIF和C $( t ) .$ 之间的时间漂移会导致计算的灌注参数不精确；为了避免对比剂延迟问题,许多研究提出了不同的解决方法[12.17-18],其中${ \mathrm { w } } _ { \mathrm { u } }$ 等2采用块循环矩阵 $( A _ { c i r c } )$ 去卷积法效果较为显著，$A _ { c i r c }$ 中的元素 $\dot { a } _ { c i r c }$ 可表示如下：

$$
\left( a _ { c i r c } \right) _ { i , j } = \left\{ \begin{array} { l l } { \Delta t c _ { a r t } \Big ( t _ { i - j + 1 } \Big ) , } & { f o r j \leq i } \\ { \Delta t c _ { a r t } \Big ( t _ { M + i - j + 1 } \Big ) , } & { f o r j > i } \end{array} \right.
$$

这里， $\Delta t _ { \perp }$ 是数据采样时间间隔 $, i , j = 1 , \cdots N , M = 2 N$ 矩阵K和C也要从N维扩展到M维，将(3)式替换为：

$$
H X = Y
$$

此时 $\cdot H { = } A _ { c i r c } , X { \in } \mathbb { R } ^ { M \times L } { \mathcal { F } } \mathbb { H } Y { \in } \mathbb { R } ^ { M \times L }$ 分别是对 $K$ 和C补零扩展后的矩阵[14]。

# 1.2基于HDTV正则化的去卷积模型

关于(5)式的最小二乘解等价于极小化该式的二次欧几里得残差范数，可计算如下：

$$
X _ { l s } = \underset { K \in \mathbb { R } ^ { M \times L } } { \arg \operatorname* { m i n } } \Bigl ( \big \| H X - Y \big \| _ { 2 } ^ { 2 } \Bigr )
$$

其中， $H$ 是一个病态的托普利茨矩阵，因此 $X _ { l s }$ 并不是一个正定的最小二乘解，只要Y中微小的变化(投影噪声)就会导致 $X _ { l s } { ' }$ 很大变动；为了得到优质的 $X _ { l s }$ ，考虑到心肌血管空间结构相似性和心肌血流信号时间连续性，本文提出了基于HDTV正则化的去卷积模型，可表示为：

$$
X _ { H D T V } = \underset { X \in \mathbb { R } ^ { M \times L } } { \arg \operatorname* { m i n } } \bigg ( \frac { 1 } { 2 } \big \| H X - Y \big \| _ { 2 } ^ { 2 } + \lambda \psi \big ( X \big ) \bigg )
$$

其中，正则化项y $( \boldsymbol { X } )$ 定义为

$$
\psi \big ( X \big ) = \Bigg \| \sqrt { \sum _ { i = 0 } ^ { 2 } \biggl | \Phi _ { i } ^ { T } X \Psi _ { i } \biggr | ^ { 2 } } \Bigg \| _ { \ell _ { 1 } }
$$

其中， $\Phi _ { 0 } = D _ { x } , \Psi _ { 0 } = I , \Phi _ { 1 } = D _ { y } , \Psi _ { 1 } = I , \Phi _ { 2 } = I , \Psi _ { 2 } = D _ { t } ; D _ { x }$ $D _ { y }$ 和 $| D _ { i } |$ 是分别沿着 $x$ ,y和t三维的有限差分算子;为正则化参数。

# 1.3优化策略

为了极小化(7)式，通过引入辅助变量S把(7)式转变成一个等价的约束问题，如下：

$$
\operatorname* { m i n } _ { X , S } { \frac { 1 } { 2 } } { \big \| } H X - Y { \big \| } _ { 2 } ^ { 2 } + \lambda { \bigg \| } \sqrt { \sum _ { i = 0 } ^ { 2 } { \big | } S _ { i } { \big | } ^ { 2 } } { \bigg \| } _ { \ell _ { 1 } } \quad s . t . ~ S _ { i } =
$$

$$
\Phi _ { i } ^ { T } X \Psi _ { i } ; i = 0 , 1 , 2
$$

对于(9)式求解等价于极小化下面的增广拉格朗日函数[19]

$$
L \big ( \boldsymbol { X } , \boldsymbol { S } _ { i } \big ) = \frac { 1 } { 2 } \big \| \boldsymbol { H } \boldsymbol { X } - \boldsymbol { Y } \big \| _ { F } ^ { 2 } + \lambda \bigg \| \left. \sqrt { \sum _ { i = 0 } ^ { 2 } \big | \boldsymbol { S } _ { i } \big | ^ { 2 } } \right\| _ { \ell _ { 1 } } +
$$

$$
\frac { \beta } { 2 } { \sum _ { i = 0 } ^ { 2 } } \Big | \Big | \Phi _ { i } ^ { T } X \Psi _ { i } \Big | \Big | _ { F } ^ { 2 } + { \sum _ { 0 } ^ { 2 } } \Big \langle Z _ { i } , \Phi _ { i } ^ { T } X \Psi _ { i } - S \Big \rangle
$$

其中， $Z _ { i }$ 为拉格朗日乘子， $\beta$ 为惩罚参数，两个矩阵的内积定义为 ${ \big \langle } A , B { \big \rangle } = \operatorname { t r } a c e { \Big ( } A ^ { T } B { \Big ) } .$ 。我们使用交替极小化方法极小化(10)式,具体如下：

$$
\begin{array} { r l } & { X _ { k + 1 } = \underset { X } { \arg \operatorname* { m i n } } \| H X - Y \| _ { F } ^ { 2 } + \frac { \beta } { 2 } \underset { i = 0 } { \overset { \textstyle 2 } { \sum } } \| \Phi _ { i } ^ { T } X \Psi _ { i } \| _ { F } ^ { 2 } } \\ & { S _ { k + 1 } = \underset { \{ s _ { i } ^ { 3 } \} } { \arg \operatorname* { m i n } } \frac { 1 } { 2 } \underset { i = 0 } { \overset { \textstyle 2 } { \sum } } \| ( \Phi _ { i } ^ { T } X \Psi _ { i } + \frac { Z _ { k } } { \beta } ) - S _ { i } \| } \\ & { + \frac { \lambda } { \beta } \|  \sqrt { \underset { i = 0 } { \overset { \textstyle 2 } { \sum } } | S _ { i } | ^ { 2 } } \| _ { \ell _ { 1 } } ; i = 0 , 1 , 2 } \end{array}
$$

$$
\boldsymbol { Z } _ { i , k + 1 } = \boldsymbol { Z } _ { i , k } + \left( \boldsymbol { \Phi } _ { i } ^ { T } \boldsymbol { X } \boldsymbol { \Psi } _ { i } - \boldsymbol { S } _ { i , k + 1 } \right) ; i = 0 , 1 , 2
$$

本文采用共轭梯度算法求解(11)式，(12)式的求解使用多维收缩算法[20]

$$
S _ { k + 1 } = \frac { P _ { i } } { \displaystyle \sum _ { i = 0 } ^ { 2 } \bigl \| P _ { i } \bigr \| ^ { 2 } } \Biggl ( \sum _ { i = 0 } ^ { 2 } \bigl \| P _ { i } \bigr \| ^ { 2 } - \frac { \lambda } { \beta } \Biggr ) _ { + }
$$

此时 $\mathbf { \partial } ^ { \cdot } P _ { i } = \Phi _ { i } ^ { T } X \Psi _ { i } + \frac { Z _ { k } } { \beta }$ Z,(13)式是对拉格朗日乘子Zi的更新。

# 2结果与讨论

为了验证新方法在低剂量CT心肌灌注去卷积中的有效性，我们通过XCAT体模仿真和动物数据实验分别进行了定性分析和定量分析。

# 2.1XCAT心肌灌注体模实验

本实验中，选择修订的 $\mathrm { X C A T } ^ { [ 2 1 ] }$ 体模仿真生成CT心肌灌注数据。CT仿真扫描的成像参数如下：XCAT体模图像大小为 $5 1 2 \times 5 1 2$ ，层厚为 $1 \mathrm { m m }$ ;射源到旋转中心和探测器的距离分别为 $7 4 6 ~ \mathrm { m m }$ 和 $1 3 6 1 ~ \mathrm { m m }$ ；管电压为 $1 2 0  { \mathrm { k V } }  { \mathrm { p } }$ ，旋转角在 $[ 0 , 2 \pi ]$ 间采样值为1160,探测器个数为672。低剂量投影数据生成方法参考文献[22-23」，其中光子总数设为 $2 . 5 { \times } 1 0 ^ { 5 }$ ，噪声方差 $\cdot \sigma _ { e } ^ { 2 } = 1 0$ ,最后对噪声测量数据进行FBP重建获得低剂量CT-MPI图像；为了体现本文方法对缺血心肌显示的优越性，我们通过临床医生指导在XCAT体模上定义了一块马蹄形缺血心肌区域；图1给出了真值和低剂量仿真XCAT心肌灌注图像，其中黑色箭头所示为缺血心肌。

C 8 A B

Fig.1 XCAT myocardial perfusion image and low-dose image reconstructed from the simulated projection data.A:XCAT myocardial perfusion phantom;B: low-dose myocardial perfusion image reconstructed from the simulated projection data.

为了定量分析不同方法的血流动力学参数图像质量，本文计算了标准参数图像与四种去卷积方法得到的参数图像之间的峰值信噪比(peak signalto noise ratioPSNR)和相对均方根误差(relative root mean squareerror,rRMSE),其计算公式如下：

$$
P S N R = 1 0 \log _ { 1 0 } \left( \frac { M A X ^ { 2 } \big ( \mu _ { x \mathrm { t r } u e } \big ) } { \displaystyle \sum _ { n = 1 } ^ { Q } \big ( \mu ( n ) - \mu _ { x \mathrm { t r } u e } \big ( n \big ) ^ { 2 } / \big ( Q - 1 \big ) \big ) } \right) ( \
$$

$$
r R M S E = \sqrt { \frac { \displaystyle { \sum _ { n = 1 } ^ { Q } } \big ( \mu ( n ) - \mu _ { x \mathrm { t r } u e } ( n ) \big ) ^ { 2 } } { \displaystyle { \sum _ { n = 1 } ^ { Q } } \big ( \mu _ { x \mathrm { t r } u e } ( n ) \big ) ^ { 2 } } }
$$

$\mu _ { x { \mathrm { t r } } u e }$ 表示标准参数图像， $\mu$ 表示低剂量去卷积得到的参数图像， $\boldsymbol { \mathcal { Q } }$ 是感兴趣层面内的像素个数。

图2所示为不同去卷积方法得到XCAT体模心肌灌注MBF，MBV和MTT血流动力学参数图像，其中这三种去卷积方法：标准截断奇异值分解(standardtruncated singular value decomposition, sSVD)方法[]、快循环矩阵截断奇异值分解(block-circulanttruncatedsingularvaluedecomposition,bSVD)方法[2和Tikhonov正则化方法4目前广泛应用于商业灌注CT设备中。从图2可以看出，由sSVD方法得到的三种参数图均含有严重的噪声和条形伪影，正常心肌和缺血心肌区域几乎被噪声淹没;bSVD和Tikhonov的结果稍有改善，但是与Phantom参数图相比存在较大差距，且无法从其MBF，MBV和MTT参数图像中分辨缺血心肌轮廓；本文方法结果明显优于其他三种方法，从MBF参数图中可以清晰的判断正常心肌和缺血心肌边界，进一步观察可以发现，本文方法得到的MBF，MBV和MTT参数图中背景区域和心脏区域条形伪影的抑制效果显著;通过与其他三种方法对比，本文方法降低噪声同时保持精确定量的参数图估计。图3分别对应于图2中的MBF，MBV和MTT的水平轮廓图(Profile)。相对于sSVD,bSVD和Tikhonov方法，本文方法所得的轮廓图在心室，缺血心肌和健康心肌区域都更接近于体模参数图的轮廓图，继而说明本文方法能够实现低剂量CT-MPI血流动力学参数图的优质成像。

![](images/8e2b334d2720db035ee12863e99c2f6a4d216a697dbad86db4259a85a50358dd.jpg)  
图2不同去卷积方法得到XCAT体模MBF、MBV、MTT血流动力学参数图Fig.2 Hemodynamic parameter mapsofthe XCATmyocardialperfusionphantombydiferent methods.MBF inunitof mL·100 $\mathbf { g } ^ { - 1 }$ ·min,MBV in unit of $\mathrm { \ m L / 1 0 0 ~ g } ,$ MTT in sec.

为了定量分析这4种方法的差异性，表1列出了图2中各参数图的PSNR和rRMSE测量值。由表1可以看出，相对于sSVD,bSVD和Tikhonov方法，HDTV方法可以获得最高的PSNR测量值和最小的rRMSE测量值；尤其从MBF参数图的定量分析表明本文方法获得更高的PSNR和更低的rRMSE。

# 2.2动物数据实验

为进一步验证本文方法的有效性，我们对一组猪的CT心肌灌注数据进行了测试。实验数据由GE公司DiscoveryCT75064层CT设备采集，射源到扫描物体和探测器的距离分别为 $5 3 8 . 5 2 \mathrm { m m }$ 和 $9 4 6 . 7 4 6 \ \mathrm { m m }$ ；管电压和管电流分别为 $1 2 0 \mathrm { k V } , 1 0 0 \mathrm { m A }$ ，层厚为 $5 ~ \mathrm { m m }$ ，CT机架旋转一周时间为0.4s；旋转角在 $[ 0 , 2 \pi ]$ 间采样值为984,探测器个数888。为了减少辐射剂量避免二次扫描，根据文献[22-23」,我们通过获得的高剂量心肌灌注数据仿真猪的低剂量心肌灌注数据。图4给出了猪的高剂量和低剂量仿真心肌灌注图像。

图5显示了不同方法计算的心肌血流动力学参数图。由图5可以看出，本文提出的HDTV正则化去卷积方法抑制了噪声和伪影的同时保持了清晰的细节。从MBF参数图可以看出本文方法估计的MBF和高剂量得到的MBF具有高度一致性，而sSVD，bSVD和Tikhonov方法获得的MTT参数图严重退化。基于奇异值分解的Tikhonov方法获得的三种参数图在噪声较少和条行伪影抑制方面有一定的改善，但是通过总体对比，本文方法在噪声滤除和边缘细节保持两方面表现更为突出。表2所示为图5中各参数图的PSNR和rRMSE测量值，可以看出，本文方法较其他方法在真实动物数据实验中具有更好的噪声抑制性能。

![](images/483691f952a6c97fdc200e251490b61da86dfecabddee5823ec7a302bd5333f1.jpg)  
图3图2中血流动力学参数图的水平轮廓图 Fig.3 Horizontal profiles (186 th row, 250 th to 336 th columns)of hemodynamic parameter maps in figure 2.A:Result from MBF;B: Result from MBV; C: Result from MTT.

![](images/256ba7654b200c30cfbd302ab03c68681409377011ff48439c1a79b8ff331634.jpg)

表1对应图2中各参数图的PSNR和rRMSE Tab.1PSNR and rRMSE measured on the parameter maps in Fig.2   

<html><body><table><tr><td rowspan="2">Method</td><td colspan="2">MBF (mL·100 g·min1)</td><td colspan="2">MBV (mL/100 g)</td><td rowspan="2"></td><td colspan="2">MTT (s)</td></tr><tr><td>PSNR</td><td>rRMSE</td><td>PSNR</td><td>rRMSE</td><td>PSNR</td><td>rRMSE</td></tr><tr><td>sSVD</td><td>22.2456</td><td>0.4638</td><td>19.1955</td><td>0.6438</td><td></td><td>6.9944</td><td>4.7795</td></tr><tr><td>bSVD</td><td>21.7904</td><td>0.6251</td><td>21.9737</td><td>0.4823</td><td></td><td>4.6393</td><td>6.3393</td></tr><tr><td>Tikhonov</td><td>22.1086</td><td>0.5563</td><td>21.3343</td><td>0.5352</td><td></td><td>6.3917</td><td>5.5313</td></tr><tr><td>HDTV</td><td>34.0013</td><td>0.087</td><td>32.5322</td><td>0.1459</td><td></td><td>19.2882</td><td>1.2750</td></tr></table></body></html>

![](images/32d09f13873c99b9f998ae1b6c2bf5f2bd214fbfdb550c28a7ee1b0191d35192.jpg)  
图4高剂量和低剂量仿真猪心肌灌注CT图像  
Fig.4Preclinical porcine high-dose myocardialperfusionimageand low-dose image reconstructed from the simulated projection data.A: Highdose CT-MP image reconstructed by the FBP；B: Low-dose CT-MP image reconstructed by FBP.

# 3结论

针对低剂量CT心肌灌注去卷积估计动力学参数不准确问题,本文提出一种基于HDTV正则化的去卷积方法，其中，HDTV正则化利用心肌血管空间结构相似性和心肌血流信号时间连续性。为了评价本文方法的优异性，我们采用XCAT仿真和猪心肌灌注数据进行实验。通过与SVD、bSVD和Tikhonov去卷积方法实验结果对比，本文方法实验结果表明能有效抑制心肌血流动力学参数图噪声和伪影，且本文方法的实验结果更加逼近XCAT真值参数图和高剂量猪参数图。我们从MBF,MBV和MTT参数图可以清晰判断出缺血心肌的位置和大小，这对于临床有实际的应用意义。

![](images/42b7ae2c802468a89d31b12a46ba5486fa8a973a339a580e3781120aa482a7a6.jpg)  
图5不同去卷积方法得到猪的MBF、MBV、MTT血流动力学参数图Fig.5 Hemodynamic parameter maps of pig myocardial perfusion image by diferent methods. MBF in unit of $\mathrm { \ m L / 1 0 0 \ g / m i n , }$ MBV in unit of $\mathrm { \ m L } / 1 0 0 \mathrm { g } ,$ and MTT in sec.

表2对应图5中各参数图的PSNR和rRMSE Tab.2PSNR and rRMSE measured on the parameter maps in Fig.5   

<html><body><table><tr><td rowspan="2">Method</td><td colspan="2">MBF (mL/100 g/min)</td><td rowspan="2"></td><td colspan="2">MBV (mL/100 g)</td><td colspan="2">MTT (s)</td></tr><tr><td>PSNR</td><td>rRMSE</td><td>PSNR</td><td>rRMSE</td><td>PSNR</td><td>rRMSE</td></tr><tr><td>sSVD</td><td>23.6417</td><td>0.4134</td><td>29.2716</td><td>0.3206</td><td></td><td>15.3749</td><td>0.1694</td></tr><tr><td>bSVD</td><td>21.1776</td><td>0.6426</td><td>28.3514</td><td>0.4505</td><td></td><td>16.6818</td><td>0.2154</td></tr><tr><td>Tikhonov</td><td>21.2826</td><td>0.6753</td><td>27.9775</td><td>0.4631</td><td></td><td>17.5036</td><td>0.3517</td></tr><tr><td>HDTV</td><td>34.7795</td><td>0.1317</td><td>34.6883</td><td>0.1805</td><td></td><td>21.0989</td><td>0.0865</td></tr></table></body></html>

由于算法引入惩罚参数入来平衡保真项和正则化项，本文未对进行自适应优化设计，而是通过去卷积过程的视觉评价，因此存在一定的缺陷；另外，本文仅列出了三种商业软件广泛使用去卷积方法作为对比，还有其他重建和图像后处理方法需要进一步的对比试验；还有本文实验基于XCAT体模仿真和动物实验，若要实现本文方法的临床应用，还需要进行更为广泛的临床实验。

# 参考文献：

[1]Becker A,Becker C.CT imaging of myocardial perfusion: possibilities and perspectives[J].JNucl Cardiol,2013,20(2): 289-96.   
[2]George RT,Jerosch-Herold M,Silva C,et al.Quantification of myocardial perfusion using dynamic 64-detector computed tomography[J]. Invest Radiol,2007,42(12): 815-22.   
[3]Mehra VC,Ambrose M,Valdiviezo-Schlomp C,et al.CT-based myocardial perfusion imaging-practical considerations:acquisition, image analysis,interpretation，and challenges [J].J Cardiovasc TranslRes,2011,4(4):437-48.   
[4]Brenner DJ,Hall EJ. Computed tomography-an increasing source of radiation exposure[J].N EnglJMed,2007,357(22): 2277-84.   
[5]Speidel MA,Bateman CL,Tao Y,et al.Reduction of image noise in low tube current dynamic CT myocardial perfusion imaging using HYPR processing:a time-attenuation curve analysis[J].Med Phys, 2013,40(1):011904.   
[6]Ramirez-Giraldo JC,Yu L,Kantor B,et al.A strategy to decrease partial scan Reconstruction artifacts in myocardial perfusion CT: phantom and in vivo evaluation[J].Med Phys,2012,39(1): 214-23.   
[7]Tao Y,Chen GH,Hacker TA，et al.Low dose dynamic CT myocardial perfusion imaging using a statistical iterative Reconstruction method[J].Med Phys,2014,41(7): 071914.   
[8]Biao ZY,Gong CF, Zeng D,et al.Motion Adaptive Sparsity Prior forLow-dose Dynamic CT Myocardial Perfusion Imaging[D].The 13th International Meeting on Fully Three-Dimensional,2015.   
[9]Frindel C,Robini MC,Rousseau D.A 3-D spatio-temporal deconvolution approach for Mr perfusion in the brain[J].Med Image Anal,2014,18(1):144-60.   
[10]Fang R,Zhang S.Chen T,et al.Robust low-dose CT perfusion deconvolution via tensor total-variation regularization [J]. IEEE Trans Med Imaging,2015,Feb 20.[Epub ahead of print]   
[11] Ostergaard L,Weisskoff RM,Chesler D,et al.High resolution measurement of cerebral blood flow using intravascular tracer bolus passages.Part I: Mathematical approach and statistical analysis[J].Magn Reson Med,1996,36(5): 715-25.   
[12]Wu O,Ostergaard L,Weisskoff RM,et al. Tracer arrival timinginsensitive technique for estimating flow in Mr perfusion-weighted imaging using singular value decomposition with a block-circulant deconvolution matrix[J].Magn Reson Med,2003,50(1):164-74.   
[13]Zierler K. Indicator dilution methods for measuring blood flow, volume,and other properties of biological systems:a brief history and memoir[J].Ann Biomed Eng,2000,28(8): 836-48.   
[14]Fieselmann A,Kowarschik M,Ganguly A,et al. Deconvolutionbased CT and MR brain perfusion measurement: theoretical model revisited and practical implementation details[J].Int J Biomed Imaging,2011: 467563.   
[15]Fahmi R,Eck BL,Vembar M,et al.Dynamic CT myocardial perfusion imaging:detection of ischemia in a porcine model with FFRverification[J].Proc SPIE,2014:9038.   
[16]Fahmia R,Eck BL,Vembar M,et al.Dose reduction assessment in dynamic CT myocardial perfusion imaging in a porcine ballooninduced-ischemia model[J].Proc SPIE Med Imaging,2014: 9033.   
[17] Calamante F,Gadian GD,Connelly A.Delay and dispersion effects in dynamic susceptibility contrast mri: simulations using singular value decomposition[J].Magn Reson Med,200o,44(3): 466-73.   
[18]Mouannes-Srour JJ,Shin W,Ansari SA,et al. Correction for arterial-tissue delay and dispersion in absolute quantitative cerebral perfusion DSC Mr imaging[J]. Mag Reson Med,2012,68(2): 495-506.   
[19]Hestenes M. Multiplier and gradient methods [J].J Optim Theo Appl,1969,4(1): 303-20.   
[20] Yang J, Zhang Y.Alternating direction algorithms for L1-problems in compressive sensing [J]. SIAM J Sci Comput,2011,33(1): 250-78.   
[21] Segars WP, Sturgeon G,Mendonca S,et al. 4D XCAT phantom for multimodality imaging research [J].Med Phys,2010,37(9): 4902-15.   
[22]Ma JH,Liang ZR,Fan Y,et al. Variance analysis of $\mathbf { \boldsymbol { x } }$ -ray CT sinograms in the presence of electronic noise background[J].Med Phys,2012,39(7): 4051-65.   
[23]Ma J, Zhang H,Gao Y,et al. Iterative image Reconstruction for cerebral perfusion CT using a pre-contrast scan induced edgepreserving prior[J].Phys Med Biol,2012,57(22): 7519-42. (编辑：吴锦雅）