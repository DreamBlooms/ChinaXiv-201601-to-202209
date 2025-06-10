# 一种新的基于H.264/AVC的可逆鲁棒隐写方法

刘舒扬1，陈亮²

(1．兰州大学，兰州 730000;2．国家计算机网络应急技术处理协调中心，北京 100029)

摘要：提出了一种新的基于H。264/AVC 的可逆鲁棒视频隐写方法。该方法首先利用（t，n）门限秘密共享技术将需要嵌入的秘密信息用多项式分发获得子秘密，再利用BCH码对子秘密进行编码，然后通过H。264的预测模式选择嵌入位置，最后将编码后的子秘密嵌入到视频的各个帧中。提取时，利用视频中t个编码后的子秘密恢复秘密信息。实验结果标明，该方法在提取秘密信息时能完全恢复原视频，具有较强的比特错、帧错鲁棒性，在随机丢帧率小于等于 $1 5 \%$ 的情况下能完全恢复秘密信息，能效控制帧内失真漂移，视觉效果良好。

关键词：H；264/AVC；可逆隐写；鲁棒性；帧内失真漂移 中图分类号：TP309.2 doi: 10.3969/j.issn.1001-3695.2017.11.0999

New robust reversible steganography method in H. 264 /AVC

Liu Shuyang1, Chen Liang² (1.Lanzhou University，Lanzhou 7300，China；2. National Computer Network Emergency Response Technical Team/Coordination Centerof China,Beijing 10o029,China)

Abstract: Thispaper proposedanewreversiblerobust steganography method in H.264/AVC.It firstdistributed theembedded secretdata byaspecific polynomial andobtainaseriesofsub-secrets.Then itused the BCHcode to encode each groupof the sub-secretsand embed theencoded sub-secrets into each frameofthe video with prediction mode.And itrecovered thehidden data byusing the encodedtsub-secrets of the video frames.Theexperimentresults shown that the method canrecover the originalvideocompletelyandhasthehighbiterrorandframe errorrobustness.Whentherandomframerate islessthanorequal to $1 5 \%$ ,the methodcanrecoverthe secretdata completely.Inaddition,the methodcan avoid intra-frame distortiondriftand has better visual concealment.

Key Words: Key Words: H.264/AVC; reversible steganography; robust ; intra-frame distortion drift

# 0 引言

视频隐写是将秘密信息隐藏于视频中，非授权者无法感知其传递行为及内容的一种技术。H.264/AVC (H.264)视频压缩标准因具有压缩率高、差错恢复能力强、适用范围广等优点已成为目前最流行的视频压缩标准,并在多个领域得到了迅速部署与广泛普及[]。

隐藏了秘密信息的H.264视频在网络上传输时，因遭到恶劣的物理环境(无意攻击)、网络攻击(有意攻击)等而产生比特错、丢帧、丢包等，致视频损毁秘密信息无法恢复。2005年学术界已经开始了H.264视频隐写的研究，但研究的文献大多数选择在变换域内,非常依赖于DCT系数[2-]，针对视频隐写鲁棒性的算法研究依然很少[7]。Esen 等人[8]利用禁止区和选择嵌入的方法实现强鲁棒性视频隐写,Liu等人[4-针对H.264视频利用BCH码来实现恢复比特错,但这些算法均不能实现丢帧、丢包等情况

下秘密信息的恢复。

通常,秘密信息在嵌入和提取过程中会在一定范围内修改原始载体,这对那些如医疗、图像及法律证据等不容忍永久失真的载体来说是不可接受的。可逆隐写的出现可以解决这一问题。通常，把秘密信息在提取后能完全恢复原载体的隐写方法叫可逆隐写。目前,对于可逆隐写方法的研究大都集中在可逆性方面[10],基于H.264 视频可逆隐写算法的研究还不是很多[12]。文献[10,11]利用预测模式选择嵌入块实现信息隐藏，文献[10]只考虑算法的可逆性,文献[11]在文献[10]的基础上解决了比特位出错问题,提高了鲁棒性,但不能解决由于丢包、丢帧等引起的帧错、帧丢失等问题。文献[12]利用秘密共享实现鲁棒性,但是算法不能解决比特位出错、丢失等问题。文献[13]利用直方图实现了基于3DH.264/AVC的可逆视频隐写。

本文针对H.264视频,提出了一种新的可逆鲁棒视频隐写方法。该方法在信息提取完全恢复原视频的同时，可以恢复由于恶劣物理环境、网络攻击等引起的比特丢失、比特错、帧丢失及帧错误等,有并能效控制帧内失真漂移,视觉效果良好。

# 1 基本概念

# 1.1帧内失真漂移预防

H.264视频压缩编码标准中 $4 \times 4$ 块的帧内预测模式有 9种， $1 6 \times 1 6$ 块的帧内预测模式有4种,分别用0\~8和0\~3表示。在帧内预测时,预测块是依据已编码块和待编码的当前块（当前块）来计算的。如图1所示,假定当前块为，则 $B _ { i , j }$ 的预测值是由其已编码的左邻块 $B _ { i , j - 1 }$ 、左上邻块 $B _ { i - 1 , j - 1 }$ 、上邻块 $B _ { i - 1 , j }$ 及右上邻块 $B _ { i - 1 , j + 1 }$ 块中灰色部分，根据当前块所采用的帧内预测模式计算出来。若在图中灰色部分嵌入秘密信息,则因嵌入所导致的误差必然会通过上述计算传递到当前块中,造成帧内失真漂移。若对当前块进行预测时，不采用嵌入秘密信息的邻块边缘像素,帧内失真漂移就能预防。

![](images/941910d98874b0b106a3a7dce92272a5c11111e5fc9d2b62e2c2319db1b13872.jpg)  
图1帧内预测块及其邻块  
图2当前块及三个条件

为使用方便,给出如下定义：

条件1 右邻块 $\in \{ 0 , 3 , 7 \} _ { 4 \times 4 } \cup \{ 0 \} _ { 1 6 \times 1 6 }$

条件左下邻块 $\in \left\{ 0 , 1 , 2 , 4 , 5 , 6 , 8 \right\} _ { 4 \times 4 } \cup \left\{ 0 , 1 , 2 , 3 \right\} _ { 1 6 \times 1 6 }$ 和下邻块 $\in \{ 0 , 8 \} _ { 4 \times 4 } \cup \{ 1 \} _ { 1 6 \times 1 6 }$ 。

条件3 右下邻块 $\in \left\{ 0 , 1 , 2 , 3 , 7 , 8 \right\} _ { 4 \times 4 } \cup \left\{ 0 , 1 , 2 , 3 \right\} _ { 1 6 \times 1 6 }$ 。  
当前块及三个条件如图2所示。

<html><body><table><tr><td></td><td>当前块</td><td>预测模式： 4×4:0,3,7 16×16:0</td></tr><tr><td>预测模式： 4×4:0,1,2,4,5,6,8 16×16:0,1,2,3</td><td>预测模式： 4×4:1, 8 16×16:1</td><td>预测模式： 4×4:0,1,2,3,7,8 16×16:0,1,2,3</td></tr></table></body></html>

若当前块满足条件1,则在该块内嵌入信息所导致的误差不会通过最右边一列传递到其右邻块中。

若当前块满足条件2,则在该块内嵌入信息所导致的误差不会通过最下边一行传递到其左下与下邻块中。

若当前块满足条件3,则在该块内嵌入信息所导致的误差不会通过最右下角的子块传递到其右下邻块。

因此,利用条件1、2和3可以控制帧内失真漂移。

# 1.2 BCH码

若 $\mathbf { \eta } _ { \mathrm { ~ n ~ } }$ 为码长,k为信息位， $\mathrm { \mathbf { B C H } ( n , ~ k , ~ t ) }$ 能纠正t个错误，则BCH $( \mathrm { n , k , t } )$ 码的校验矩阵为

$$
H = \left[ \begin{array} { c c c c c } { 1 } & { \alpha } & { \alpha ^ { 2 } } & { \cdots } & { \alpha ^ { n - 1 } } \\ { 1 } & { \alpha ^ { 3 } } & { ( \alpha ^ { 3 } ) ^ { 2 } } & { \cdots } & { \left( \alpha ^ { n - 1 } \right) ^ { 2 } } \\ { \vdots } & { \vdots } & { \vdots } & { \ddots } & { \vdots } \\ { 1 } & { \alpha ^ { 2 t - 1 } ( \alpha ^ { 2 t - 1 } ) ^ { 2 } } & { \cdots } & { \left( \alpha ^ { n - 1 } \right) ^ { 2 } } \end{array} \right]
$$

其中： $\alpha$ 是 $G F ( 2 ^ { m } )$ 上的本原元。若原始二进制数据流为$Q = \{ q _ { 0 } , q _ { 1 } , . . . , q _ { n - 1 } \}$ ，要嵌入的秘密信息的数据流为$V = \{ \nu _ { 0 } , \nu _ { 1 } , . . . , \nu _ { n - 1 } \}$ ，则

$$
V = Q H ^ { T }
$$

若经传输后接收到的码流数据为 $S = \{ s _ { 0 } , s _ { 1 } , . . . , s _ { n - 1 } \}$ ，则 $\mathrm { \Delta V }$ 和 S 可分别表示为 $\operatorname { V } ( \mathbf { X } ) = \nu _ { 0 } + \nu _ { 1 } x + \nu _ { 2 } x ^ { 2 } + \nu _ { 3 } x ^ { 3 } + \cdots \nu _ { n - 1 } x ^ { n - 1 }$ 与$S ( X ) = s _ { 0 } + s _ { 1 } x + s _ { 2 } x ^ { 2 } + s _ { 3 } x ^ { 3 } + \cdots s _ { n - 1 } x ^ { n - 1 } , \mathrm { S }$ 和 $\mathrm { \Delta V }$ 的差别E可表示为

$$
S = V + E
$$

由式（2）和（3）可得

$$
\boldsymbol { Y } = ( \boldsymbol { S } - \boldsymbol { H } ) \boldsymbol { H } ^ { T } = \boldsymbol { E } \boldsymbol { H } ^ { T }
$$

则嵌入秘密信息的S可由式(3)计算,秘密信息可由式(2)来提取.

# 1.3秘密共享

秘密共享是一种将秘密分发给参与者,至少有若干个参与者才能将秘密恢复的技术。1979年Shamir[提出了基于拉格朗日插值的门限秘密共享方法。

假设要分割的秘密信息为 $a _ { 0 } = k$ ,构造t-1 次方多项式$p _ { t - 1 } ( x ) = a _ { 0 } + a _ { 1 } x + a _ { 2 } x ^ { 2 } + \cdots a _ { t - 1 } x ^ { t - 1 } { \bmod { p } }$ 其中，大素数$> 0 , \ a _ { i } \in Z _ { p } ( i = 1 , . . . , n )$ 。设有 $n ( n > p )$ 个参与者,计算 t-1次方多项式在 $x _ { i }$ 处的值 $y _ { i }$ ,将其作为子秘密$( x _ { i } , y _ { i } ) ( i = 1 , . . . , n )$ 分发给 $\mathfrak { n }$ 个参与者。若多项式 $p _ { i - 1 } ( x _ { i } )$ 的t个值为 $( x _ { i } , y _ { i } ) ( i { = } 1 , . . . , t )$ ,则由Lagrangre 插值公式可得

$$
p _ { t - 1 } ( x ) = \sum _ { i = 1 } ^ { t } y _ { i } \prod _ { j = 1 , j \ne i } ^ { t } \frac { x - x _ { j } } { x _ { i } - x _ { j } }
$$

则常数项为

$$
k = p _ { t - 1 } ( 0 ) = \sum _ { i = 1 } ^ { t } { y _ { i } \prod _ { j = 1 , j \ne i } ^ { t } { \frac { - x _ { j } } { x _ { i } - x _ { j } } } } = \sum _ { i = 1 } ^ { t } { b _ { i } y _ { i } } ( b _ { i } = \prod _ { j = 1 , j \ne i } ^ { t } { \frac { - x _ { j } } { x _ { i } - x _ { j } } } )
$$

# 2 算法嵌入与提取过程

# 2.1嵌入过程

由于 $1 6 \times 1 6$ 块的视频内容相对平缓,嵌入秘密信息容易引起视觉失真，所以本算法选用量化后的 $4 { \times } 4$ 块DCT系数来嵌入信息。图3给出了算法嵌入部分的操作流程。首先对H.264原始视频进行熵解码,得到解码后的DCT系数和 $4 \times 4$ 的帧内亮度预测模式。根据DCT系数中DC 绝对值及自定义参数threshold,选取合适的 $4 \times 4$ 块，根据当前块是否同时满足条件1、2 和3来选择嵌入块。对已BCH 编码的子秘密进行嵌入操作,最后对所有的已嵌入已编码信息的DCT系数重新熵编码得到嵌入秘密信息的目标视频。

![](images/d4b467ce39273332d51e9bb51c0b552c50808cfce55648f87be2092df13cb0d0.jpg)  
图3嵌入操作流程

以正整数N与系数 $\widetilde { Y } _ { i j }$ ? $\scriptstyle \mathrm { i , j = 0 , } 1 , 2 , 3$ ）为例来具体描述算法嵌入过程，步骤如下：

a）按秘密共享分发子秘密。b）对子秘密进行BCH编码。c）根据直流系数的绝对值和自定义参数threshold的值选择可嵌入块（因为有非零系数的块进行调制时引起的失真效果不明显,所以选择具有非零系数及 $\tilde { Y } _ { 0 0 } \geq 0$ 的块作为备选嵌入块)。d)根据c）中选择可嵌入块是否同时满足条件1、2和3选择嵌入块。依据调制方法把经过BCH编码的子秘密嵌入到满足条件的DCT系数中。

e）重新对DCT系数进行熵编码得到H.264目标视频。

调制方法：

如果 $\left| \widetilde { Y } _ { i j } \right| = N + 1$ 或 $\left| \widetilde { Y } _ { i j } \right| \neq N$ K $\widetilde { Y } _ { _ { i j } }$ 按式 (6)进行修改。  
如果嵌入的比特是1且 $\left| \widetilde { Y } _ { i j } \right| = N , \widetilde { Y } _ { i j }$ 式(7)进行修改。  
如果嵌入的比特是0且 $\left| \widetilde { Y } _ { i j } \right| = N , \widetilde { Y } _ { i j }$ 不做修改。

$$
\begin{array} { r } { \tilde { \mathrm { Y } } _ { \mathrm { i , j } } = \left\{ \begin{array} { l l } { \tilde { \mathrm { Y } } _ { \mathrm { i , j } } + 1 , } & { \mathrm { i f } \tilde { \mathrm { Y } } _ { \mathrm { i , j } } \geq 0 \mathrm { a n d } \left| \tilde { \mathrm { Y } } _ { \mathrm { i , j } } \right| = \mathrm { N } + 1 , } \\ { \tilde { \mathrm { Y } } _ { \mathrm { i , j } } - 1 , } & { \mathrm { i f } \tilde { \mathrm { Y } } _ { \mathrm { i , j } } < 0 \mathrm { a n d } \left| \tilde { \mathrm { Y } } _ { \mathrm { i , j } } \right| = \mathrm { N } + 1 , } \\ { \tilde { \mathrm { Y } } _ { \mathrm { i , j } } , } & { \mathrm { i f } \left| \tilde { \mathrm { Y } } _ { \mathrm { i j } } \right| \neq \mathrm { N } . } \end{array} \right. } \end{array}
$$

$$
\tilde { \mathrm { Y } } _ { \mathrm { i , j } } = \left\{ \begin{array} { l l } { \tilde { \mathrm { Y } } _ { \mathrm { i , j } } + 1 , ~ \mathrm { i f } ~ \tilde { \mathrm { Y } } _ { \mathrm { i , j } } \geq 0 \mathrm { a n d } \left| \tilde { \mathrm { Y } } _ { \mathrm { i , j } } \right| = \mathrm { N } , } \\ { \tilde { \mathrm { Y } } _ { \mathrm { i , j } } - 1 , ~ \mathrm { i f } ~ \tilde { \mathrm { Y } } _ { \mathrm { i , j } } < 0 \mathrm { a n d } \left| \tilde { \mathrm { Y } } _ { \mathrm { i , j } } \right| = \mathrm { N } . } \end{array} \right.
$$

# 2.2提取过程

图4给出了算法提取的操作流程。首先对接收到的H.264视频进行熵解码操作,得到解码后DCT系数和 $4 \times 4$ 的帧内预测模式。根据DCT系数中DC绝对值、自定义阈值threshold以及邻块的预测模式是否同时满足条件1、2和3,选择已嵌入秘密信息的 $4 \times 4$ 块，并从其量化DCT系数中提取已编码的秘密信息 $\mathbf { M }$ 。

![](images/0d546351bb0b5c0141e645f6a38b6f5584cd2821bc4eef0ed02bac3be6109d48.jpg)  
图4提取操作流程

提取方法：

如果 $\left| \widetilde { Y } _ { i j } \right| = N + 2$ 或 $\left| \widetilde { Y } _ { i j } \right| \neq N + 2$ 或 $\left| \widetilde { Y } _ { i j } \right| \neq N + 1 , \widetilde { Y } _ { i j }$ 按式(8)进行修改。

如果 $\left| \widetilde { Y } _ { i j } \right| = N + 1$ ，提取比特位1且 $\widetilde { Y } _ { i j }$ 按式(9)进行修改。

如果 $\left| \widetilde { Y } _ { i j } \right| = N$ ,提取的比特位0且 $\widetilde { Y } _ { _ { i j } }$ 不做修改。

$$
\begin{array} { r l } & { \tilde { \mathrm {  ~ Y ~ } } _ { { \tilde { \mathrm { i } } } , j } = 1 , \mathrm { i f } \tilde { \mathrm {  ~ Y ~ } } _ { { \tilde { \mathrm { i } } } , j } \geq 0 \mathrm { a n d } \left| \tilde { \mathrm {  ~ Y ~ } } _ { { \tilde { \mathrm { i } } } , j } \right| = \mathrm { N } + 2 , } \\ & { \tilde { \mathrm {  ~ Y ~ } } _ { { \tilde { \mathrm { i } } } , j } = \left\{ \begin{array} { l l } { \tilde { \mathrm {  ~ Y ~ } } _ { { \tilde { \mathrm { i } } } , j } + 1 , } & { \mathrm { i f } \tilde { \mathrm {  ~ Y ~ } } _ { { \tilde { \mathrm { i } } } , j } < 0 \mathrm { a n d } \left| \tilde { \mathrm {  ~ Y ~ } } _ { { \tilde { \mathrm { i } } } , j } \right| = \mathrm { N } + 2 , } \\ { \tilde { \mathrm {  ~ Y ~ } } _ { { \tilde { \mathrm { i } } } , j } , } & { \mathrm { i f } \left| \tilde { \mathrm {  ~ Y ~ } } _ { { \tilde { \mathrm { i } } } , j } \right| \neq \mathrm { N } + 2 \mathrm { o r } \left| \tilde { \mathrm {  ~ Y ~ } } _ { { \tilde { \mathrm { i } } } , j } \right| \neq \mathrm { N } + 1 } \end{array} \right. . } \\ & { \tilde { \mathrm {  ~ Y ~ } } _ { { \tilde { \mathrm { i } } } , j } = \left\{ \begin{array} { l l } { \tilde { \mathrm {  ~ Y ~ } } _ { { \tilde { \mathrm { i } } } , j } - 1 , } & { \mathrm { i f } \tilde { \mathrm {  ~ Y ~ } } _ { { \tilde { \mathrm { i } } } , j } \geq 0 \mathrm { a n d } \left| \tilde { \mathrm {  ~ Y ~ } } _ { { \tilde { \mathrm { i } } } , j } \right| = \mathrm { N } + 1 , } \\ { \tilde { \mathrm {  ~ Y ~ } } _ { { \tilde { \mathrm { i } } } , j } + 1 , } & { \mathrm { i f } \tilde { \mathrm {  ~ Y ~ } } _ { { \tilde { \mathrm { i } } } , j } < 0 \mathrm { a n d } \left| \tilde { \mathrm {  ~ Y ~ } } _ { { \tilde { \mathrm { i } } } , j } \right| = \mathrm { N } + 1 . } \end{array} \right. } \end{array}
$$

提取信息 $\mathbf { M } ^ { \prime }$ 后,对其进行BCH解码和秘密共享处理即可得到秘密信息 $\mathbf { M }$ 。

# 3 实验分析

本方法在H.264标准编/解码软件 $\mathrm { J M } ~ 1 6 . 0$ 上进行了实现.每个实验视频以30 bps 编码 300 个帧,I帧编码间隔为15,量化参数为28,分辨率为 $1 7 6 \times 1 4 4$ 。实验视频序列为container、news、coastguard、mobile 等标准视频.其中,PSNR(peaksignalto noiseratio）峰值信噪比是由未编码的YUV视频文件与嵌入视频文件计算得到且比值为I、B与P帧的PSNR的平均值。原始视频是指秘密信息嵌入之前的H.264视频文件。丢帧率是所测试中丢失的帧数目占测试帧数目的之比；存活率是正确提取的嵌入比特数目与总嵌入比特数目之比。

表1给出了采用BCH(63,7,15)、(t,n）门限秘密共享为(3,8)时,实验视频在不同的丢帧率下嵌入秘密信息的恢复情况。由表可知，4个视频的平均信噪比为36.71dB,平均嵌入容量为7812bit,在随机丢帧率为 $5 \%$ 、 $10 \%$ 和 $1 5 \%$ 的情况下，嵌入秘密信息的存活率几乎达到 $100 \%$ ，可见算法具有较好的视觉质量、嵌入容量及较强的鲁棒性。在正常的网络丢包率（ $10 \%$ ）下，完全适用于秘密信息的安全传输。此外,可以通过调节秘密共享门限值来调整嵌入容量以满足所要嵌入秘密信息,还可以通过使用视频有无限多帧这一特点来满足所需嵌入的秘密信息。

表2为实验视频container在网络丢帧率为 $1 5 \%$ 时，不同的$\left( \mathrm { t , n } \right)$ 门限值的嵌入性能比较。由表2可知,当t保持不变，n值变大时,存活率变大；当n保持不变,t值变大时,存活率变小。这与秘密共享的理论分析是一致的。图5和6再次验证了这个结论。图5所示为t值不变n值变化时,不同丢帧率下秘密信息存活率的变化情况。图6为n值不变t值变化时，不同的丢帧率下秘密信息的存活率的变化情况。

图7\~11为不同网络丢帧率下,不同实验次数下的嵌入秘密信息的存活率变化情况。由图可知,在网络丢帧率不大于 $10 \%$ 的情况下，所有实验下的嵌入比特存活率都达到了 $100 \%$ 。

表1不同丢帧率的性能比较  

<html><body><table><tr><td rowspan="2">视频</td><td rowspan="2">PNS1 (dB)</td><td rowspan="2">嵌入容量 (bit)</td><td rowspan="2">比特增 加率/%</td><td>网络</td><td>存活率</td></tr><tr><td>丢帧</td><td>1%</td></tr><tr><td rowspan="3">container</td><td rowspan="3">36.57</td><td rowspan="3">7 560</td><td rowspan="3">0.025</td><td>率/% 5</td><td>100.00</td></tr><tr><td>10</td><td>100.00</td></tr><tr><td>15</td><td>100.00</td></tr><tr><td rowspan="4">news</td><td rowspan="2">37.08</td><td rowspan="4">8064</td><td rowspan="4"></td><td>20 5</td><td>92.31 100.00</td></tr><tr><td>10</td><td>100.00</td></tr><tr><td>0.025</td><td>92.86</td></tr><tr><td>15 20</td><td>100.00</td></tr><tr><td rowspan="3">mobile</td><td rowspan="3">34.93</td><td rowspan="3">8064</td><td rowspan="3">0.024</td><td></td><td>100.00</td></tr><tr><td>5 10</td><td>100.00</td></tr><tr><td>15</td><td>100.00</td></tr><tr><td rowspan="3">coastguard</td><td rowspan="3">38.26</td><td rowspan="3">7560</td><td rowspan="3">0.036</td><td>20</td><td>64.29</td></tr><tr><td>5 10</td><td>100.00 100.00</td></tr><tr><td></td><td></td></tr><tr><td rowspan="2"></td><td rowspan="2"></td><td rowspan="2"></td><td rowspan="2"></td><td>15</td><td>100.00</td></tr><tr><td>20</td><td></td></tr><tr><td></td><td></td><td></td><td></td><td>100.00</td></tr></table></body></html>

表2不同(t,n)值的性能比较  

<html><body><table><tr><td>(t,n)</td><td>嵌入容量 (bit)</td><td>PSNR1 (dB)</td><td>存活率/%</td></tr><tr><td>(2.8)</td><td>82</td><td>36.51</td><td>100.00</td></tr><tr><td>(3,8)</td><td>82</td><td>36.51</td><td>100.00</td></tr><tr><td>(4,8)</td><td>82</td><td>36.48</td><td>78.54</td></tr><tr><td>(3,4)</td><td>165</td><td>36.50</td><td>55.63</td></tr><tr><td>(3,16)</td><td>35</td><td>36.67</td><td>100.00</td></tr><tr><td>(3,32)</td><td>16</td><td>36.72</td><td>100.00</td></tr></table></body></html>

![](images/05e129093f180ff826fc5a107b1c159d109efea072ae2bf35df7fc5d536b6bcb.jpg)  
图6n值不变t值变化时的存活率

![](images/86331ccf595b1d2729aba722174f4669e17d9730fe99832ed151a65d53dc1d6f.jpg)  
图7丢帧率 $5 \%$ 时多次实验的存活率

![](images/f2929aa4b2f2fbcbadeb7bb8416f60cbc19774f3a94646a362a4d1ae190c03fa.jpg)  
图5t值不变 $\mathfrak { n }$ 值变化时的存活率

![](images/664f9548b42d5fb6dcf5876f7a5a8470a78aba1cd908162ce4fc50a2f3d025a4.jpg)  
图8丢帧率 $10 \%$ 时多次实验的存活率

![](images/80347742693b8e51310c935077edb0ee36cb074e22ba236b65a48f65d0fa9516.jpg)  
图9丢帧率 $1 5 \%$ 时多次实验的存活率

![](images/9c27f2f7de17ae8fb055010267ce0d9cbae9857b04fda2b119a1f619191f4ff8.jpg)  
图10丢帧率 $1 5 \%$ 时多次实验下的存活率

![](images/07c60a782457d2eb5d1f4b36cc67e1399309fea670e572255d3f278006aed495.jpg)  
图11丢帧率 $20 \%$ 时多次实验的存活率

图12\~14给出了News原视频,News嵌入视频及News提取信息后的视频帧。由图可以看出本算法具有较好的视觉效果。

![](images/6d4373935bc9038eb9a6b78d7e26a686c43c17c6b7e136bcb9faab8e2961981d.jpg)  
图12 原视频帧

![](images/9429094819e947000af17c9c0cf20db8a31e97111eba2fc44786473c2d850c99.jpg)  
图13嵌入视频帧

![](images/1f67fad68e82f863d3f2e9aa9abf9f582cb5afa6a0564cb4107c8671b33bfac7.jpg)  
图14提取后的视频帧

![](images/a8fe4dc734723dbc362b8495727af8b39bc9d464d9114bb3608b1a8788dcec5a.jpg)  
图15本算法与算法[对比

图15 以视频 NEWS 为例给出了本算法与算法[1的性能对比。由图可知,本算法的存活率达到 $100 \%$ 本算法明显优于算法[I].这是因为算法[I]失去了 BCH码的比特位纠错能力。

表3给出了本算法与算法[2.3]的性能对比。由表可知,在网络丢帧率为 $5 \%$ 、 $1 5 \%$ ， $20 \%$ ，的情况下，算法[2]、算法[3]及本算法的平均存活率分别为 $8 3 . 2 5 \%$ 、 $7 6 . 1 3 \%$ 、 $9 7 . 6 3 \%$ 。在网络丢帧率 $1 5 \%$ 的情况下,在正常网络传输的情况下，本文所提出的视频隐写算法能完全恢复秘密信息，且具有较高的鲁棒性。

表3本算法与其他算法的性能对比  

<html><body><table><tr><td rowspan="2">视频</td><td rowspan="2">网络丢帧率 （随机%）</td><td rowspan="2">算法[2]存</td><td rowspan="2">算法[]存</td><td rowspan="2">本算法存</td></tr><tr><td></td></tr><tr><td rowspan="2">container</td><td>15</td><td>活率/% 86.10</td><td>活率/% 83.27</td><td>活率/% 100.00</td></tr><tr><td>20</td><td>79.23</td><td>72.73</td><td></td></tr><tr><td rowspan="2">news</td><td>15</td><td>87.20</td><td>82.14</td><td>92.31</td></tr><tr><td>20</td><td>79.97</td><td>72.67</td><td>92.86</td></tr><tr><td rowspan="2">mobile</td><td>15</td><td>87.50</td><td></td><td>100.00</td></tr><tr><td>20</td><td>78.90</td><td>80.07</td><td>100.00</td></tr><tr><td rowspan="2">coastguard</td><td>15</td><td>87.42</td><td>72.30 76.75</td><td>94.29</td></tr><tr><td>20</td><td>79.68</td><td>69.12</td><td>100.00 100.00</td></tr></table></body></html>

# 4 结束语

本文提出了一种基于H.264的可逆鲁棒视频隐写方法.实现载有秘密信息的H.264视频在传输过程中遭到一种或多种有意或是无意的攻击导致视频损毁,依然可以在接收端恢复原始秘密信息,同时可以恢复原视频载体,可以应用于远程医疗、云计算、视频传输、可逆图像认证和二维向量地图等。由于秘密共享与BCH 码技术都是在嵌入前与提取后使用，所以算法具有较小的复杂度。若m1是原始秘密信息比特位的个数，m2是原始秘密信息的个数，则算法的嵌入与提取过程的复杂度都为$\mathrm { O } ( \mathrm { l o g m } 1 + \mathrm { m } 2 )$ ，能适应视频的实时性要求。

# 参考文献：

[1]毕厚杰．新一代视频压缩编码标准H.264//AVC[M].北京：人民邮电 出版社,2005:97-129.   
[2]Ma XJ,Li ZT,TuH,et al.A data hiding algorithm for H.264//AVC video streams without intraframe distortion drift [J]. Circuits and Systems for Video Technology,2010,20 (10):1320-1330.   
[3]MaXJ,Li ZT,LvyJ,et al.Data hiding inH.264//AVC streams with limited intra-frame distortion drift [C]//Proc of Computer network and Multimedia Technology. 2009:1-5.   
[4]Liu YX,Li Z T,Ma XJ,etal.A robust without intra-frame distortion drift data hiding algorithm based on H.264//AVC [J].Multimedia Tools& Applications,2014,72(1):613-636.   
[5]Liu S,Liu Y X,Feng C,et al.A reversible data hiding method based on HEVC without distortion drift [C]// Proc of International Conference on Intelligent Computing.2017: 613-624.   
[6]LiuY X,Liu SY, Zhao HG,et al.A data hiding method forH.265 without intra-frame distortion drift [C]// Proc of International Conference on Intelligent Computing,Intelligent Computing Methodologies.2017:642- 650.   
[7]Liu Y X,Li Z T,Ma XJ,et al.A robust data hiding algorithm for H. 264//AVC video streams [J]. Journal of Systems and Software,2013,86 (8): 2174-2183.   
[8]Esen E,Alatan AA.Robust video data hiding using forbidden zone data hiding and selective embedding [J].IEEE Trans on Circuits and Systems for Video Technology,2011,21(8):1130-1138.   
[9]ShamirA.How to share a secret[J].Communications of the ACM,1979,22 (11): 612-613.   
[10]Liu YX,MaXJ,Li ZT.A reversible data hiding scheme based on H. 264//AVCwithout distortion drift[J].Journal of Software,2012,7(5):1059- 1065.   
[11]Liu YX,JuLM,Hu MS,etal.A robust reversible data hiding scheme for H.264 without distortion drift [J].Neurocomputing,2015,151 (1):1053- 1062.   
[12]LiuYX,JuLM,HuMS,etal.A new data hiding method forH.264 based on secret sharing [J].Neurocomputing,2016,188:113-119.   
[13] Zhao J,Li ZT,Feng B.A novel two-dimensional histogram modification for reversible data embedding into stereo H.264 video [J].Multimedia Tools & Applications,2016,75 (10):5959-5980.