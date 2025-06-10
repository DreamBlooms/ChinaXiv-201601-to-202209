# 基于几何形态群组特征的R波检测算法

刘炜a,b,c，王林bc，李润川b,，佘维a,b,c，蒋建豫c(郑州大学a.软件与应用科技学院;b.产业技术研究院;c.互联网医疗与健康服务河南省协同创新中心，郑州 450000)

摘要：准确检测心电R波是辅助诊断心脏疾病的关键。针对R波检测问题，提出了基于几何形态群组特征的 R波检测算法。算法首先用滤波器组对心电信号进行预处理，然后通过整体与局部兼顾的信号处理方式计算几何形态特征值，并使用群组中三个几何形态特征值检测R波，最后采用MIT-BIH标准心律失常数据库验证算法。实验结果表明，算法对R波检测的错检率为 $1 . 0 7 \%$ ，灵敏度为 $9 9 . 3 8 \%$ ，精确率为 $9 9 . 6 1 \%$ ，准确率为 $9 8 . 9 9 \%$ 。

关键词：滤波器组；几何形态；群组特征；R波检测 中图分类号：TP391.7 doi: 10.19734/j.issn.1001-3695.2018.07.0549

R wave detection algorithm based on geometric morphology group characteristics

Liu Weia, b,c, Wang Linb,c,Li Runchuanb,c, She Weia,b,c, Jiang Jianyuc† (a.Software&AppliedScience&TechnologyInstitute,b.IndustrialTechnologyResearchInstitute,c.Internetmedical& health service Henan Collaborative Innovation Center,Zhengzhou University,Zhengzhou 45ooo0, China)

Abstract:The accurate detectionofECGR wave is the keyto asist in the diagnosis of heart disease.FortheR wave detection problem,this paper proposes an R-wave detection algorithm based on geometric group features.Firstly，the algorithmpreprocessestheECGsignal withthefilterbank.Then,itcalculates geometriceigenvalues bymeansofsignal processing givingconsiderationtobothoverallandlocal,anduses thethree geometric eigenvalus inthe grouptodetectthe Rwave.Finaly,itadopts MIT-BIHStandardArrhythmiaDatabaseto testandverifythisalgorithm.Theexperimental results show that the error detection rate of the algorithm for R wave detection is $1 . 0 7 \%$ ,the sensitivity is $9 9 . 3 8 \%$ ，the accuracy rate is $9 9 . 6 1 \%$ ,and the precision rate is $9 8 . 9 9 \%$ ：

Key words: filter bank; geometric morphology; group characteristics; R wave detection

# 0 引言

心血管疾病严重威胁人类健康，在我国心血管疾病也逐渐成为高发病。心电图（ECG）是心脏活动的综合体现，能够反映人体心脏的健康状况，某些病变可以通过ECG波形的异常体现出来[1.2]。目前心电图广泛应用在医学上辅助医生鉴别与分析各种心脏疾病。心电波形的检测在心电图分析上起着非常重要的作用，通过心电波形的检测可以得到准确的心率，而心率是衡量心脏疾病的重要指标。ECG检测能够及早的发现心脏病，通过预防和治疗可以降低心脏病人的死亡率。在ECG的各种波形中R波是心电信号分析的基础,是检测心律是否正常以及诊断心血管疾病的关键。

差分阈值法是最早应用在R波检测上的算法，也是R波检测的经典方法，但是当出现强干扰时算法的检测效果会有明显的下降。随着计算机技术的发展与科研人员对心电信号检测研究力度的不断增大，各种新型的信号处理算法也被应用在心电图的R 波检测中。常用算法有小波变换法[3-6]，动态自适应阈值法[7\~10]，神经网络[1]等方法。例如Razavit等人[5]提出基于小波变换的方法检测R波，先对心电信号进行预处理滤除噪声，然后对信号进行连续小波变换，同时采用阈值法来检测QRS波群的R波，实验结果表明该算法有较高的准确性。基于小波变换的检测算法虽然检测率高，但是运算量大，处理大量数据时实时性差。Chen等人[10]提出的基于自适应阈值的心电R波检测算法，通过设置阈值并且不断检查每个心动周期的方式来提高算法的准确率，实验结果显示该算法提高了R波检测的准确率。动态自适应阈值法虽然提高了检测的准确率，但是每次检测都要对阈值进行更新，增加了算法的复杂度。

在以上方法的基础上，许多学者通过改进常用算法与结合不同的算法提出了一些新的方法来进行R波检测[12-17]，但是很少能够兼顾到算法的准确率、普适性和简便性。本文通过分析常用R波检测方法的优缺点，在Yazdani等人[18]提出的自适应数学形态学检测算法的启发下提出了基于几何形态群组特征的R波检测算法，使用MIT-BIH标准心律失常数据库的心电信号数据作样本数据进行实验，实验结果表明本文提出的算法具有较高的灵敏度和准确率而且普适性好，运算简单。

# 1 数据预处理

人体内心电信号频率低，容易受到各种因素的干扰。因此，通常采集的心电信号会掺杂着各种噪声。相同的信号源产生的心电噪声对心电信号的影响具有相似性，通常可以把这些噪声归为一类，然后选取合适的方法进行滤波。典型的噪声有肌电干扰、基线漂移，肌电干扰属于高频干扰噪声，基线漂移属于低频噪声。通常进行R波检测时都需要先进行滤波，滤除心电信号中的噪声对于R波检测非常关键。对滤波后的心电信号再进行R波检测，能够减少错检的发生，提高波形检测的准确率。

常用的高频滤波器有FIR低通滤波器和带通滤波器。FIR低通滤波器能够在保证任意幅频特性的同时具有严格的线性相频特性，又因其具有有限长的单位抽样响应，因此滤波器具有稳定性在图像处理领域中应用广泛。带通滤波器的原理是设置上限、下限两个频率界限，输入信号的频率处于上限、下限之间才能够通过滤波器，超出或者低于设置的值都将会被过滤掉。带通滤波器整个频率通带内都能最大限度的让信号通过，而其阻带对信号有衰减和抑制作用。基线漂移噪声的滤除可以使用中值滤波器[19]和多项式拟合滤波器。中值滤波器运算速度快并且设计简单，对于使用整数表示的图像，因为从窗口到窗口更新直方图简单而且寻找直方图的中值不繁琐，所以中值滤波器更加有效。多项式拟合法先对信号进行多项式拟合，然后用原始信号减去拟合信号，得到去除基线的信号，但是多项式拟合在处理较大的漂移时效果不佳。通过对比各类滤波器的优缺点，本文最终采用FIR低通滤波器先对心电信号的肌电干扰噪声进行滤除，然后用中值滤波器对心电信号再次滤波，消除基线漂移噪声，由FIR低通滤波器和中值滤波器构成滤波器组进行信号预处理。

# 1.1 FIR滤波器

在数字信号处理中FIR滤波器应用广泛，主要功能是把干扰信号减弱或滤除得到所需的信号。本文设计的基于窗函数的FIR低通滤波器就是有选择性的减弱或滤除一些特定频率范围内的信号。从时域出发利用窗函数法设计FIR滤波器通过选取合适的窗函数，把无限长的理想 $h _ { d } \left( n \right)$ 截为有限长的$h ( n )$ ，用 $h ( n )$ 逼近 $h _ { d } \left( n \right)$ ，使频率响应 $H ( e ^ { j w } )$ 和所求的理想频率响应 $H _ { d } ( e ^ { j w } )$ 接近。其中窗函数的选取对于设计FIR滤波器是很重要的，需要通过所要设计的滤波器的性能指标对窗函数的类型以及窗口的长度进行确定，最后进行整体性能检测。

数字滤波器传输函数为 $H _ { d } ( e ^ { j w } )$ ， $h _ { d } ( n )$ 是与理想频响对应的理想单位抽样响应序列，公式如下：

$$
H _ { d } \left( e ^ { j w } \right) = \sum _ { n = - \infty } ^ { + \infty } h _ { d } \left( n \right) e ^ { - j w n }
$$

$$
h _ { d } \left( n \right) = \frac { 1 } { 2 \pi } { \int _ { - \pi } ^ { \pi } { { { H } _ { d } } \left( { { e } ^ { j w } } \right) { { e } ^ { j w n } } d w } }
$$

因为 $h _ { d } \left( n \right)$ 通常是无限长的非因果序列，而本文需要的为有限长的低通滤波器，为了达到设计目的，可以采用对$H _ { d } ( e ^ { j w } )$ 进行近似逼近的方法。常用方法是用窗函数法进行FIR低通滤波器设计[20]，选取适当的窗函数截取 $h _ { d } \left( n \right)$ ，公式如下：

$$
h \left( n \right) = h _ { d } \left( n \right) w \left( n \right)
$$

在式（3）中， $w ( n )$ 为偶对称且有限长的窗，本文设计时选用的窗函数为汉明窗：

$$
w \left( n \right) = \left[ 0 . 5 4 - 0 . 4 6 \cos { \left( \frac { 2 n \pi } { N - 1 } \right) } \right] R _ { N } \left( n \right)
$$

其幅度响应为

$$
W \left( w \right) = 0 . 5 4 W _ { R } \left( w \right) + 0 . 2 3 \Biggl [ W _ { R } \Biggl ( w - \frac { 2 \pi } { N - 1 } \Biggr ) + W _ { R } \Biggl ( w + \frac { 2 \pi } { N - 1 } \Biggr ) \Biggr ]
$$

由 $w ( n )$ 对称性以及卷积定理得如下公式：

$$
H \left( e ^ { j w } \right) = { \frac { 1 } { 2 \pi } } H _ { d } \left( e ^ { j w } \right) \ast w \left( e ^ { j w } \right)
$$

窗函数法是应用窗函数取有限长脉冲响应，以 $h ( n )$ 来逼近 $h _ { d } \left( n \right)$ 的方法，在FIR滤波器设计中应用广泛。

# 1.2中值滤波器

中值滤波是以排序统计理论为基础的有效抑制噪声的信号处理技术。一维信号处理最先应用中值滤波技术，随后二维信号处理也逐渐开始应用。中值滤波的原理是把数字图像或数字序列中某一点处的值用该点的一个邻域中各点值的中值代替。设一维序列为 $x _ { 1 } , x _ { 2 } , x _ { 3 } , . . . x _ { n }$ ，把这些元素按从小到大排列进行中值滤波，如果元素总数为偶数，则中值为中间两元素的均值，元素总数为奇数，中值为中间的元素值[21]，公式如下：

$$
y = m e d \{ x _ { 1 } , x _ { 2 } , x _ { 3 } . . . , x _ { n } \} = \left\{ \begin{array} { c c } { { \displaystyle { \frac { 1 } { 2 } } \Biggl [ x _ { _ { i \frac { ( n + 1 ) } { 2 } } } + x _ { _ { i ( \frac { n } { 2 } + 1 ) } } \Biggl ] } } & { { n \stackrel { . } { \sum } \Biggl [ \left( x _ { _ { i \frac { ( n + 1 ) } { 2 } } } + x _ { _ { i ( \frac { n } { 2 } + 1 ) } } \right) } } \\ { { x _ { _ { i \frac { ( n + 1 ) } { 2 } } } } } & { { n \stackrel { . } { \sum } \nonumber } } \end{array} \right.
$$

记为

$$
y _ { i } = m e d \{ x _ { i } \}
$$

$y _ { i }$ 是一维序列 $x _ { 1 } , x _ { 2 } , x _ { 3 } , x _ { 4 , } , , , , , x _ { i }$ 的中值。把中值滤波的概念推广到二维，选用特定形式的二维窗口对二维序列进行中值滤波，二维信号的中值滤波公式如下：

$y _ { i j } = m e d _ { A } \{ X _ { i j } \} , A$ 为滤波窗口

# 2 GMGC_R算法

本文提出的基于几何形态群组特征的R波检测算法GMGC_R的创新点为对信号的处理做到了整体与局部的兼顾、自适应性好。整体与局部结合的信号处理方式提升了检测的准确率，在对信号求几何特征值 $V = \{ \nu _ { 1 } , \nu _ { 2 , } , \ldots , , \nu _ { n } \}$ 时，某一点的 $V = \{ \nu _ { 1 } , \nu _ { 2 , } , \ldots , , \nu _ { n } \}$ 如果远远高于其相邻点的 $V = \{ \nu _ { 1 } , \nu _ { 2 , } , \ldots , , , \nu _ { n } \}$ （204号则会影响算法中几何形态的判定进而影响算法的准确率，本文通过计算连续四点 $V = \{ \nu _ { 1 } , \nu _ { 2 , } , \ldots , , , \nu _ { n } \}$ 的均值 $V = \{ \nu _ { 1 } , \nu _ { 2 , } , \ldots , , \nu _ { n } \}$ 来降低某一异常点对算法性能的影响。在几何形态的趋势特征值计算中，先找出几何形态上升或下降趋势区间内$V = \{ \nu _ { 1 } , \nu _ { 2 , } , \ldots , , \nu _ { n } \}$ 的最大值 $V = \{ \nu _ { 1 } , \nu _ { 2 , } , \ldots , , \nu _ { n } \}$ ，然后求出此区间内$V = \{ \nu _ { 1 } , \nu _ { 2 , } , \ldots , , \nu _ { n } \}$ 的均值 $V = \{ \nu _ { 1 } , \nu _ { 2 , } , \ldots , , , \nu _ { n } \}$ ，最后把 $V = \{ \nu _ { 1 } , \nu _ { 2 , } , \ldots , , , \nu _ { n } \}$ （204与 $V = \{ \nu _ { 1 } , \nu _ { 2 , } , \ldots , , \nu _ { n } \}$ 的均值作为几何形态的趋势特征值，这样运算的目的也是为了消减异常点对算法性能的影响，经过两次运算，消减了异常点对算法性能的影响，提升了R波检测的准确率。

与普通动态自适应阈值法不同，本文算法在确定了几何形态后，只需要设置一个可以再次过滤噪声的阈值即可，目的是为了减少不必要的几何形态判别提高算法的效率，而不需要在进行R波检测时再动态的改变阈值。然后由相邻且连续的三个几何形态组成一个群组，通过群组中几何形态的特征值进行R波检测。算法在确定R波位置的思想上与医生从视觉角度直观的从心电图中对R波进行定位一致。现实生活中医生通过心电图可以直观的找出幅值最大的波形，然后通过判断此波形的幅值是否高于其前后两个相邻波形的幅值就可以确定R波的位置。本文提出的算法中由连续三个几何形态组成一个群组，通过群组中几何形态的特征值

进行R波检测正是运用此思想，以群组中三个几何形态的特征值来替代心电图中直观的幅值，如果位于群组中间的几何形态特征值同时大于其前后两个几何形态的特征值则可以确定中间的几何形态为候选R波。算法进行R波检测时不需要每次动态的改变阈值来提高检测的准确率，降低了算法的复杂度，提高了自适应性。同时算法运用医生直观检测R波的思想以群组中几何形态的特征值代替实际幅值来检测R波而不是以心电信号中的某一点对R波进行检测，对异常波形也可以做到有效检测，因此本文算法具有普适性。算法描述如下所示：

算法 GMGC_Ralgorithm  
Input: 心电信号集合 $V = \{ \nu _ { 1 } , \nu _ { 2 , } , \ldots , , \nu _ { n } \}$   
Output: R 波位置的集合R  
1. while $V \neq \emptyset$ ， $V ^ { ' }  V ^ { ' } \cup | V _ { i } |$ ，end  
2. while $V ^ { ' } \neq \emptyset$ ， $\Delta \mathbf { y } = y ( x + \Delta x ) - y ( x ) ~ .$ $U \gets U \cup \Delta \mathbf { y }$ ，end  
3. while $U \neq \emptyset$ if $U _ { i } < 0 , U _ { i + 1 } > 0$ （204号if $U _ { i } > 0 , U _ { i + 1 } < 0$ if $U _ { i } < 0 , U _ { i + 1 } > 0$ （204号$D  D \cup \{ \mathrm { G } _ { s } , ~ \mathrm { G } _ { p } , ~ \mathrm { G } _ { e } \}$ ，end  
4. while $D \neq \emptyset$ ，确定几何形态 $C _ { i }$ ， $C \gets C \cup C _ { i }$ ，设置 ${ \mathrm { T } } _ { n }$ ，end  
5. （ $\begin{array} { r l } & { \mathrm { w h i l e } V \not = \emptyset \ , k _ { 1 } = V _ { \mathrm { i } + 1 } ^ { ' } - V _ { i } ^ { ' } , \qquad k _ { 2 } = ( V _ { \mathrm { i } + 2 } ^ { ' } - V _ { i } ^ { ' } ) / 2 } \\ & { k _ { 3 } = ( V _ { \mathrm { i } + 3 } ^ { ' } - V _ { i } ^ { ' } ) / 3 , k _ { 4 } = ( V _ { \mathrm { i } + 4 } ^ { ' } - V _ { i } ^ { ' } ) / 4 , } \\ & { k _ { i } = ( k _ { 1 } + k _ { 2 } + k _ { 3 } + k _ { 4 } ) / 4 , } \\ & { { S \gets S \cup K _ { i } } , \ \mathrm { e n d } } \end{array}$ ，  
6. while $C \neq \emptyset$ ，取出 $K _ { \mathrm { m a x } }$ ，计算 $K _ { a v g }$ ， $K _ { _ { u p } } = ( K _ { \operatorname* { m a x } } + K _ { _ { a \nu g } } ) / 2$ ，同理得 $k _ { d o w n }$ $, K _ { g s } = K _ { u p } * \Delta s + k _ { d o w n } * ( 1 - \Delta s ) ,$ （K←KUKgs，end7. while $C \neq \emptyset$ ，if $K _ { i } < K _ { i + 1 } , K _ { i + 2 } < K _ { i + 1 }$ ， （20 $Y \gets Y \cup C _ { i + 1 }$ ，end8. while $Y \neq \emptyset$ ，if $Y _ { i + 1 } > Y _ { i } / 2 , Y _ { i + 1 } > Y _ { i + 2 } / 2$ $R \gets R \cup Y _ { i + 1 }$ ，end9. return R

本文算法中输入的是心电信号（ECG）集合V，输出的是R波位置的集合R。首先把集合 $\mathrm { \Delta V }$ 中的所有数值进行取绝对值运算，把运算后的结果存入集合 $\boldsymbol { V } ^ { ' }$ 中。对集合 $\boldsymbol { V } ^ { \prime }$ 中所有值做一阶差分运算，把结果存入数组 $U$ 。然后依次判断 $U _ { i }$ 和$U _ { i + 1 }$ 的正负，确定几何形态的起始点 $\mathrm { G } _ { \mathnormal { s } }$ ，峰值点 $\mathrm { ~ G ~ } _ { p }$ ，结束点 $\mathrm { G } _ { e }$ 直至取完 $U$ 中的值。若 $U _ { i }$ 小于零且 $U _ { i + 1 }$ 大于零则该点为几何形态的起始点 $\mathrm { G } _ { s }$ ，若 $U _ { i }$ 大于零且 $U _ { i + 1 }$ 小于零则该点为几何形态峰值点 $\mathrm { ~ G ~ } _ { p }$ ，接着判断 $\boldsymbol { U } _ { i }$ 和 $U _ { _ { i + 1 } }$ ，若 $U _ { i }$ 小于零且 $U _ { i + 1 }$ 大于零则该点为这个几何形态的结束点 $\mathrm { G } _ { e }$ ，同时也是后继几何形态的起始点，将几何形态的 $\mathrm { G } _ { s }$ 、 $\mathrm { ~ G ~ } _ { p }$ 、 $\mathrm { G } _ { e }$ 存入数组D中。数组D中相邻且连续的起始、峰值、结束三点确定一个完整的几何形态 $C _ { i }$ ，把找出的几何形态存入数组C。设置一个最低有效阈值 ${ \mathrm { T } } _ { n }$ 即电压为 $0 . 0 1 \ \mathrm { m V }$ ，几何形态特征值为0.001，滤除数组C中无效几何形态，得到滤除无效几何形态后的数组C，同时把集合 $\boldsymbol { V } ^ { ' }$ 中对应无效几何形态的值也删除得到删除值后的集合 $\boldsymbol { V } ^ { ' }$ 。以一阶微分为基础，对集合 $\boldsymbol { V } ^ { ' }$ 中的每点求几何特征值 $K _ { d o t }$ ，即从集合 $\boldsymbol { V } ^ { ' }$ 中依次取每个点后连续三点的值并分别求出 $K _ { d o t }$ 值，然后取这四个 $K _ { d o t }$ 值的平均值 $k _ { i }$ 并将 $k _ { i }$ 存入数组S中，每个几何形态都与S中的一些几何特征值 $k _ { i }$ 相对应。

计算几何形态的特征值 $K _ { g s }$ ，从数组C中依次取出几何形态，并从数组S中取出与已取出的几何形态相对应的所有几何特征值 $k _ { i }$ ，然后从这些 $k _ { i }$ 中找出起始点至峰值点区间的几何特征最大值 $K _ { \operatorname* { m a x } }$ ，并计算出这区间中所有几何特征值 $k _ { i }$ 的均值 $K _ { a v g }$ ，最后计算几何形态的上升趋势特征值 $K _ { u p }$ 。按照上述方式计算得到下降趋势特征值 $k _ { d o w n }$ 。由 $K _ { \boldsymbol { u p } }$ 和 $k _ { d o w n }$ 算出几何形态的特征值 $K _ { g s }$ ，其中 $\Delta \mathrm { s }$ 为0.6，把 $K _ { g s }$ 值存入数组 $\mathrm { ~ \bf ~ K ~ }$ ，数组C与数组K下标一一对应。

选出候选R波，依次比对数组C中的三个连续几何形态的 $K _ { g s }$ 值，把每个几何形态对应的 $K _ { g s }$ 值记为 $K _ { i }$ 、 $K _ { _ { i + 1 } }$ 、 $K _ { i + 2 }$ ，如果 $K _ { i }$ 小于 $K _ { i + 1 }$ 且 $K _ { i + 1 }$ 大于 $K _ { i + 2 }$ 时，将 $C _ { i + 1 }$ 记为候选R波，并将此几何形态的所有信息存入数组 $Y$ 中，信息中包含几何形态的 $K _ { g s }$ 值。确定有效R波，依次比对数组 $Y$ 中的三个连续几何形态的 $K _ { g s }$ 值，把 $S E N = \frac { T P } { T P + F N } { \times } 1 0 0 \%$ 值记为$+ P = \frac { T P } { T P + F P } \times 1 0 0 \%$ 、 TP+FP+FN×100%、Y+，如果Y大于1/2的 $Y _ { \mathrm { i } }$ 且 $Y _ { i + 1 }$ 大于1/2 的 $Y _ { _ { i + 2 } }$ 时，则可以判定 $Y _ { i + 1 }$ 是有效R波，将其存入数组 $\mathtt { R }$ ，输出即为 $\mathtt { R }$ 波位置的集合。

本算法采用流水线式的处理模式，算法中的每一个步骤只处理其对应阶段的问题并得出中间结果，后续步骤依次连续处理得出最终结果，而且算法中的每个步骤主要是通过单层循序遍历来处理前一结果数据集。文章中算法采用数组集合存储数据，因此综合上述分析本文提出的GMGC_R算法具有较低的运算复杂度，其整体复杂度为O(n)。

# 3 实验结果

# 3.1实验流程

本文按图1所示流程进行实验验证算法。原始采集的心电信号用滤波器组进行预处理，然后对输入的ECG集合V进行R波检测。集合V中的所有值进行取绝对值运算，取绝对值运算后的集合中所有值均做一阶差分运算。通过运算结果找出几何形态的起始、峰值、结束点，然后通过相邻且连续的这三点确定几何形态。计算集合 $K _ { g s }$ 中每点几何特征值,并求出连续四点几何特征值的均值并存入数组S。从S取出起始点至峰值点区间的几何特征最大值，且计算出这区间中几何特征的均值，然后计算几何形态的上升趋势特征值。同理，计算得到下降趋势特征值，由公式计算几何形态

特征值 $K _ { g s }$ 。比较连续三个几何形态特征值找出候选R波，通过确定有效R波的操作最终确定R波位置集合。

![](images/79721773e0e141d7b44c49907297926c477f49b3b6d30fd766b7f4cfb249399c.jpg)  
图1实验流程  
Fig.1Experimental flow chart

# 3.2结果与讨论

心电信号检测算法的性能需要权威的心电检测标准来对其进行验证，新的算法只有经过权威心电数据库的验证后才能够得到人们的认可。通常用MIT-BIH数据库对提出的检测算法进行验证。MIT-BIH库记录了48个病例,每个病例数据长30分钟，总计约有116000多个心拍，其中既有正常心拍也有异常心拍，可以对R波检测算法进行有效的验证[22]。

本文所有实验都在相同实验环境下进行，其中CPU 为$\mathrm { I n t e l ^ { \oplus } C o r e ^ { T M } i 7 - 7 7 0 0 @ 3 . 6 0 ~ G H z }$ 内存为16GB，操作系统为64位Windows10。在MATLABR2015b中用滤波器组对心电数据进行预处理，然后用GMGC_R算法进行R波检测。MIT心拍定位标注包括N(1)、L(2)、R(3)、a(4)、V(5)、F(6)、J(7)、A(8)、S(9)、E(10)、j(11)、/(12)、Q(13)、[(16)、!(31)、e(34)、$\mathbf { n } ( 3 5 )$ 、f(38)，检测结果如表1所示。表1中的检测指标有四项，错检率记为DER，灵敏度记为SEN，精确率记为 $+ \mathrm { P }$ ，准确率记为Acc，公式如下所示：

$$
D E R = \frac { F P + F N } { T P } \times 1 0 0 \%
$$

$$
S E N = \frac { T P } { T P + F N } { \times } 1 0 0 \%
$$

$$
+ P = \frac { T P } { T P + F P } \times 1 0 0 \%
$$

$$
A c c = \frac { T P } { T P + F P + F N } { \times } 1 0 0 \%
$$

表1MIT-BIH心率失常数据库 $\mathtt { R }$ 波的检测部分结果统计

Table1Statistical results ofR wave detection in MIT-BIHarrhythmia database   

<html><body><table><tr><td colspan="5">database</td></tr><tr><td>FileName</td><td>DER</td><td>SEN</td><td>+P</td><td>Acc</td></tr><tr><td>100</td><td>0</td><td>100.00%</td><td>100.00%</td><td>100.00%</td></tr><tr><td>101</td><td>0.59%</td><td>99.63%</td><td>99.79%</td><td>99.41%</td></tr><tr><td>102</td><td>0.74%</td><td>99.36%</td><td>99.91%</td><td>99.27%</td></tr><tr><td>103</td><td>0</td><td>100.00%</td><td>100.00%</td><td>100.00%</td></tr><tr><td>106</td><td>0.25%</td><td>99.85%</td><td>99.90%</td><td>99.75%</td></tr><tr><td>107</td><td>0.23%</td><td>99.86%</td><td>99.91%</td><td>99.77%</td></tr><tr><td>109</td><td>0</td><td>100.00%</td><td>100.00%</td><td>100.00%</td></tr><tr><td>113</td><td>0</td><td>100.00%</td><td>100.00%</td><td>100.00%</td></tr><tr><td>114</td><td>0.05%</td><td>99.95%</td><td>100.00%</td><td>99.95%</td></tr><tr><td>117</td><td>0</td><td>100%</td><td>100.00%</td><td>100.00%</td></tr><tr><td>119</td><td>0.05%</td><td>100.00%</td><td>99.95%</td><td>99.95%</td></tr><tr><td>124</td><td>0.12%</td><td>100.00%</td><td>99.88%</td><td>99.88%</td></tr><tr><td>202</td><td>0.14%</td><td>99.86%</td><td>100.00%</td><td>99.86%</td></tr><tr><td>205</td><td>0.15%</td><td>99.85%</td><td>100.00%</td><td>99.85%</td></tr><tr><td>207</td><td>14.92%</td><td>87.32%</td><td>99.61%</td><td>87.02%</td></tr><tr><td>212</td><td>0.25%</td><td>100.00%</td><td>99.75%</td><td>99.75%</td></tr><tr><td>213</td><td>0.18%</td><td>100.00%</td><td>99.82%</td><td>99.82%</td></tr><tr><td>217</td><td>0.41%</td><td>99.82%</td><td>99.77%</td><td>99.59%</td></tr><tr><td>220</td><td>0</td><td>100.00%</td><td>100.00%</td><td>100.00%</td></tr><tr><td>231</td><td>0</td><td>100.00%</td><td>100.00%</td><td>100.00%</td></tr><tr><td>232</td><td>0.06%</td><td>100.00%</td><td>99.94%</td><td>99.94%</td></tr><tr><td>Total avg</td><td>1.07%</td><td>99.38%</td><td>99.61%</td><td>98.99%</td></tr></table></body></html>

本文用四个指标对算法性能进行衡量，由表1中可以看出算法的错检率为 $1 . 0 7 \%$ ，灵敏度为 $9 9 . 3 8 \%$ ，精确率为$9 9 . 6 1 \%$ ，准确率为 $9 8 . 9 9 \%$ 。在实验结果中出现了207号文件灵敏度为 $8 7 . 3 2 \%$ ，准确率为 $8 7 . 0 2 \%$ 的现象，主要原因是这类心电信号自身带有较强的噪声，经过滤波器组滤波后，没有彻底滤除噪声。其中部分心电信号R波检测的灵敏度、精确率、准确率为 $100 \%$ ，主要原因是这类ECG信号自身携带的噪声较少，前期滤波处理彻底滤除了噪声，如100号、103号和109号等。通过表1中实验结果可以看出，除了207号文件因噪声过多造成实验结果不理想外，该算法每一个文件的灵敏度为 $9 6 . 3 6 \%$ 以上，精确率为 $9 5 . 3 0 \%$ 以上，准确率为$9 4 . 4 3 \%$ 以上。所有文件的错检率为 $1 . 0 7 \%$ ，灵敏度为 $9 9 . 3 8 \%$ ，精确率为 $9 9 . 6 1 \%$ ，准确率为 $9 8 . 9 9 \%$ 。通过每一个文件各项指标的结果和总体文件的检测结果可以看出本文算法不但能够准确检测出正常波形的R波，对异常波形的R

波检测也具有较好的效果，说明该算法具有较高的普适性。将本文R波检测算法的实验结果和文献中的检测算法结果进行对比，不同算法实验结果对比如表2所示。

表2算法结果对比表  
Table 2Algorithm result comparison table   

<html><body><table><tr><td>算法</td><td>SEN</td><td>+P</td><td>Acc</td></tr><tr><td>文献[8]</td><td>99.39%</td><td>99.49%</td><td>98.89%</td></tr><tr><td>文献[12]</td><td>98.46%</td><td>98.62%</td><td>97.12%</td></tr><tr><td>文献[13]</td><td>98.68%</td><td>97.24%</td><td>96.03%</td></tr><tr><td>文献[16]</td><td>96.28%</td><td>99.71%</td><td>97.65%</td></tr><tr><td>文献[17]</td><td>98.89%</td><td>99.40%</td><td>98.37%</td></tr><tr><td>This paper</td><td>99.38%</td><td>99.61%</td><td>98.99%</td></tr></table></body></html>

从表2中可以看出与其他文献中提出的R波检测算法相比，本文算法具有较好的灵敏度、精确率和准确率。本文算法核心部分是以整体与局部兼顾的信号处理方式计算几何形态特征值，算法处理信号时兼顾整体与局部的思想，既可以规避因某一点几何特征值偏大对实验结果造成影响又具有滤波功能。兼顾整体与局部的运算消减了异常点对算法性能的影响，提升了R波检测的准确率。算法的另一创新点为用几何形态群组特征值确定R波，通过比对群组中三个几何形态特征值检测出R波，极大的提高了本算法的灵敏度和精确率。综合以上分析，本文提出的GMGC_R算法在灵敏度、精确率、准确率、普适性方面有明显的优势而且运算复杂度低，适用于各种心电信号中的R波检测。

# 4 结束语

本文提出了基于几何形态群组特征的R波检测算法，首先采用滤波器组对心电信号进行预处理为准确定位R波奠定了基础。然后在确定几何形态特征值的运算中兼顾了整体与局部信号的处理，不但降低了异常信号点对几何形态特征值计算的影响而且可以对心电信号再次去噪，最后用群组中几何形态特征值对波形进行检测。用MIT-BIH心律失常数据库对算法进行了验证，并与其他的算法实验结果做了对比，结果表明本文提出的算法有较高的灵敏度、精确率、准确率，而且具有普适性。

# 参考文献：

[1]Raj S,Ray K C.Application of variational mode decomposition and ABCoptimized DAG-SVM in arrhythmia analysis [C]//Procof International Symposium on Embedded Computing and System Design. 2017: 1-5.   
[2]El-Saadawy H, Tantawi M,Shedeed H A,et al.Electrocardiogram (ECG）heart disease diagnosis using PNN，SVM and Softmax regression classifiers [C] //Proc of the 8th International Conference on Intelligent Computing and Information Systems.2O17:106-110.   
[3]Merah M,Abdelmalik T A,Larbi B H.R-peaks detection based on stationary wavelet transform.[J].Computer Methods & Programs in Biomedicine,2015,121(3):149-160.   
[4]Goodfellow J,Escalona OJ,Kodoth V,et al.Denoising and automated R-peak detection in the ECG using discrete wavelet transform [C]/Proc of Computing in Cardiology Conference.IEEE,2017.   
[5]Razavi SR,Mohammadi MHD.R-peak detection inelectrocardiogram signals using continuous wavelet transform [C]. International Journal Bioautomation.2017,21(2):165-178.   
[6]Ma Yurun,Li Tongqing，Ma Yide,etal.Novel real-time fpga-based R-wave detection using lifting wavelet [J].Circuits Systems & Signal Processing,2016,35(1): 281-299.   
[7]Zhang Yue,Wang Zhao. Research on intelligent algorithm for detecting ECGR waves [C]//Proc of International Conference on Electronics Information and Emergency Communication. 2015:47-50.   
[8]Qin Qin,Li Jianqing,Yue Yinggao,etal.An adaptive and time-efficient ECG R-peak detection algorithm [J]. Journal of Healthcare Engineering, 2017(1): 1-14.   
[9]Sabut S,Sahoo S,Biswal P,et al.De-noising of ECG Signal and QRS detection using Hilbert transform and adaptive thresholding [J]. Procedia Technology,2016,25:68-75.   
[10] Chen Guodong,Wang Xuzhi,Wan Wanggen.An ECG R-wave detection algorithm based on adaptive threshold [C]//Proc of International Conference on Smart and Sustainable City and Big Data.2015:550-566.   
[11] Poungponsri S，Yu X H.An adaptive filtering approachfor electrocardiogram (ECG) signal noise reduction using neural networks [J].Neurocomputing,2013,117(87): 206-213.   
[12] Diker A,Avci E,Gedikpinar M.Determination of R-peaks in ECG signal using Hilbert transform and Pan-Tompkins algorithms [C]/Proc of the 25th Signal Processing and Communications Applications Conference.2017:1-4.   
[13] Chouakri S A,Bereksi-Reguig F,Taleb-Ahmed A.QRS complex detection based on multi wavelet packet decomposition [J]. Applied Mathematics & Computation,2011,217(23): 9508-9525.   
[14] Xia Yong，Han Junze，Wang Kuanquan.Quick detection of QRS complexes and R-waves using a wavelet transform and $\mathrm { ~ K ~ }$ -means clustering [J].Biomed Mater Eng,2015,1(s1):1059-65.   
[15] Park J S,Lee S W,Park U.R peak detection method using wavelet transform and modified shannon energy envelope[J]. Journal of Healthcare Engineering,2017,2017(46):1-14.   
[16] Rodriguez R，Mexicano A，Bila J,etal.Feature extraction of electrocardiogram signals by applying adaptive threshold and principal component analysis [J]. Journal of Applied Research & Technology, 2015,13(2): 261-269.   
[17] Ravanshad N,Rezaee-Dehsorkh H,LotfiR,etal.A level-crossing based QRS-detectionalgorithm for wearable ECG sensors [J].IEEEJBiomed Health Inform,2014,18(1): 183-192.   
[18] Yazdani S,Vesin JM.Adaptive mathematical morphology for QRS fiducial points detectionin the ECG [C]//Computing in Cardiology. 2014: 725-728.   
[19] Bouaziz F,Boutana D,Benidir M.Automatic detection method of R-wavepositionsinelectrocardiographicsignals[C]//Procof International Conference on Microelectronics.2013:1-4.   
[20] Ranjushree P.Comparison of the design of FIR and IIR filters for a given specification and removal of phase distortion from IIR filters [C]/Proc of International Conference on Advances in Computing, Communication and Control. 2O17: 1-3.   
[21]宗永胜，胡晓辉，张荣光．一种自适应双阈值中值滤波方法[J].小 型微型计算机系统，2017，38(7):1642-1647.(Zong Yongsheng，Hu Xiaohui,Zhang Rongguang.An adaptive dual threshold median filtering method [J].Journal of Chinese Computer Systems,2O17,38(7): 1642-1647. )   
[22] Rajankar S O,Bhanushali R K,Talbar S N.A wavelet-based progressive ECG compression using modified SPIHT [J]. International Journal of Biomedical Engineering & Technology,2016,22(3): 21.