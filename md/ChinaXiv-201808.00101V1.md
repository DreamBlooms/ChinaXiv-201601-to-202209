# 社交网络中考虑不同传播概率上的谣言传播模型

王飞雪¹，李芳²

(1．重庆人文科技学院 计算机工程学院，重庆 401524;2.重庆大学 计算机学院，重庆 400044)

摘要：针对社交网络中的谣言传播的分析与控制问题，现有的谣言传播模型无法描述不同节点对谣言传播概率的影响，从而造成了谣言传播模型无法真实地描述现实社交网络中的谣言传播，进而影响了对网络中谣言传播的控制。针对这一问题，在 SIR传播模型的基础上考虑了谣言在不同节点之间的传播概率，并且分析了不同节点对传播概率的影响情况，从而建立了社交网络中考虑网络节点自身影响的谣言传播模型。最后，通过将改进的谣言传播模型与常用的SIR 模型进行对比，实验结果显示，提出的改进模型可以较快地控制网络中谣言的传播。

关键词：社交网络；谣言模型；信息传播；传播概率 中图分类号：TP391 doi: 10.3969/j.issn.1001-3695.2018.04.0286

# Rumor propagation model considering different propagation probability in social networks

Wang Feixuel, Li Fang2 (1.SchoolofComputer Engineering,Chongqing InstituteofHumanities&Technology,Chongqing401524,China;2.School of Computer Science, Chongqing University, Chongqing 40oo44, China)

Abstract: Asfortheanalysisandsuppressonofrumorpropagation insocialnetworks,theexistingrumorpropagationmodels can't describe the effectof diferent nodeson the probabilityof rumor propagation.Thus,the existing rumor propagation models can'ttrulydescribethespreadofrumors inthereal social network.Therebyitafects thesuppresionof rumor propagation insocial networks.To solvethis problem,thispaper studies therumorpropagation probabilitybetweendiffrent nodes basedon the SIR propagation model,andanalyzes the impactof different nodes onthe propagation probability.The rumor propagation modelthatconsidering the influenceof nodes isproposed forthe socialnetworks.Finally,therumor propagation modelproposed in this paper is compared with thecommonlyused SIR model.The experimentalresultsshowthat the improved model proposed in this paper can quickly suppress the rumor propagation in network.

Key Words: social networks; rumor model; information spreading; propagation probability

# 0 引言

基于互联网的社交网络涵盖以人类社交为核心的所有网络服务形式，它改变了当代人们的沟通方式和思维方式。在社交网络为人与人之间的沟通带来便利的同时，社交网络中出现的不实信息也为这种社交活动带来了困扰，称这类不实信息为网络谣言[1。网络谣言是指通过网络介质而传播的没有事实依据，并且带有攻击性或者目的性的话语。谣言传播具有突发性且流传速度极快的特点，从而给正常的网络交流带来不良影响。为了控制社交网络中谣言的传播，需要对网络中谣言的传播机制进行分析。谣言动力学[2通过动力学原理与数学方法相结合，来研究网络中谣言普及度随时间变化的规律。基于谣言动力学的研究方法，通过对网络中谣言的传播规律进行建模，从而得到对应的谣言传播模型是目前最常用的控制谣言传播的方法。

针对社交网络中的谣言传播，目前已经出现大量谣言传播模型对其传播机制进行分析和描述。由于社交网络不仅具有复杂网络的特点，同时还属于一种关系网络，这种关系是影响谣言传播的主要原因。因此，目前的谣言传播模型大都从社交网络中的社会关系来进行研究。比如，文献[3]在CSR 模型中的接受概率数学模型基础上，考虑个人接受阈值对接受概率的影响，从而改进了CSR模型的传播规则和传播动力学方程，使得更符合移动SNS上用户的使用习惯。文献[4]通过考虑具有正负影响的媒介效应、谣言接受信号叠加作用以及信任度的因素，提出一种基于谣言接受概率函数的谣言传播模型。文献[5]为了考虑意见领袖对谣言传播过程的影响,在传播模型SIR的基础上,构建考虑冬眠者被领袖传播者唤醒的微博谣言传播模型。这些研究都是从社交网络中个体本身的角度来分析对谣言的接受情况，虽然考虑了个体本身的影响，但是没有分析不同个体对谣言（主动）传播带来的影响，从而无法分析谣言在整个网络中的传播情况。

经典的SIR 传播模型可以对社交网络中的信息传播过程进行抽象描述[，因此被广泛应用于研究社交网络中的谣言传播。比如文献[7]基于SIR传播模型，在传统谣言模型中引入谣言正向感染及负向感染两个感染状态，提出了描述谣言传播的SPNR模型。文献[8]针对异质网络中暴露于谣言下的节点有可能以一定的速率成为被移除的节点（即不再相信谣言），提出一种SEIR谣言传播模型。文献[9]在对社交网络的网络结构和节点进行分析的基础上，在社交网络中引入热传播节点来表示具有高传播能力的网络节点，进而提出了基于改进SIR的信息传播模型。文献[10]在基于SIR 传播模型上研究了具有怀疑机制的谣言传播模型，提出了SIQR谣言传播模型，并对SIQR模型中的谣言真相传播率对谣言传播过程进行了数值模拟。以上工作虽然从不同的角度来分析网络节点类型对谣言传播的影响，但是仅针对几种典型的节点类型，而且同类型节点上的谣言传播都认为是同质的[11,12]，即谣言在同类型网络节点之间都以相同的概率进行传播。然而，这种假设在真实的社交网络中是不成立的[13]。这是因为在社交网络中不同个体（即比节点类型更小的粒度）在传播谣言时的传播效力通常是不同的[14]。

针对现实社交网络中不同节点之间的谣言传播概率是不同的这一现象，本文在最常用的SIR谣言传播模型的基础上，重点分析谣言在不同节点之间的传播概率，从而建立了社交网络中考虑不同传播概率的谣言传播模型。最后，本文通过将改进的谣言传播模型与常用的SIR模型进行对比，实验结果显示，本文提出的改进模型可以较快的控制网络中谣言的传播。

# 1 SIR传播模型

经典的SIR谣言传播模型[15]通常通过三类节点来表示社交网络中不同类型的个体：不知者(S)表示对谣言没有意识的节点；传播者(I)表示已经被谣言影响，并且散布谣言的节点；移除者(R)表示已经知道该信息属于谣言，从而不参与谣言传播的节点。

在 SIR传播模型中,如果一个传播者 $I$ 与不知者S接触，那么不知者S将以某一固定的概率 $\beta$ 变为传播者 $\boldsymbol { I } _ { \circ }$ 对于网络中的传播者 $I$ 来说，都将以某一固定的概率 $\mu$ 转变为移除者 $R$ 。SIR 谣言模型中不同类型节点之间的转换过程可以表示为以下的形式：

$$
\begin{array} { r l } { I + S \xrightarrow [ ] { } \beta } & { { } \xrightarrow [ ] { } I + I ; } \\ { I + R \xrightarrow [ ] { } \mu } & { { }  R + R ; } \\ { I + I \xrightarrow [ ] { } \mu } & { { }  R + I ; } \end{array}
$$

其中： $^ +$ 操作符表示两个节点之间具有接触行为， $I , \ S , \ R$ 分别表示社交网络中的传播者、不知者和移除者三类节点。

通过式（1）可以看出，SIR传播模型认为节点之间的谣

言传播或者恢复的概率都是固定的，这种传播模型无法表示不同个体对谣言传播能力的差异性。

# 2 改进的谣言传播模型

在社交动力学中，个体之间的行为模式大多数都是异质的，即并不是所有的个体都具有同样的倾向来说服其他人[16]。基于该事实，本文在SIR谣言传播模型的基础上进行了改进，提出了考虑不同传播概率的谣言传播模型。

# 2.1改进的传播模型表达公式

在社交网络的谣言传播中，如果某一个体原来没有接触过该谣言信息，那么通过与周围邻居接触交流，该个体就有可能变为听信谣言的人（即由不知者变为传播者），这种可能性与向该个体传播谣言的个体的影响力有直接关系，即不同的谣言传播者在传播谣言时，该谣言被相信的概率是不同的。另外，如果某一个体听信了谣言，那么该个体能否在下一时刻识别自己接受到的信息是谣言（即由传播者变为移除者）的概率也因人而异。针对社交网络中的这种现象，本文在式（1）中的谣言传播规则上同时考虑了节点在任意时刻 $t$ 从一种类型转变为另一种类型的概率。下面以网络中的任意一个节点 $x$ 为例来介绍改进的谣言传播模型中三类节点之间的转变过程。如下所示：

$$
\begin{array} { r l } & { S \left( t + 1 \right) = S \left( t \right) i _ { x } ( t ) , } \\ & { I \left( t + 1 \right) = I \left( t \right) r _ { x } ( t ) + S \left( t \right) \left[ 1 - i _ { x } ( t ) \right] , } \\ & { R \left( t + 1 \right) = R \left( t \right) + I \left( t \right) \left[ 1 - r _ { x } ( t ) \right] } \end{array}
$$

其中：s ${ \mathsf { S } } ( t ) ~ , ~ I ( t ) ~ , ~ R ( t )$ 分别表示节点 $x$ 在 $t$ 时刻上属于不知者(S),传播者 $( I )$ 和移除者 $( R )$ 状态的三种情况； $i _ { x } ( t )$ 表示节点 $x$ 在 $t$ 时刻仍然保持不知者状态的概率， $r _ { x } ( t )$ 表示节点 $x$ 在 $t$ 时刻仍然保持为传播者的概率。

从式（2）可以看出，如果节点 $x$ 在 $\mathbf { \chi } _ { t }$ 时刻处于不知者状态，那么在与邻居节点进行交互的过程中，该节点以 $i _ { x } ( t )$ 的概率继续保持不知者的状态，那么该节点变为传播者的概率为1-$i _ { x } ( t )$ ， $i _ { x } ( t )$ 的大小取决于周围邻居对谣言的传播能力。如果节点$x$ 在 $t$ 时刻处于传播者的状态，那么在下一时刻，该节点将以$r _ { x } ( t )$ 的概率继续保持传播者的状态（即继续听信谣言），那么该节点变为移除者的概率为1- $r _ { x } ( t )$ ， $r _ { x } ( t )$ 的大小取决于该节点对谣言的辨别能力。

# 2.2传播概率计算方法

下面介绍改进的传播模型中两个重要的概率：保持不知者状态的概率 $i _ { x } ( t )$ 和保持传播者状态的概率 $r _ { x } ( t )$ 。

在网络节点信息传播过程中，每个节点都是随机的与该节点周围的邻居节点进行交互。本文通过统一的形式来表示这种随机性，将节点 $x$ 与其一个邻居节点 $y$ 进行交互的概率表示为$\frac { A _ { y x } } { k _ { y } }$ 。其中 $k _ { y }$ 表示节点 $y$ 与其周围节点之间的交互频率， $\lvert A _ { y x }$ 表示节点 $y$ 与节点 $x$ 之间的交互频率。对于节点 $x$ 来说，它是否变为一个传播者的概率取决于它周围的邻居是否是传播者，以及该传播者对谣言的传播能力。假设节点 $x$ 在 $t$ 时刻被传播者 $y$ 进行谣言传播的概率为 $\beta _ { y }$ ，那么节点 $x$ 不会因为 $y$ 的传播而成为一个传播者的概率为 $[ 1 - \beta _ { y } \frac { A _ { y x } } { k _ { y } } I _ { y } ( t ) ]$ 。

如果节点 $x$ 处于传播状态，那么在与其邻居节点的交互过程中，该节点可能会因为邻居节点知道该信息属于谣言从而不再相信该谣言信息。我们将节点 $x$ 与能识别该谣言信息的邻居节点 $y$ 进行交互的概率表示为 $\frac { A v } { k \mathrm { ~ } }$ ，其中 $k _ { x }$ 表示节点 $\textbf { \em x }$ 与其周围节点之间的交互频率。对于节点 $x$ 来说，它是否变为一个恢复者（即不再相信该谣言）的概率取决于它周围的邻居是否是恢复者，以及该恢复者的影响力（即能否劝服传播者不再相信谣言）。假设节点 $x$ 在 $t$ 时刻被该恢复者节点唤醒不再相信谣言的概率为 $\mu _ { x }$ ，那么节点 $x$ 因为 $y$ 而不会成为一个恢复者的概率为 $1 - \mu x \ \frac { A v } { k x } R _ { y } ( t )$

# 3 仿真验证

为了验证本文提出的谣言传播模型的有效性，通过与经典的SIR谣言传播模型以及当今两种流行的基于SIR模型改进的方法进行比较，来验证改进的谣言模型中不同谣言传播概率对谣言控制的影响。这两种基于SIR改进的方法分别对应文献[7]中的 SPNR方法和文献[9]中考虑热传播节点的HSIR 方法。另外，为了便于描述，这里称本文提出的方法为SPSIR方法。

通过仿真网络中的节点表示社交网络中的个体节点，分别包括不知者I，传播者S和移除者 $R$ 三种类型。为了便于分析，在实验过程中只设定一个谣言传播者。在每一个时间步上，网络中所有节点同时交互进行信息传播。在仿真过程中，网络中的个体在每个时间步上只能影响其中一个邻居节点。另外，本文把网络中的谣言传播概率 $\beta$ 和传染者节点的恢复概率！均设置为0.5。对于经典的SIR传播模型来说，每个传播者在选择一个邻居节点进行交互时，都将以固定的概率（0.5）进行谣言传播。另外，对于两种改进的谣言传播模型（SPNR和HSIR）来说，热传播概率和怀疑概率分别设定为0.8和0.2。而对于本文提出的谣言传播模型，将在传播概率 $\beta { = } 0 . 5$ 和恢复概率$\scriptstyle { \mu = 0 . 5 }$ 的基础上，同时设置了两种传播概率：保持不知者状态的概率I和保持传播者的概率R。并针对这两种概率的不同设置分别做了两次实验：实验1中每个节点上的概率I和概率R分别在（0.2.0.5）和（0.8.1）上随机分布；实验2中每个节点上的概率I和概率R分别在（0.5.0.8）和（0.2.0.5）上随机分布。实验结果通过移除者在全网中所占的比例来表示网络中的谣言控制情况。最终的结果是通过运行50次的仿真得到的平均结果。实验结果如图1和2所示，其中横轴表示网络中的交互时间，纵轴表示网络中移除者节点在所有节点上的比例。

通过实验结果可以看出，本文提出的考虑不同传播概率的谣言传播模型比其他三种对比方法在控制谣言传播上具有显著的效果。这是因为本文提出的谣言传播模型考虑了不同网络节点在谣言传播上的不同可能性，而不是都按照固定的概率进行谣言传播。另外，其他两种改进的方法（SPNR和HSIR）虽然具有比经典SIR更好的效果，但是在两次实验中都比本文提出的SPSIR方法显示出较明显的劣势。这是因为这两种改进方法只是考虑节点类型（分别是热传播节点和怀疑节点）对谣言传播带来的影响，而无法更详细地表示每个具体节点对谣言传播带来的不同影响。

![](images/18c2ecd7a0e01dc8320f9b111438433cd78b6f390d0b96853651714796d20508.jpg)  
图1实验1结果

![](images/9fe25199733a5d959e26b25491c6953ca03e1789f4d367b2904d1e6646f02126.jpg)  
图2实验2结果

具体来说，当网络中的保持不知者状态的概率I较小时，并且保持传播者的概率R较大时，网络中的谣言控制所花费的时间较长，比如图1中当仿真了100个时间步后，网络中的移除者的比例为 $70 \%$ ，而SPNR、HSIR和SIR传播模型中的移除者的比例仅为 $5 5 \%$ 、 $4 0 \%$ 和 $30 \%$ ；另外，当网络中的概率I较大而概率R较小时，网络中的谣言控制所花费的时间较短，比如图2中当仿真了45个时间步后，网络中的移除者的比例可高达 $80 \%$ ，而 SPNR、HSIR和SIR传播模型中的移除者的比例仅为 $5 0 \%$ 、 $3 5 \%$ 和 $30 \%$ .从而说明本文提出的谣言传播模型对谣言控制有更好的效果。该效果与传播模型中保持不知者状态的概率成正比，与保持传播者状态的概率成反比。

# 4 结束语

针对社交网络中不同影响力的个体对谣言传播的概率不同的问题，本文基于SIR谣言传播模型进行了改进，使之通过考虑不同传播概率来描述社交网络中的谣言传播动力学。分析了不同节点对传播概率的影响情况，从而建立了社交网络中考虑网络节点自身影响的谣言传播模型。本文通过将改进的谣言传播模型与常用的SIR模型进行对比，实验结果显示，本文提出的改进模型可以较快的控制网络中谣言的传播。

# 参考文献：

[1]Zhai Min.The generation mechanism of internet rumors-based or consideration of information philosophy [C]// Proc of the IS4SI Summit

Digitalisation for a Sustainable Society. 2O17:114.   
[2]Singh A, Singh Y N.Rumor dynamics and inoculation of the nodes in complex networks [Cl// Complex Networks and their Applications.2014: 132.   
[3] 杨云鹏，樊重俊，杨坚争，等．基于官方信息控制的多层网络谣言传播 模型[J]．计算机应用研究．2018，35(5)：1294-1297，1314.（Yang Yunpeng,Fan Chongjun, Yang Jianzheng,et al. Rumor propagation model on multilayered interconnected complex networks based on official information driven [J].Application Researchof Computers.2018,35 (5): 1294-1297,1314.)   
[4] 廖列法，孟祥茂，吴晓燕，等.微信社交网络上CASR 谣言传播模型研 究[J].小型微型计算机系统,2016,37(1):110-113.(Liao Liefa,Meng Xiangmao Liu Yongshan,et al.Research of CASR rumor propagation model on WeChat social network [J].Journal of Chinese Computer Systems.2016,37(1): 110-113.)   
[5]张志花，夏志杰，葛涛，等．基于唤醒机制的微博谣言传播模型[J]. 现代情报,2015,35(3):28-33.(Zhang Zhihua;Xia Zhijie,Ge Tao,et al. Rumor spreading model based on mechanism in micro-blog [J]. Journal of Modern Information,2015,35 (3): 28-33.   
[6]熊熙，胡勇．基于社交网络的观点传播动力学研究[J].物理学报, 2012,61 (15):104-110.(Xiong Xi, Hu Yong.Research on the dynamics of opinion spread based on social network services [J].Acta Physica Sinica, 2012, 61 (15): 104-110. )   
[7]薛一波，鲍媛媛，易成岐.SPNR:社交网络中的新型谣言传播模型[J]. 信息网络安全，2014(1):5-9.(Xue Yibo,Bao Yuanyuan，Yi Chengqi. SPNR:a novel rumor propagation model on social networks [J]. Netinfo Security,2014 (1): 5-9.)   
[8]Liu Qiming，Li Tao,Sun Meici.The analysis of an SEIR rumor propagation model on heterogeneous network [J].Physica A: Statistical Mechanics and its Applications,2017,469: 372-380.   
[9]李可嘉，王义康．改进 SIR 模型在社交网络信息传播中的应用[J].电

子科技，2013,26(8):168-171.(Li Kejia,Wang Yikang.Application of

improved SIR model in social network information communication [J]. Electronic Science and Technology,2013,26 (8): 168-171.)   
[10]王筱莉，赵来军．社会网络中具有怀疑机制的谣言传播模型[J].上海 理工大学学报,2012,34(5): 424-428.(Wang Xiaoli, Zhao Laijun. Rumor spreading model with skepticism mechanism in social networks [J]. Journal of University of Shanghai for Science & Technology,2O12,34 (5): 424-428. )   
[11]Pastor-Satorras R,Castellano C,Van Mieghem P,et al.Epidemic processes in complex networks [J].Reviews of Modern Physics,2015,87(3): 925.   
[12] Haddon L.The social dynamics of information and communication technology [M]. Routledge,2016.   
[13]张永，和凯．一种基于邻居节点间相互影响和改进概率的社交网络信 息传播模型[J].计算机应用研究.2018，35(3):755-759,764.(Zhang Yong,He Kai. Information propagation model with improved probability based on influence of neighbors for social network [J].Application Researchof Computers.2018,35(3):755-759,764.)   
[14]吴信东，李毅，李磊．在线社交网络影响力分析[J].计算机学报，2014, 37(4):735-752.(Wu Xindong,Li Yi,Li Lei. Influence analysis of online social networks [J]. Chinese Journal of Computers．2014，37(4): 735-752.)   
[15] Huang Chuangxia,Cao Jie,Wen Fenghua,et al.Stability analysis of sir model with distributed delay on complex networks [J].PloS One,2016,11 (8): e0158813.   
[16]张子柯．在线社交网络信息传播机制与动力学研究综述[J].情报学报， 2017,36 (4):422-431.(Zhang Zike.Mechanisms and dynamics of information spreading on online social networks: a state-of-the-art survey [J].Journal of the China Society for Scientific and Technical Information. 2017,6 (4): 422-431. )