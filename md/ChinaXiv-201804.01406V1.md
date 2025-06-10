# 大规模MIMO系统中基于用户位置的导频分配

张进彦，金凤，尹礼欣，马东亚(重庆邮电大学 移动通信重庆市重点实验室，重庆 400065)

摘要：大规模多输入多输出（multiple input multiple output，MIMO）系统中因导频复用而存在的导频污染问题，成为其性能提高的瓶颈。针对此问题，提出一种基于用户位置的导频分配方案。该方案通过上行功率控制方法保证不同用户到各自小区基站的信号功率相同，并在功率控制情况下，根据干扰用户到本小区基站距离与到目标小区基站距离的比值来定义干扰用户对目标用户的导频污染强度，并给用户间导频污染强度较小的两个不同小区用户分配相同的导频。仿真结果表明，所提方案能够有效提高系统容量，减小用户间性能差距，较好地降低了用户间的导频污染。

关键词：大规模多输入多输出；导频污染；功率控制；用户位置；导频分配中图分类号：TN929.5 doi:10.3969/j.issn.1001-3695.2018.01.0012

Pilot allocation based on user location in massive MIMO systems

Zhang Jinyan, Jin Feng, Yin Lixin, Ma Dongya (Chongqing KeyLabofMobileCommunicationTechnology,Chongqing UniversityofPosts &Tlecommunications,Chongqing 400065, China)

Abstract:The problem of pilotcontamination caused bypilot multiplexing has becomea botleneck for its performance improvementi Massivemultipleinput mutipleoutput（MIMO）systems.To solvethis problem,weproposedapilotalocation scheme basedonuserlocation.Inthisscheme,the uplink power controlmethodensured thatsignal powerof diferentusers to thebase stationof theirowncellwereequal.Inthecaseofpowercontrol,wedefined thepilotcontamination intensityofthe interferingusers tothetargetuseras theratioofthedistance fromtheinterferingusertothebase stationofinterferenecell to thedistanceoftargetcell.weallcated thesamepilottotwousersofdifferentcellwithlesspilotcontamnationbetweenusers. The simulationresults showthatthe proposed scheme can effectively improve the systemcapacity,reduce the performance gap between users,and reduce the pilot contaminationbetween users.

Key words: Massive multiple input mutiple output; pilot contamination; power control; user location; pilot allocation

# 0 引言

近年来，随着移动互联网和物联网的爆发式增长，移动数据流量呈现出指数级的增长态势，当前正在使用的第四代移动通信系统其速率及系统容量已很难满足要求。因此，学术界和工业界已全面展开对第五代移动通信系统（5G）的研究[1-2]，大规模MIMO技术是提高5G传输速率和系统容量的关键技术之一。

理论研究表明，大规模MIMO技术由于在基站端配置大量天线，使得用户信道趋近于正交，蜂窝小区的频谱效率和能量效率都能得到大幅的提升[3]，当基站天线数量逐渐增加时，上下行传输中噪声和信道小尺度衰落对系统的性能影响都将逐步减小乃至消除。但考虑在实际的多小区场景中，相邻小区往往复用或者部分复用导频序列进行信道估计以提高系统的频谱效率[4，由此带来的导频污染问题无法通过增加基站端的天线数来解决。因此，采取合理的导频污染减轻方法来降低小区间干扰是发挥大规模MIMO技术优势的前提条件。

当前学术界对导频污染减轻方法已做了大量研究，主要有以下三个研究方向：基于信道子空间的信道估计方法，基于信号到达角的方法，基于导频分配的方法。其中，基于信道子空间的方法需要信道的二阶统计信息[5]，但二阶统计信息在实际通信系统中较难获取。基于信道到达角的方法需要假设用户到基站的到达角较窄且不同用户的到达角互不重叠[6，但此假设在实际系统中较难满足。基于导频分配的导频污染能减轻方案通过对用户所发射的导频序列进行重新分配，从而降低使用相同或非正交导频序列用户之间的小区间干扰。文献[7-12]从导频分配的角度对减轻导频污染方案进行了研究。文献[7]的智能导频分配（SmartPilotAssignment,SPA）方案利用不同用户到基站的大尺度衰落因子不同的特点，给目标小区中信道质量最差的用户分配产生小区间干扰最小的导频序列。此方案虽然能够显著提高边缘用户性能，但很大程度上降低了中心用户的性能。文献[8]利用用户到基站的用户信号强度设置的干扰强度差将用户分类，并对不同类用户采用不同的导频分配算法，一定程度上提高了系统容量，但是其对于中心用户采用随机导频分配方式分配导频，未能显著提高中心用户的性能。文献[9]采用软导频复用方案，将小区中用户分为中心用户组和边缘用户组，对于中心用户组，相邻小区将复用同一导频子组以提高导频利用率，而对于边缘用户组，将分配相互正交的导频子组以抑制干扰。文献[10]利用用户间的导频污染强度矩阵，通过搜索整个矩阵元素的方式给导频污染强度较大的两个用户分配不同的导频。此方案有效优化了导频分配算法，大幅度提高了系统容量。但此方案计算复杂度过高，在实际的通信系统中较难实现。文献[11]提出基于位置信息的导频分配方案，该方案根据用户位置在所属基站为极点的极坐标系下的极角大小，对用户进行排序并分配导频。此方案结合定向天线的特点，通过增大复用相同导频的不同小区用户之间的距离来降低用户间的导频污染。相似的，文献[12]也利用定向天线的特点，提出联合时移和空间划分的导频分配方案，该方案从时域和空间域两个角度来降低用户间的导频复用程度，从而有效地抑制了导频污染。

本文提出一种基于用户位置的导频分配方案来减轻用户间的导频污染。首先，采用开环功率控制方法，通过调整上行功率控制因子的大小，提高边缘用户的发射功率，适当降低中心用户的发射功率，最终使基站接收到不同用户的功率相等。然后，在功率控制的条件下，利用用户到本小区基站的距离与到目标小区基站距离的比值来定义用户对目标小区中使用相同导频用户的导频污染强度，使不同小区中导频污染强度之和较小的两个用户分配相同的导频序列。与文献[7-9]中利用用户到基站的大尺度衰落因子来定义用户信号强度不同的是，本文方案为降低计算复杂度和系统开销，将用户到不同小区基站距离的比值距离作为衡量用户间导频污染强度的主要因素，进而进行导频分配。仿真结果表明，所提导频分配方案有效缩小了边缘用户与中心用户的通信性能差距，也一定程度上提高了系统容量，且本导频分配方案计算复杂度较低，在实际的通信系统中更易实现。

# 1 系统模型

如图1所示，本文考虑一个大规模MIMO多小区多用户系统，由 $L$ 个蜂窝小区组成，每个蜂窝小区有 $K$ 个单天线用户，位于小区中心的基站配备了 $M$ 根天线 $( M { > } { > } K )$ 并同时同频服务于小区中的所有用户。其中，第 $j$ 小区中第 $k$ 个用户到第i小区基站的信道向量可以建模为

$$
\pmb { { h } } _ { i , j , k } = \pmb { { g } } _ { i , j , k } \sqrt { \beta _ { i , j , k } }
$$

其中: $\pmb { g } _ { i , j , k } \sim C N ( \mathbf { 0 } _ { M \times 1 } , \mathbf { I } _ { M } ) ,$ 表示小尺度衰落向量， $\pmb { I } _ { \pmb { M } }$ 为M阶单位阵。 $\beta _ { i , j , k }$ 表示该用户到基站的大尺度衰落系数。进一步的，第 $j$ 小区的 $K$ 个用户到第 $i$ 小区基站的信道矩阵可以表示为

$$
\begin{array} { l } { { \pmb { H } } _ { i , j } = \left[ { \pmb { h } } _ { i , j , 1 } { \pmb { h } } _ { i , j , 2 } \cdots \cdots { \pmb { h } } _ { i , j , K } \right] } \\ { = \left[ { \pmb { g } } _ { i , j , 1 } { \pmb { g } } _ { i , j , 2 } \cdots \cdots \cdot { \pmb { g } } _ { i , j , K } \right] { \pmb { D } } _ { i , j } ^ { 1 / 2 } } \end{array}
$$

其中： $D _ { i , j } = d i a g \left\{ \beta _ { i , j , 1 } , \beta _ { i , j , 2 } , \cdots \beta _ { i , j , K } \right\}$ 表示由第 $j$ 小区的 $K$ 个用户到第 $i$ 小区基站的大尺度衰落系数构成的对角矩阵。则第$i$ 小区基站接收到的信号可以表示为

$$
{ \bf y } _ { i } ^ { u l } = \sqrt { p _ { j , k } } \sum _ { j = 1 } ^ { L } \sum _ { k = 1 } ^ { K } { \pmb { h } } _ { i , j , k } x _ { j , k } ^ { u l } + { \pmb { n } } _ { i } ^ { u l }
$$

其中: $\boldsymbol { p } _ { j , \boldsymbol { k } }$ 为第 $j$ 小区第 $k$ 个用户的发送功率， $\boldsymbol { x } _ { j , k } ^ { u l }$ 为第 $j$ 小区第$k$ 个用户的上行发送信号， ${ \pmb n } _ { i } ^ { u l } \sim C N ( 0 , { \pmb I } _ { { M } } )$ 表示信道噪声。

![](images/64a546e373b792be0fad23b60402d7a033d5c5ea06ab76d71a867a619aaa5594.jpg)  
图1系统模型

在实际的通信系统中，为了减轻小区间干扰，通常会对本小区用户进行上行功率控制。则根据功率控制模型[14]，第 $i$ 小区基站接收到本小区内第 $k$ 个用户的功率可以表示为$p _ { r } = \gamma \frac { p _ { i , k } } { ( d _ { i , i , k } ) ^ { \alpha } }$ Pi，其中，p,为第i小区基站接收到的功率，α为路损因子， $\gamma$ 为功率控制因子， $d _ { i , i , k }$ 为第 $i$ 小区中第 $k$ 个用户到本小区基站的距离。

由于小区边缘区域用户距离基站较远，路径损耗较大，为了保证通信质量，需要增大其上行信号发射功率；中心区域用户由于距离基站较近，路径损耗较小，在保证通信性能的前提下，可以适当降低上行信号发射功率。因此，为保证小区用户正常的通信，设置一个用户上行接收的门限功率 $p _ { t h }$ ，通过调整功率控制因子 $\gamma$ 的大小，改变用户上行发射功率，使基站接收到本小区用户的功率为pth°

在进行上行功率控制后，使不同用户到各自小区基站的信号功率相等，那么根据功率衰减模型[13]，第 $j$ 小区第 $k$ 个用户的发送功率为 $\boldsymbol { p } _ { j , \boldsymbol { k } } = \boldsymbol { p } _ { t h } / \beta _ { j , j , \boldsymbol { k } } , \forall j , \boldsymbol { k }$ ，因而式（3）可以改写为

$$
\mathbf { y } _ { i } ^ { u l } = \sum _ { j = 1 } ^ { L } \sum _ { k = 1 } ^ { K } \sqrt { p _ { t h } \beta _ { i , j , k } / \beta _ { j , j , k } } \mathbf { g } _ { i , j , k } x _ { j , k } ^ { u l } + \pmb { n } _ { i } ^ { u l }
$$

令 $\overline { { \pmb { g } } } _ { i , j , k } = \sqrt { \beta _ { i , j , k } / \beta _ { j , j , k } } \pmb { g } _ { i , j , k }$ ，其协方差矩阵为

$$
\pmb { R } _ { i , j , k } = ( \beta _ { i , j , k } / \beta _ { j , j , k } ) \pmb { I } _ { M }
$$

则上式进一步变为

$$
{ \bf y } _ { i } ^ { u l } = \sum _ { j = 1 } ^ { L } \sum _ { k = 1 } ^ { K } \sqrt { p _ { t h } } \overline { { { \pmb g } } } _ { i , j , k } x _ { j , k } ^ { u l } + { \pmb n } _ { i } ^ { u l }
$$

# 1.1信道估计

在TDD模式下，每一帧时隙都被划分为上行导频传输、上行数据传输和下行数据传输三个阶段。在上行导频传输阶段，假设每个用户都向基站发送导频序列，则第 $i$ 小区基站接收到的导频信号可以写成如下形式：

$$
Y _ { i } ^ { { p i l o t } } = \sqrt { { p _ { t h } } } \tau \sum _ { j = 1 } ^ { L } \sum _ { k = 1 } ^ { K } \overline { { \pmb { g } } } _ { i , j , k } \phi _ { { f _ { j , k } } } ^ { T } + N _ { i } ^ { { p i l o t } }
$$

其中: $\boldsymbol { \tau }$ 表示导频长度， ${ \cal N } _ { i } ^ { p i l o t } \in { \cal C } ^ { M \times \tau }$ 表示基站接收到的高斯白噪声。 $\Phi = \left[ \phi , \phi , \cdots \cdots \phi _ { \cal S } \right] \in C ^ { \tau \times { \cal S } }$ 表示长度为 $\boldsymbol { \tau }$ ，数量为 $s$ 的正交导频序列，并满足下列条件： $\phi _ { i } ^ { T } { \phi } _ { j } ^ { * } = \left\{ 1 , \quad i = j \atop 0 , \quad i \neq j  \right.$ {1，i=j，下标fj表示把导频序列 $\phi _ { f _ { j , k } }$ 分配给第 $j$ 小区中第 $k$ 个用户，需满足条件：$f _ { j , k } \in \left\{ 1 , 2 , \cdots \cdots S \right\}$ $f _ { j , k } \neq \ * f _ { j , k ^ { \prime } } , \forall k \neq k ^ { \prime }$ 。第 $i$ 小区基站根据接收到的导频信号 $Y _ { i } ^ { p i l o t }$ 进行最小二乘（Least Squares,LS)信道估计，则第 $i$ 小区第 $k$ 个用户的信道估计结果可以表示为

$$
\hat { \pmb { g } } _ { i , i , k } = \frac { 1 } { \sqrt { p _ { t h } \tau } } { \cal Y } _ { i } ^ { p i l o t } \pmb { \phi } _ { f _ { i , k } } ^ { * } = \overline { { \pmb { g } } } _ { i , i , k } + \sum _ { j \neq i , f _ { j , k ^ { \prime } } = f _ { i , k } } \overline { { \pmb { g } } } _ { i , j , k ^ { \prime } } + \pmb { n } _ { i , i , k }
$$

其中：ni,ik ${ \pmb n } _ { i , i , k } = \frac { 1 } { \sqrt { p _ { t h } \tau } } N _ { i } ^ { p i l o t } { \pmb \phi } _ { f _ { i , k } } ^ { * }$ 表示等效噪声， $\sum _ { j \neq i , f _ { j , \boldsymbol { k } ^ { \prime } } = f _ { i , \boldsymbol { k } } } \overline { { \pmb { g } } } _ { i , j , \boldsymbol { k } ^ { \prime } }$ 表示其他小区中使用相同导频的用户产生的小区间干扰，由于基站端无法区分不同小区中使用相同导频用户发射的导频信号，因而，无法随着基站天线数的增加而大幅度减小，所以无法彻底消除导频污染。

# 1.2上行数据传输

在完成上行导频传输后，用户会在第二阶段向各自的基站发送数据信号，则第 $i$ 小区基站接收到的上行数据信号可以表示为

$$
{ \bf { y } } _ { i } ^ { d a t a } = \sqrt { { p _ { t h } } } \sum _ { j = 1 } ^ { L } { \sum _ { k = 1 } ^ { K } { { { \overline { { { g } } } } _ { i , j , k } } x _ { j , k } ^ { d a t a } } } + { { \pmb { n } } _ { i } ^ { u l } }
$$

其中: $x _ { j , k } ^ { d a t a }$ 为第 $j$ 小区第 $k$ 个用户发送的上行数据，满足能量约束条件 $E \Big \{ { ( x _ { j , k } ^ { d a t a } ) } ^ { * } x _ { j , k } ^ { d a t a } \Big \} = 1$ ，为检测用户上行传输数据，基站利用上行信道估计结果来生成相应的检测矩阵A=[ai,ai,2aiκ]∈Cκx，若采用经典的MF 算法，则检测矩阵 $A _ { i } = \hat { \pmb { g } } _ { i , i } ^ { H }$ ，其中， $\pmb { \hat { g } } _ { i , i } = \left[ \hat { \pmb { g } } _ { i , i , 1 } \hat { \pmb { g } } _ { i , i , 2 } \cdots \cdots \hat { \pmb { g } } _ { i , i , K } \right]$ 表示在上行功率控制情况下，第 $i$ 小区基站对本小区 $K$ 个用户的信道估计结果。经过检测矩阵 $A _ { i }$ 处理后，第 $i$ 小区基站接收到的第 $k$ 个用户的数据可以表示为

$$
\begin{array} { l } { { \pmb r } _ { i , k } ^ { u l } = \sqrt { p _ { t h } } { \pmb a } _ { i , k } ^ { T } \overline { { \pmb g } } _ { i , i , k } x _ { i , k } ^ { d a t a } + \sqrt { p _ { t h } } \sum _ { k ^ { \prime } \neq k } { \pmb a } _ { i , k } ^ { T } \overline { { \pmb g } } _ { i , i , k ^ { \prime } } x _ { i , k ^ { \prime } } ^ { d a t a } } \\ { + \sqrt { p _ { t h } } \sum _ { j \neq i } \displaystyle \sum _ { k ^ { \prime } = 1 } ^ { K } { \pmb a } _ { i , k } ^ { T } \overline { { \pmb g } } _ { i , j , k ^ { \prime } } x _ { j , k ^ { \prime } } ^ { d a t a } + { \pmb a } _ { i , k } ^ { T } { \pmb n } _ { i } ^ { u l } } \end{array}
$$

根据文献[13,15]中计算可达速率的方法，

$$
\pmb { a } _ { i , k } ^ { T } \overline { { \pmb { g } } } _ { i , i , k } = E ( \pmb { a } _ { i , k } ^ { T } \overline { { \pmb { g } } } _ { i , i , k } ) + [ \pmb { a } _ { i , k } ^ { T } \overline { { \pmb { g } } } _ { i , i , k } - E ( \pmb { a } _ { i , k } ^ { T } \overline { { \pmb { g } } } _ { i , i , k } ) ]
$$

同时，令

则式（10）可以表示为

$$
r _ { i , k } = \sqrt { p _ { t h } } E ( \pmb { a } _ { i , k } ^ { T } \overline { { \pmb { g } } } _ { i , i , k } ) x _ { i , k } ^ { d a t a } + \pmb { Z } _ { i , k }
$$

所以第 $i$ 小区中第 $k$ 个用户的上行SINR为

$$
S I N R _ { i , k } ^ { u l } = \frac { p _ { t h } \left| E ( \pmb { a } _ { i , k } ^ { T } \overline { { \pmb { g } } } _ { i , i , k } ) \right| ^ { 2 } } { E ( \left| \pmb { Z } _ { i , k } \right| ^ { 2 } ) }
$$

其中:

$$
E ( { \left| { { \mathbf { Z } } _ { i , k } } \right| } ^ { 2 } ) = \sum _ { j = 1 } ^ { L } \sum _ { l = 1 } ^ { K } p _ { t h } E ( { \left| { { a } _ { i , k } ^ { T } { { \overline { { g } } } _ { i , j , l } } } \right| } ^ { 2 } ) - p _ { t h } { \left| E ( { { a } _ { i , k } ^ { T } { { \overline { { g } } } _ { i , i , k } } } ) \right| } ^ { 2 } + E ( { \left| { { a } _ { i , k } ^ { T } { { n } _ { i } } } \right| } ^ { 2 } )
$$

由于各用户信道相互独立，所以

$$
E ( \pmb { a } _ { i , k } ^ { T } \overline { { \pmb { g } } } _ { i , i , k } ) = t r ( E ( \overline { { \pmb { g } } } _ { i , i , k } ^ { T } \overline { { \pmb { g } } } _ { i , i , k } ) ) = t r ( \pmb { R } _ { i , i , k } )
$$

$$
\begin{array} { l } { { \displaystyle E \big ( \left| { \pmb a } _ { i , k } ^ { T } { \pmb n } _ { i } ^ { u l } \right| ^ { 2 } \big ) = t r ( E ( { \pmb a } _ { i , k } ^ { T } { \pmb a } _ { i , k } { \pmb n } _ { i } ^ { u l } ( { \pmb n } _ { i } ^ { u l } ) ^ { H } ) ) = t r ( E ( { \pmb a } _ { i , k } { \pmb a } _ { i , k } ^ { T } ) ) } } \\ { { \displaystyle \qquad = t r ( \sum _ { j \not = i , f _ { j , k } = f _ { i , k } } { \pmb R } _ { i , j , k } + \frac { 1 } { P _ { t h } \tau } { \pmb I } _ { M } ) } } \end{array}
$$

根据文献[16]中相关结论，

$$
\begin{array} { l } { { \displaystyle E \big ( \big | a _ { i , k } ^ { T } \overline { { g } } _ { i , j , l } \big | ^ { 2 } \big ) = t r ( ( \sum _ { j \neq i , j , l } R _ { i , j , k } + \frac { 1 } { P _ { t h } \tau } I _ { M } ) R _ { i , j , l } ) + [ t r ( R _ { i , j , l } ) ] ^ { 2 } } } \\ { ~ + t r ( ( \sum _ { j \neq i , j , j \neq f _ { i , k } } R _ { i , j , k } + \frac { 1 } { P _ { t h } \tau } I _ { M } ) R _ { i , j , l } ) }  \\ { { \displaystyle = \sum _ { j = 1 } ^ { L } \sum _ { l = 1 } ^ { K } t r ( ( \sum _ { j \neq i } R _ { i , j , k } + \frac { 1 } { P _ { t h } \tau } I _ { M } ) R _ { i , j , l } ) + \sum _ { j = 1 } ^ { L } \Bigl [ t r ( R _ { i , j , k } ) \Bigr ] ^ { 2 } } } \end{array}
$$

所以得到的用户上行SINR表示形式如式（19）所示。

$$
S I N R _ { i , k } ^ { u } = \frac { \left[ \frac { 1 } { M } t r ( R _ { i , i , k } ) \right] ^ { 2 } } { \frac { 1 } { M ^ { 2 } } \sum _ { j = 1 } ^ { L } \sum _ { l = 1 } ^ { K } t r ( ( \sum _ { j \neq i } R _ { i , j , k } + \frac { 1 } { P _ { t b } } I _ { l } ) R _ { i , j , l } ) + \frac { 1 } { M ^ { 2 } p _ { i b } } t r ( \sum _ { j \neq i , j _ { i } = j _ { l } } R _ { i , j , k } + \frac { 1 } { P _ { t b } } I _ { M } ) + \sum _ { j \neq l } \left[ \frac { 1 } { M } t r ( R _ { i , j , k } ) \right] }
$$

由式（5）可得

$$
t r ( { R } _ { i , j , k } ) / M = \beta _ { i , j , k } / \beta _ { j , j , k }
$$

所以有 T $\frac { 1 } { M } ( t r ( \sum _ { j \neq i , f _ { j , k } = f _ { i , k } } R _ { i , j , k } + \frac { 1 } { P _ { t h } \tau } I _ { M } ) ) = \sum _ { j \neq i } \frac { \beta _ { i , j , k } } { \beta _ { j , j , k } } + \frac { 1 } { P _ { t h } \tau }$

$$
\frac { 1 } { M } t r ( ( \sum _ { j \neq i } R _ { i , j , k } + \frac { 1 } { P _ { t h } \tau } I _ { M } ) R _ { i , j , l } ) = \frac { 1 } { M } t r ( \sum _ { j \neq i } R _ { i , j , k } R _ { i , j , l } ) + \frac { 1 } { p _ { t h } \tau } \frac { \beta _ { i , j , l } } { \beta _ { j , j , l } }
$$

当 $M \to \infty$ 时，小区内干扰和噪声的影响可以忽略不计，所以

$$
S I N R _ { i , k } ^ { u l } = \frac { 1 } { \frac { 1 } { M ^ { 2 } } { \sum _ { j = 1 } ^ { L } } \displaystyle { \sum _ { l = 1 } ^ { K } } t r ( { \sum _ { j \ne i } } { \cal R } _ { i , j , k } { \cal R } _ { i , j , l } ) + { \sum _ { j \ne i } } ( { \beta _ { i , j , k } / \beta _ { j , j , k } } ) ^ { 2 } }
$$

由于 $\frac { 1 } { M ^ { 2 } } t r ( \sum _ { j \neq i } R _ { i , j , k } { \pmb R } _ { i , j , l } ) = \frac { 1 } { M } \sum _ { j \neq i } \frac { \beta _ { i , j , k } } { \beta _ { j , j , k } } \frac { \beta _ { i , j , l } } { \beta _ { j , j , l } }$ βi,jkβij，在M→∞时）→，所以

$$
S I N R _ { i , k } ^ { u l } = \frac { 1 } { \displaystyle \sum _ { j \neq i } ( \beta _ { i , j , k } / \beta _ { j , j , k } ) ^ { 2 } }
$$

则该用户的上行可达速率可以表示为

$$
C _ { i , k } ^ { u l } = B _ { w } \frac { T _ { u l } } { T _ { 0 } } E \big \{ \log _ { 2 } ( 1 + S I N R _ { i , k } ^ { u l } ) \big \}
$$

其中： $B _ { { } _ { w } }$ 为系统带宽， $T _ { 0 }$ 为 TDD 模式一帧的时间长度， $T _ { u l }$ 为TDD 模式一帧中上行数据传输的时间长度。

# 2 导频分配

2.1用户间导频污染强度分析

由式（22）可得，则第 $i$ 小区第 $k$ 个用户的上行SINR可以表示为

$$
S I N R _ { i , k } ^ { u l } = \frac { 1 } { \displaystyle \sum _ { j \neq i , f _ { j , k ^ { \prime } } = f _ { i , k } } ( \beta _ { i , j , k ^ { \prime } } / \beta _ { j , j , k ^ { \prime } } ) ^ { 2 } }
$$

其中： $\beta _ { i , j , k ^ { \prime } }$ 为第 $j$ 小区第 $k ^ { \prime }$ 个用户到第 $i$ 小区基站的大尺度衰落系数，同理， $\beta _ { j , j , k ^ { \prime } }$ 是其到本小区基站的大尺度衰落系数。$f _ { j , k ^ { \prime } } = f _ { i , k }$ 表示第 $j$ 小区第 $k ^ { \prime }$ 个用户与第 $i$ 小区第 $k$ 个用户使用相同的导频。从上式可以看出，由于本文的系统模型是在采用了上行功率控制的情况下建立的，所以用户的上行SINR由相邻小区中与目标用户使用相同导频的干扰用户的大尺度衰落系数决定，而与目标用户到本小区基站的大尺度衰落系数无关。用户到基站的大尺度衰落系数与用户到基站的距离和阴影衰落有关，可以表示为

$$
\beta _ { i , j , k } = \frac { S _ { i , j , k } } { ( d _ { i , j , k } / R ) ^ { \alpha } }
$$

其中： $S _ { i , j , k }$ 为阴影衰落， $1 0 \log _ { 1 0 } S _ { i , j , k } \sim C N ( 0 , \sigma )$ ， $d _ { i , j , k }$ 为第 $j$ 小区第 $k$ 个用户到第 $i$ 小区基站的距离， $R$ 是小区半径， $\alpha$ 是路径损耗因子。将式（25）代入式（24)，则式（24）可以进一步写为

$$
S I N R _ { i , k } ^ { u l } = \frac { 1 } { \displaystyle \sum _ { j \neq i , f _ { j , k ^ { \prime } } = f _ { i , k } } ( \frac { S _ { i , j , k ^ { \prime } } } { S _ { j , j , k ^ { \prime } } } \cdot ( \frac { d _ { j , j , k ^ { \prime } } } { d _ { i , j , k ^ { \prime } } } ) ^ { \alpha } ) ^ { 2 } }
$$

从式（26）可以得出，目标小区用户的上行SINR与导频干扰用户到本小区基站及到目标小区基站的距离密切相关。在系统采用上行功率控制时，干扰小区中的导频干扰用户到本小区基站越远，其发射功率越大。若此干扰用户位于目标小区与干扰小区的交界处（即干扰用户到目标小区基站距离较小)，根据功率衰减模型，目标小区基站接收到的干扰功率越强，导频污染越严重。相反的，当干扰用户到本小区基站较近，且干扰用户到目标小区基站距离较大，则导频污染较小。由于在实际的通信系统中，想要准确快速地获取用户到基站的大尺度衰落系数不是很容易，需要较高的计算复杂度。根据式（25)，用户到基站的大尺度衰落系数的大小很大程度上由用户到基站的距离决定，而且随着定位技术的快速发展，小区中用户的位置相对容易获得，用户到基站的距离能够快速获得，可以大幅度降低系统的计算复杂度。因此，本文将利用不同干扰用户到基站的距离不同的特点进行导频分配。利用干扰小区内的导频干扰用户到本小区基站距离与到目标小区距离的比值来定义导频干扰用户对目标小区用户产生的导频污染强度，表示为ni,jk'= k=2第（204号 $k ^ { \prime }$ 个用户对目标小区 $i$ 中第 $k$ 个用户的导频污染强度，（204 $f _ { j , k ^ { \prime } } = f _ { i , k }$ 表示这两个用户使用相同的导频。同样的，目标小区$i$ 中第 $k$ 个用户也会对干扰小区 $j$ 中第 $k ^ { \prime }$ 个用户产生导频污染，$\eta _ { j , i , k } = \frac { d _ { i , i , k } } { d _ { j , i , k } }$ dk。所以，目标小区i中第 $k$ 个用户与干扰小区 $j$ 中第 $k ^ { \prime }$ 个用户之间的导频污染强度可以表示为

$$
\eta _ { < i , k > , < j , k ^ { \prime } > } = \eta _ { j , i , k } + \eta _ { i , j , k ^ { \prime } } = \frac { d _ { i , i , k } } { d _ { j , i , k } } + \frac { d _ { j , j , k ^ { \prime } } } { d _ { i , j , k ^ { \prime } } }
$$

$\eta _ { < i , k > , < j , k ^ { \prime } > }$ 越大,表示当两个用户分配相同的导频时,用户间的导频污染强度越大,小区间干扰越强。

# 2.2导频分配方案

为简化导频分配方案，本文考虑两个小区间的导频分配。假设目标小区为第 $i$ 小区，相邻干扰小区为第 $j$ 小区，每个小区均有 $K$ 个用户，系统所能提供的正交导频数等于用户数。通过对式（27）的分析，本文得出，为降低用户间的导频污染，应该给 $\eta _ { < i , k > , < j , k ^ { \prime } > }$ 较大的两个不同小区用户分配相互正交的导频；给 $\eta _ { < i , k > , < j , k ^ { \prime } > }$ 较小的两个不同小区用户分配相同的导频。具体的导频分配步骤如下：

a)测量用户到本小区基站距离。计算干扰小区 $j$ 中所有 $K$ 个用户到本小区基站的距离 $d _ { j , j , k ^ { \prime } } ( k ^ { \prime } = 1 , 2 , \cdot \cdot \cdot K )$ ；计算目标小区$i$ 中所有 $K$ 个用户到本小区基站的距离 $d _ { i , i , k } ( k = 1 , 2 , \cdot \cdot \cdot K )$ □

b)测量用户到相邻小区基站距离。计算干扰小区 $j$ 中所有$K$ 个用户到目标小区基站的距离 $d _ { i , j , k ^ { \prime } } ( k ^ { \prime } = 1 , 2 , \cdots K )$ ；计算目标小区 $\mathbf { \chi } _ { i }$ 中所有 $K$ 个用户到干扰小区基站的距离$d _ { j , i , k } ( k = 1 , 2 , \cdot \cdot \cdot K )$ 。

c)用户分区。为降低后续导频分配算法的计算复杂度，在进行导频分配前，首先根据用户到相邻小区基站的距离对用户进行分区。为便于计算，假设小区形状近似于半径为 $R$ 的圆形。具体用户分区方法如下：(a)干扰小区用户分区。若$R < d _ { i , j , k ^ { \prime } } \leq 2 R$ ，则将用户 $u _ { j , k ^ { \prime } }$ 加入用户集合 $U _ { j , 1 }$ ；若 $d _ { i , j , k ^ { \prime } } > 2 R$ ，则将用户 $\boldsymbol { u } _ { j , \boldsymbol { k } ^ { \prime } }$ 加入用户集合 $U _ { j , 2 }$ 。统计得到用户集合 $U _ { j , 1 }$ 中用户数为 $N$ ，则用户集合 $U _ { j , 2 }$ 中用户数为 $K \ – N _ { \mathfrak { c } }$ 。(b)目标小区用户分区。按照 $d _ { j , i , k }$ 递减的顺序对目标小区用户进行排序；将已排序的用户中的前 $N$ 个用户加入用户集合 $U _ { i , 1 }$ ，后 $K – N$ 个用户加入用户集合Ui,2。

d)正交导频组划分。按照步骤c)中用户分区情况对系统所能提供的正交导频组 $\Phi = \left[ \phi _ { 1 } , \phi _ { 2 } , \cdot \cdot \cdot \phi _ { K } \right]$ 进行划分。可以划分为如下形式： $\Phi = \Phi _ { 1 } + \Phi _ { 2 }$ ， $\Phi _ { 1 } = [ \phi _ { 1 } , \phi _ { 2 } , \cdot \cdot \cdot \phi _ { N } ] , \Phi _ { 2 } = [ \phi _ { N + 1 } , \phi _ { N + 2 } , \cdot \cdot \cdot \phi _ { K } ] \ : \ : ,$ （其中:用户集合 $U _ { j , 1 }$ 与用户集合 $U _ { i , 1 }$ 中的 $N$ 个用户复用导频子组$\Phi _ { 1 }$ 中的 $N$ 个正交导频；用户集合 $U _ { j , 2 }$ 与用户集合 $U _ { i , 2 }$ 中的 $K \cdot$ $N$ 个用户复用导频子组 $\Phi _ { 2 }$ 中的 $K { - } N$ 个正交导频。

e)导频分配。为了保证用户之间的公平性，提高边缘用户的通信性能，需要保证复用相同导频的两个用户间的导频污染强度 $\eta _ { < i , k > , < j , k ^ { \prime } > }$ 较低。因此，本文所采用的导频分配算法具体思路为：干扰小区中 $\eta _ { i , j , k ^ { \prime } }$ 较大的用户与目标小区中 $\eta _ { j , i , k }$ 较小的用户复用相同的导频。在用户分区和导频组划分完成后，下面进行具体的导频分配：(a)计算用户集合 $U _ { i , 1 }$ 中 $N$ 个用户对干扰小区的导频污染强度nj,i,k = $\eta _ { j , i , k } = \frac { d _ { i , i , k } } { d _ { j , i , k } } ( k = 1 , 2 , \cdot \cdot \cdot N )$ dik(k=1,2,N)，按照nj,递减的顺序对用户进行排序，并将导频子组 $\Phi _ { 1 }$ 中导频依次分配给排序后的用户，即 $\phi _ { k } = \phi _ { f _ { i , k } } , \eta _ { j , i , k } \geq \eta _ { j , i , k + 1 } ( k = 1 , 2 , \cdots N ) ; ($ b)计算用户集合 $U _ { j , 1 }$ 中的 $N$ 个用户对目标小区的导频污染强度dj(k'=1,2,N)，按照nj,递增的顺序对用户进行 dij.'排序，同样导频子组 $\Phi _ { 1 }$ 中的导频依次分配给排序后的用户，即：$\phi _ { \boldsymbol { k } ^ { \prime } } = \phi _ { f _ { j , \boldsymbol { k } ^ { \prime } } } , \eta _ { i , j , \boldsymbol { k } ^ { \prime } } \le \eta _ { i , j , \boldsymbol { k } ^ { \prime } + 1 } ( \boldsymbol { k } ^ { \prime } = 1 , 2 , \cdots N )$ 。同理，用户集合 $U _ { i , 2 }$ 与用户集合 $U _ { j , 2 }$ 中 $K { - } N$ 个用户的导频分配方法与步骤(a)和(b)所述分配算法相同。

# 3 仿真分析

本节对提出的导频污染减轻方案进行仿真验证，考虑一个由 $L$ 个蜂窝小区组成的系统，每个小区包括 $K$ 个单天线用户和一个配备 $M$ 根天线的基站组成，仿真模型如图1所示，系统仿真参数如表1所示。

图2描述了不同导频分配方案下，目标小区用户平均上行可达速率随基站天线数的变化情况。从图中可以看出，所提导频分配方案比随机导频分配方案性能上得到了较大提升。而且当基站天线数达到256时，导频污染问题愈发严重时，随机导频分配方案的性能提高程度几乎为零。而其余几种方案性能仍得到一定程度的提升。本文所提方案也优于用户分类方案以及SPA方案，因为本文更多的考虑了用户间的公平性，其中心用户性能好于上述两种方案。需指出的是，本文方案在性能上相对于文献[10]所提方案仍有差距。原因主要有两点：首先，文献[10]中计算导频污染强度是根据用户到基站的大尺度衰落因子考虑了信号的阴影衰落对信号衰减的影响，其计算公式为（20 $\eta = \beta _ { j , k ^ { \prime } , i } ^ { 2 } \big / \beta _ { i , k , i } ^ { 2 } + \beta _ { i , k , j } ^ { 2 } \big / \beta _ { j , k ^ { \prime } , j } ^ { 2 }$ 所以，与本文仅根据用户到基站距离衡量用户间导频污染强度相比，文献[10]方案的准确性更高。其次，文献[10]在进行导频分配时，在用户选择时，是通过计算整个系统内未分配导频用户与不同小区中已分配导频用户之间的导频污染强度，从中选择导频污染强度最大的用户为其分配导频；而在导频选择时，是通过计算已分配导频用户与当前选择的用户之间的导频污染强度，从中选择导频污染强度较小的用户其所对应的导频，并将其分配给已选择的用户。所以与本文导频分配方案相比，文献[10]方案能够给系统中每一个用户分配当前最佳的导频序列。综合以上两个原因，文献[10]方案在系统容量、频谱效率等方面是要优于本文方案的。但文献[10]方案的缺点是复杂度过高，工程上实施难度较大。下面对本文和文献[10]导频分配算法的计算复杂度做具体分析。

表1系统仿真参数  

<html><body><table><tr><td>参数</td><td>数值</td></tr><tr><td>小区数L</td><td>7</td></tr><tr><td>用户数K</td><td>1~50</td></tr><tr><td>小区半径R（m)</td><td>1000</td></tr><tr><td>基站天线数M</td><td>[8，512]</td></tr><tr><td>路径损耗指数α</td><td>3.8</td></tr><tr><td>阴影衰落系数δshadow</td><td>8dB</td></tr><tr><td>系统带宽Bw</td><td>20MHz</td></tr><tr><td>导频长度τ</td><td>τ=K</td></tr><tr><td>上行发射功率p,</td><td>15</td></tr><tr><td>上行接收门限功率 Pih</td><td>5</td></tr><tr><td>一帧时隙总数To</td><td>100</td></tr><tr><td rowspan="2">上行数据传输时隙数Tul</td><td>To-t</td></tr><tr><td>2</td></tr></table></body></html>

首先，在计算用户间导频污染强度时，虽然文献[10]的准确性较高，但是要准确快速地获得用户到基站的大尺度衰落因子是有一定难度的，而本文所提方案获取用户到基站的距离则相对容易一些。其次，在导频分配阶段，文献[10]方案在进行用户选择和导频选择时都是计算整个系统中所有小区用户间导频污染强度，并通过排序选取最佳的用户和导频，其时间复杂度为$ { \mathrm { O } } ( S ( L K ) ^ { 3 } )$ ，其中 $s$ 为正交导频数。而本文导频分配方案在用户选择和导频选择时，只考虑相邻小区之间的用户，且分配算法也较为简单，其时间复杂度为 $\mathrm { O } ( L K ^ { 2 } )$ 。所以在本文所提导频分配算法的时间复杂度与文献[10]相比是较低的，且随着小区用户数的增多，优势更加明显。通过上述分析可得，文献[10]方案虽然性能较好，但计算复杂度较大，实用性很低。而本文方案虽然性能低于文献[10]，但计算复杂度较低，易于实现，具有一定的实用价值。

![](images/05cccafdf61385e671aea96cd0f00048841313774e3f32808213bed61e4475cb.jpg)  
图2用户上行可达速率随基站天线数变化曲线

图3描述了上行用户SINR的累积分布函数，其中，基站天线数 $\mathrm { M } { = } 1 2 8$ 。从图中易得，随机导频分配方案性能最差，甚至有大约 $7 \sim 8 \%$ 的用户上行SINR 低于OdB。文献[7]的 SPA导频分配方案在较低SINR用户方面优势较为明显，但在高SINR用户方面却不如其余三种导频分配方案。这是因为文献[7]采用贪婪算法为用户分配导频，优先保证边缘用户的通信性能，但会导致中心用户性能的下降。相对而言，本文方案则更多的考虑了用户公平性，在提高边缘用户性能的同时，也一定程度上保证了中心用户性能的稳定。本文方案在低SINR用户方面性能要优于用户分类方案和文献[10]方案，在高SINR用户方面低于文献[10]方案，这是因为文献[10]方案在导频分配过程中，进行用户选择和导频选择时，首先选择的用户分配的导频受到的干扰要小于后面选择的用户分配的导频受到的干扰，所以在高SINR用户方面文献[10]方案是最优的，但低SINR用户方面其性能要低于本文所提方案，但总体相差不大。

![](images/93b593d1584260527d2bb34f7735c86b94ed72a92aa95e6e91ff4c072a77f49e.jpg)  
图3上行传输用户接收SINR的CDF分布

图4描述了几种导频分配方案以及无导频污染情况下信道的误比特率（BER，biterrorratio）对比曲线。其中调制方式为BPSK，基站天线数为128。容易看出，本文导频分配方案误比特率性能明显优于随机导频分配方案，相对于文献[7]SPA方案和文献[8]基于用户分类的导频分配方案的BER也更低一些，而且随着SINR的增加，性能优势更加突出。但性能仍低于文献[10]方案，但差距较小，与无导频污染情况下相比，本文方案的 BER仍然较高。

![](images/ccf86b25d4fb327b6a63b8c5b8b50f7c544a7f55de732758dfe7cdd0429e7f59.jpg)  
图4不同SINR时信号传输的误比特率

图5描述了小区上行可达和速率随小区内用户数的变化情况，其中，基站天线数 $\mathrm { M } { = } 2 5 6$ 。从图中可得，随着用户数的增多，小区上行可达和速率增长幅度逐渐变小。这是因为根据式(23)，当用户数增多时，为了保证小区内正交导频的数量，需要增大导频的长度，从而一定程度上降低了用户速率增长速度，也影响了系统容量的提高。受到导频污染的影响，当用户数大于10时，随机导频分配方案的系统容量的增长幅度接近于零。用户分类方案以及SPA方案的上行可达和速率在用户数大于20 后就已经趋于饱和，而本文方案及文献[10]方案在用户数达到50时，仍然保持一定的增长幅度。

![](images/9c77b333d1de8d5293158177139a8059a8e3e8b1c500d557725382beecf7c928.jpg)  
图5上行可达和速率随小区用户数变化情况

# 4 结束语

本文提出了一种基于用户位置的导频分配方案。该方案在功率控制条件下，推导得到用户上行信干噪比公式，利用干扰用户到本小区基站距离与到目标小区基站距离的比值来定义干扰用户对目标小区中使用相同导频用户产生的导频污染强度，进而根据用户间导频污染强度来为用户分配导频。理论和相关仿真结果表明，所提方案能够显著提高用户的上行可达速率，并降低了用户间的性能差距，一定程度上提高了系统公平性。另外，本方案中测量用户到基站的距离的复杂度要低于计算用户到基站的大尺度衰落系数，更适用于实际的通信系统。

# 参考文献：

[1]Larsson E G,Edfors O,Tufvesson F,et al.Massive MIMO for nexi

generation wireless systems [J].IEEE Communications Magazine,2014,52 (2): 186-195.   
[2]LuL,Li GY,Swindlehurst AL,etal.An overview of massive MIMO: benefits and challenges [J].IEEE journal of selected topics in signal processing,2014,8(5): 742-758.   
[3]Zuo J,Zhang J,Yuen C,et al.Multicell multiuser massive MIMO transmission with downlink training and pilot contamination precoding [J]. IEEE Trans on Vehicular Technology,2016,65 (8): 6301-6314.   
[4]Yan X,Yin H,Xia M,et al.Pilot sequences allocation in TDD massive MIMO systems [C]/ Proc of Wireless Communications and Networking Conference.2015:1488-1493.   
[5]MüllerRR,Cottatellucci L,Vehkaperä M.Blind pilot decontamination [J]. IEEE Journal of Selected Topics in Signal Processing,2014,8(5): 773-786.   
[6]Yin H,Gesbert D,Filippou M,et al.A coordinated approach to channel estimation in large-scale multiple-antenna systems [J]. IEEE Journal on Selected Areas in Communications,2013,31(2): 264-273.   
[7]Zhu X,Wang Z,Dai L,et al. Smart pilot assignment for massive MIMO [J]. IEEE Communications Letters,2015,19 (9):1644-1647.   
[8] 方昕，张建锋，曹海燕，等．大规模 MIMO系统中动态导频分配[J]. 电子与信息学报,2016,38(8):1901-1907.   
[9]Zhu X,Wang Z,Qian C,et al.Soft pilot reuse and multicell block diagonalization precoding for massive MIMO systems [J]. IEEE Trans on Vehicular Technology,2016,65 (5):3285-3298.   
[10] Zhu X,Dai L,Wang Z.Graph coloring based pilot allocation to mitigate pilot contamination for multi-cell massive MIMO systems [J].IEEE Communications Letters,2015,19(10): 1842-1845.   
[11]杜嘉良，杨霖，宋新雷．大规模MIMO系统中基于用户位置信息的导 频分配[J].通信学报,2017,38(8):156-164.   
[12]宋新雷，杨霖，杜嘉良．联合时移和空间划分方法抑制大规模MIMO 导频污染[J].通信学报,2017,38(2):165-172.   
[13]何强，张秀军，肖立民，等．大规模MIMO系统中多小区导频重用对上 行可达速率的影响[J].清华大学学报：自然科学版,2015,55(5):526 531.   
[14]周志超，肖扬，王东.MassiveMIMO多小区系统中导频污染减轻方法 [J]．系统工程与电子技术,2016,38(2):434-441.   
[15] Jose J,Ashikhmin A,Marzetta TL,et al.Pilot contamination and precoding in multi-cell TDD systems [J].IEEE Trans on Wireless Communications, 2011,10(8):2640-2651.   
[16]Maiwald D,KrausD.Calculation of moments of complex Wishart and complex inverse Wishart distributed matrices [J].IEEE Proceedings-Radar, Sonar and Navigation,2000,147(4):162-168.