# 基于BDI-Agent模型的突发事件网络舆情应急响应建模研究

# 吴鹏1,2.3 金贝贝1,2.3 强韶华4

(南京理工大学经济管理学院南京 210094)  
2(江苏省社会公共安全科技协同创新中心 南京 210094)  
3(安全预警与应急联动技术湖北省协同创新中心武汉 430070)  
4(南京工业大学经济管理学院南京 211800)

摘要:【目的】基于“信念-愿望-意图"(BDI)模型分析网民在突发事件网络舆情中行为决策的动因和发展规律，引导网民情绪，建立复杂网络情境下可推理、可预测的应急响应计算模型。【方法】基于“信念-愿望-意图"模型建立起网络舆情演变过程中各类主体(网民、政府、媒体)的多 Agent交互模型，对网民的心智状态的转换过程建模仿真，从而揭示网络舆情演变的内在动因，支持应急响应策略的科学制定。本文以突发事件网络舆情中网民情感倾向性为核心，面向网民、政府、媒体的交互，设计 BDI-Agent 概念模型，包括 Agent 语境和推理规则设计；在此基础上设计实证模型，包括 Agent 属性、推理规则和交互规则设计，并结合实际案例进行验证。【结果】结合典型突发事件网络舆情案例进行实证研究，验证本文提出的多 Agent 模型的科学性。【局限】该模型需要更多同类事件的对比和优化。【结论】可以基于BDI模型将复杂的网络舆情映射为一个可以规约推理的计算模型，并为突发事件网络舆情演变趋势的预测和应急策略的制定提供一套可参考的实证模型。

关键词:突发事件网络舆情 应急响应“信念-愿望-意图"模型

分类号：C931 G350

# 1引言

在突发事件网络舆情中，网民希望从社交媒体(微博、微信)获取真相，分享信息和自己的情感[1]。政府如果不能采取有效的应急响应，采取干预措施，会让负面情绪主导网络舆情，影响政府公信力，目前虽然有研究者从公共管理的角度提出一些理论模型，例如Social-mediated CrisisCommunication Model[2]、Blog-mediated Crises Communication Modell3]，但是这些研究往往只关注如何管理社会媒体，大都基于对历史事件的分析统计和解释，采用宏观理论分析或微观模型设计的方法，进行静态分析，而不是从网民情感倾向性情况角度来测量和预测社会情绪的发展，缺乏动态性的连续观察和模拟，尤其是在现实社会和网络社会交互融合的复杂情境下，缺少能够映射网络舆情各类主体的仿真和预测模型[4]

1985年,Minsky在《心智的社会》一书中指出，复杂的群体行为是由多个具有交互性和自主性的智能体(Agent)在相互协调、相互合作的基础上涌现生成的[5]。Agent可以看作是那些宿主于复杂动态环境中，能够自主地感知环境中的信息，自主地采取行动，并能够实现一系列预先设定目标或任务的计算实体[5在突发事件中，具有不同偏好和行为习惯的网民个体，在与各网络媒介交互过程中，通过对网络媒介当时状态的感知，来获得、理解和判断各影响因素的综合作用，并依据感知的信息确定其行为，使其成为适应性的行动者[，因此网民就可以被抽象为具有感知性、协同性、交互性的智能体(Agent)。网民智能体在相互作用的同时受到其所在环境的影响进行自适应的感知、学习、决策，能够表现出符合真实社会群体特性的模拟效果。

“信念、愿望、意图"(Belief,Desire,Intention,BDI)模型理论是在Cohen 和Levesque 等对理性Agent进行形式化描述的研究中建立起来的三元认知结构，分别刻画了Agent 在信念、愿望和意图等方面的思维状态[7],可以适应Agent 在求解过程中环境多变且复杂的情况，实现理性的推理[8]。基于BDI模型可以建立起网络舆论演变过程中各类主体的多Agent 交互模型，对网民的心智状态的转换过程建模仿真，从而揭示网络舆情演变的内在动因，有效提高应急响应的效果。

本文面向突发事件网络舆情应急管理过程中网民群体行为特征，基于BDI模型研究网民群体在突发事件网络舆情演变过程中的"信念-愿望-意图”，进一步分析网民群体的感知行为、推理行为、决策行为、学习行为，形成基于BDI的突发事件网络舆情应急响应模型，并结合实际案例进行系统验证。

# 2 BDI模型

BDI 模型用拟人化的理念来刻画Agent，将信念(Belief)描述为Agent结合当前环境状态对自身能力的估计，包括 Agent 所拥有的知识和能力，作为 Agent的信息部件；将愿望(Desire)描述为Agent对未来环境状态的一种期盼，表达了Agent 希望达到或保持的一种状态，作为Agent的愿望目标部件；将意图(Intention)描述为Agent对将要实现目标和行动计划的确定和承诺，作为Agent的真实目标组件，直接驱动Agent的外部行为[9]。

与 BDI模型相关的研究工作代表性的成果包括:Cohen 和Levesque 基于正规模态逻辑对信念、目标、持续目标、意图以及理性的逻辑表达与演算问题进行系统研究[10]；Wooldridge 提出理性 Agent 的 BDI 模型结构及其实用推理过程[1]；Rao 和 Georgeff采用非线性的分支时态逻辑，基于三个基本的模态算子：信念、愿望和意图，建立起 Agent 的 BDI 模型等[12]。基于BDI-Agent的虚拟人群群体行为建模已应用于群体行为仿真中[13-15]，但在已有研究中，基于 BDI-Agent 在虚拟人群仿真的研究核心是Agent 的非通信行为，如导航或对象的操作，演练仿真中对虚拟人群的交互行为研究并不多见；另一方面，这些研究在系统具体化会话代理(Embodied Conversational Agent,ECA)领域重点研究 Agent 之间可信的交互行为[16-17]。在应用中使用基于BDI-Agent的虚拟人群通信行为，在显示其优势的同时带来了诸多挑战。

# 3 BDI-Agent概念模型设计

BDI模型为虚拟人群关键角色的会话行为提供了高效的工作流程转换认知模型，基于文献[18-19]研究的基础上，本文构建了突发事件网络舆情应急响应的BDI-Agent概念模型，如图1所示，包括两部分：面向不同主体感知的多Agent系统，实现Agent 决策的推理系统。

![](images/47e48a95b3df470d179799e736bb2aee76d17a53cb273ce6aec15de8a7e370f2.jpg)  
图1突发事件网络舆情应急响应的BDI-Agent概念模型

BDI-Agent结构由一系列相互关联代表思维模态的语境 $\langle \{ \mathbf { c } _ { \mathrm { i } } \} _ { \mathrm { i \in I } } , \Delta \rangle$ 组成，每个单元 $\mathbf { c } _ { \mathrm { i } } \in \{ \mathbf { c } _ { \mathrm { i } } \} _ { \mathrm { i \in I } }$ 是一个元组 $\langle { \bf L } _ { \mathrm { i } } , { \bf A } _ { \mathrm { i } } , \Delta _ { \mathrm { i } } \rangle$ ，其中 $\mathrm { L } _ { \mathrm { i } }$ ， $\mathbf { A } _ { \mathrm { i } }$ 和 $\Delta _ { \mathrm { i } }$ 分别定义了每一个语境逻辑的语言、公理和推理规则。 $\Delta$ 是语境之间的桥接规则集合，即推理前提和结论都属于不同语境的推理规则[19-20]

# 3.1 BDI-Agent模型语境设计

BDI-Agent被定义为具有多语境的结构，展现了一个多语境的分级BDI模型。主要思路就是采用权重来表示一个心理命题的肯定度(Certainty Degree)或愿望度(Desirability Degree)。多语境的分级 BDI-Agent主要由表征信念的语境(BeliefContext,BC)、表征愿望的语境(Desire Context,DC)、表征意图的语境(IntentionContext,IC)，以及表征计划的语境(PlanContext,PC)、表征交流的语境(Communication Context,CC)等功能性语境构成[17]。

(1）信念语境(BC):BC由属于信念逻辑命题组成,即如逻辑命题 $( \mathbf { B } _ { \gamma } , \mathbf { \beta } _ { \gamma } )$ ，其中 $\mathbf { B } _ { \gamma }$ 代表 Agent某种信念，$\gamma \in \mathrm { L } _ { \mathrm { D L } }$ 是动态逻辑命题, $\beta _ { \gamma } \in [ 0 , 1 ]$ 代表Agent信念的肯定度(Certainty Degree)[18,21]

(2）愿望语境(DC):DC 由属于愿望逻辑的命题组成,即如命题 $( \mathrm { D } _ { \gamma } ^ { * } , \delta _ { \gamma } ^ { * } )$ ，其中 $\mathbf { D } _ { \gamma } ^ { \ast }$ 代表Agent 的某种愿望$\gamma \in \mathrm { L } _ { \mathrm { D L } }$ 且 $\delta _ { \gamma } ^ { * } \in [ 0 , 1 ]$ 代表愿望度(Desirability Degree),$\ast \in \{ + , - \}$ 分别代表积极和消极的愿望，可以针对不同级别的偏好或排斥给积极和消极的愿望设置不同的愿望度[18]。

(3）意图语境(IC):IC由属于意图逻辑的动态命题组成，即如 $( \mathrm { I } _ { \gamma } , l _ { \gamma } )$ 的逻辑命题，其中 $\mathrm { I } _ { \gamma }$ 代表Agent 的某种意图, $\gamma \in \mathrm { L } _ { \mathrm { D L } }$ 并且 $l _ { \gamma } \in [ 0 , 1 ]$ 代表该意图的意图度(Intention Degree)[18]

(4)计划语境(PC)：在计划语境中允许Agent根据自己的愿望确定将被期望执行的行动的顺序[19]。PC由形如 $\mathrm { { p l a n } } ( \Sigma )$ 的公式组成，其中 $\Sigma$ 是一系列组成计划的动作[22]

(5）交流语境(CC):CC 是指不同Agent交流的环境[22]。CC 由形如 $( \operatorname { C } | \gamma )$ 的表达式组成，其中$\mathrm { C } \in \{ \mathrm { P } , \mathrm { O } \}$ ， $\mathrm { ~ O } _ { \gamma }$ 代表命题 $\gamma$ 已经被(Observed)，而 ${ \bf P } _ { \gamma }$ 表示 $\gamma$ 已经被Agent执行。因此，这些命题(例如 $\mathrm { P } _ { \gamma }$ )是由环境提供给 Agent 的输入， ${ \bf P } _ { \gamma }$ 表示与环境的交互[22]。

根据这种表示方法，给出方案 $\boldsymbol { \gamma }$ ， $\beta _ { \gamma }$ 表示分配给$\mathbf { B } _ { \boldsymbol { \gamma } }$ 的信任度； $l _ { \gamma }$ 表示 $\mathrm { I } _ { \gamma }$ 的意向性程度； ${ \delta } _ { \gamma } ^ { + }$ 表示希望$\mathrm { D } _ { \gamma } ^ { + }$ 发生的愿望度, ${ \delta } _ { \gamma } ^ { - }$ 表示不希望 $\mathrm { D } _ { \gamma } ^ { - }$ 发生的愿望度[23]

# 3.2 BDI-Agent模型推理规则设计

在认知层，Agent的功能包括通用功能和特定功能两个模块。Agent的通用功能是Agent 都具备并且在Agent之间可以共享的功能。Agent的特定功能指具备某些特定的知识和任务的Agent表现出来的行为，并且只能是特定的Agent才具有的功能。为了确定

BDI-Agent在系统中做出的不同类型的决定，现有的文献中定义了不同Agent语境的桥接规则。

推导具体愿望的桥接规则(图1中规则1)，该规则可以根据Agent 的信念将Agent抽象的愿望推导成更加现实的愿望：

$$
\small \frac { \mathrm { D C } : ( \mathrm { D } ^ { \ast } \phi , \delta _ { \Phi } ^ { \ast } ) , \mathrm { B C } : ( \mathrm { B } ( [ \hat { \sigma } ] ) \Phi , \beta _ { [ \hat { \sigma } ] \varphi } ) } { \mathrm { D C } : ( \mathrm { D } ^ { \ast } ( [ \hat { \sigma } ] ) \Phi , \mathrm { f } _ { \mathrm { D } } ( \delta _ { \Phi } ^ { \ast } , \beta _ { [ \hat { \sigma } ] \varphi } ) ) }
$$

通用的Agent愿望 $( \boldsymbol { \mathrm { D } } ^ { * } \boldsymbol { \Phi } , \delta _ { \varphi } ^ { * } )$ 推导出具体的愿望$( \mathrm { D } ^ { \ast } ( [ \hat { o } ] ) \varphi , \mathrm { f _ { D } } ( \delta _ { \varphi } ^ { \ast } , \beta _ { [ \hat { o } ] \varphi } ) )$ ，并且考虑到存在的能够实现的行动 $( \mathrm { B } ( [ \hat { o } ] ) \varphi , \beta _ { [ \hat { o } ] \varphi } )$ ，具体愿望的优先度(Preference Degree)取决于初始的期望度愿望 $( \delta _ { \boldsymbol { \Phi } } ^ { * } )$ 以及通过行动 $\hat { \sigma } ( \beta _ { [ \hat { \sigma } ] \varphi } )$ 实现该愿望的概率，通过函数$\mathrm { f _ { D } }$ 完成这两个值的计算，函数 $\mathrm { f _ { D } }$ 的定义与具体问题相关[23-24]。在本文中， $\mathrm { f _ { D } }$ 被定义为获得预期的满意度与厌恶的值的乘积。

从Agent的愿望中推导Agent意图的桥接规则(图1中规则2)，该规则从现有的可以实现的一组愿望中推导出 Agent意图:

$$
\begin{array} { r l } & { \mathrm { D C } : ( \mathrm { D } ^ { + } [ \hat { \sigma } ] \varphi , \delta _ { \mathrm { \tiny ~ [ \hat { \sigma } ] \varphi } } ^ { + } ) , \mathrm { D C } : ( \mathrm { D } ^ { + } \boldsymbol { \phi } , \delta _ { \boldsymbol { \phi } } ^ { + } ) , \mathrm { P C } : \mathrm { p l a n } ( \Sigma ) } \\ & { \mathrm { D C } : ( \mathrm { D } ^ { - } [ \hat { \sigma } ] \Psi _ { 1 } , \delta _ { \mathrm { \tiny ~ [ \hat { \sigma } ] \Psi _ { 1 } } } ^ { - } ) , \cdots , ( \mathrm { D } ^ { - } [ \hat { \sigma } ] \Psi _ { n } , \delta _ { \mathrm { \tiny ~ [ \hat { \sigma } ] \Psi _ { n } } } ^ { - } ) } \\ & { \frac { \hat { \sigma } \in \Sigma , ( \delta _ { \mathrm { \tiny ~ [ \hat { \sigma } ] \varphi } } ^ { + } + \delta _ { \hat { \sigma } } ^ { + } ) \gtrsim \sum _ { { \mathrm { k - } } 1 } ^ { { \mathrm { n } } } \delta _ { \mathrm { \tiny ~ [ \hat { \sigma } ] \Psi _ { k } ~ } } ^ { - } } { \mathrm { I C } : ( \mathrm { I } [ \hat { \sigma } ] \varphi , \mathrm { f } _ { \mathrm { I } } ( \delta _ { \mathrm { \tiny ~ [ \hat { \sigma } ] \varphi } } ^ { + } + \delta _ { \mathrm { \tiny ~ \varphi } } ^ { * } , \delta _ { \hat { \sigma } } ^ { + } , \sum _ { { \mathrm { k - } } 1 } ^ { { \mathrm { n } } } \delta _ { \mathrm { \tiny ~ [ \hat { \sigma } ] \Psi _ { k } } } ^ { - } ) ) } } \end{array}
$$

如果命题 $( { \delta } _ { [ \hat { v } ] \varphi } ^ { + } )$ 和行动 $( { \delta ^ { + } } _ { \hat { \sigma } } )$ 的愿望度都大于行动的负面影响值的总和 $\sum _ { { \bf k } - 1 } ^ { \mathfrak { n } } \delta _ { \ [ \hat { \sigma } ] \Psi _ { \bf k } } ^ { - }$ ，那么计划plan $( \Sigma )$ 中可以通过行动 $\hat { o }$ 实现的积极愿望$( \mathrm { D } ^ { + } [ \hat { \sigma } ] \boldsymbol { \varphi } , \delta _ { [ \hat { \sigma } ] \boldsymbol { \varphi } } ^ { + } )$ 将会产生一个新的意图$\mathrm { I C : ( I [ } \hat { \sigma } ] \Phi , \mathbf { f } _ { \mathrm { I } } ( \mathbb { \delta } _ { \mathrm { \ t } [ \hat { \sigma } ] \Phi } ^ { + } + \mathbb { \delta } _ { \Phi } ^ { * } , \mathbb { \delta } _ { \hat { \sigma } } ^ { + } , \sum _ { \mathrm { k } - 1 } ^ { \mathrm { n } } \mathbb { \delta } _ { \mathrm { \ t } [ \hat { \sigma } ] \Psi _ { \mathrm { k } } } ^ { - } ) )$ 。最终，函数$\mathbf { f } _ { \mathrm { I } }$ 包含了行动 $\hat { o }$ 所产生的正面和负面的影响[21-22]。在本例中 $\mathbf { f } _ { \mathrm { I } }$ 被定义为公式(3):

$$
\mathrm { f _ { I } ( a , b ) = \mathrm { m i n } ( a - b , l ) }
$$

从意图中导出Agent行动的桥接规则(图1中规则3)，该规则定义了 Agent 具有最大意图度 $( \mathrm { I } [ \hat { \sigma } ] \varphi , l _ { \mathrm { m a x } } )$ 的意图将要采取的下一个行动 $\left( \mathrm { P } \hat { o } \right) ^ { [ 2 3 - 2 4 ] } ;$ 。在本例中被定义为公式(4):

$$
\frac { \mathrm { I C : ( I [ \hat { \sigma } ] { \boldsymbol { \varphi } } , \boldsymbol { l } _ { \mathrm { m a x } } ) } } { \mathrm { C C : ( P \hat { \sigma } ) } }
$$

# 4实证模型设计

在BDI-Agent概念模型的基础上，结合突发事件网络舆情中网民、政府官方微博以及媒体三类主体,设计了突发事件网络舆情应急演练的实证模型，包括Agent属性设计、Agent推理规则设计、Agent交互规则设计。

# 4.1Agent属性设计

本研究将突发事件网络舆情应急指挥中的主体分成三类：个体网民Agent、媒体Agent、政府Agent。根据图1中Agent 的结构，三类 BDI-Agent 的属性如表1所示：

表1 Agent 属性  

<html><body><table><tr><td>个体网民 Agent</td><td>媒体 Agent</td><td>政府 Agent</td></tr><tr><td>①自身特性:</td><td>①自身特性：媒体</td><td>①自身特性：政府公</td></tr><tr><td>网民属性(Xi)</td><td>信度(R)、媒体广度</td><td>信力(C)、政府传播力</td></tr><tr><td>② 信念(BC)</td><td>(W)</td><td>(P)、政府议程设置引</td></tr><tr><td>③ 计划(PC)</td><td>② 信念(BC)</td><td>导力(S)</td></tr><tr><td>④ 愿望(DC)</td><td>③ 计划(PC)</td><td>②信念(BC)</td></tr><tr><td>⑤ 意图(IC)</td><td>④ 愿望(DC)</td><td>③ 计划(PC)</td></tr><tr><td>⑥ 交流(CC)</td><td>⑤ 意图(IC)</td><td>④ 愿望(DC)</td></tr><tr><td>? 情感(En)</td><td>⑥ 交流(CC)</td><td>⑤ 意图(IC)</td></tr><tr><td></td><td>? 情感(Em)</td><td>⑥ 交流(CC)</td></tr><tr><td></td><td></td><td>⑦情感(Eg)</td></tr></table></body></html>

# 4.2Agent推理规则设计

根据BDI-Agent 模型推理规则设计可得网民Agent、媒体Agent、政府Agent的推理规则，定义如下。

# （1）网民Agent

网络舆情突发事件中网民Agent 的信念度β由网民的网民属性决定(见表2)。将网民Agent的信念推理成具体愿望(见图2)，根据桥接规则2推理出网民Agent的意图(见图3)，生成网民Agent的行为意向(见图4)。

表2网民抽象愿望和信念以及计划  

<html><body><table><tr><td>名称</td><td>属性</td></tr><tr><td>抽象愿 望(DC)</td><td>(D+关注事件发展,1)</td></tr><tr><td>信念 (BC)</td><td>(B[支持政府行为,希望传播正能量]关注事件发展,βy1) (B[寻求事件真相，了解事件始末]关注事件发展,βy2) (B[怀疑政府行为，对政府不信任]关注事件发展,βy3)</td></tr><tr><td>计划 (PC)</td><td>PC:(plan(支持政府行为，希望传播正能量)) PC :(plan (寻求事件真相，了解事件始末))</td></tr></table></body></html>

愿望1: $\left( \mathbf { D } ^ { + } \right.$ 关注事件发展，1),(B[支持政府行为，希望传播正能量]关  
注事件发展, ${ \delta } _ { { \gamma } _ { 1 } } ^ { + }$ ）$\Rightarrow \mathrm { D C }$ . $\left( \mathrm { D } ^ { + } \right)$ [支持政府行为，希望传播正能量]关注事件发展，  
$\mathbf { f } _ { \mathrm { D } } ( 1 , \delta _ { \gamma _ { 1 } } ^ { + } )$ ）  
愿望2: $\mathrm { ( D ^ { + } }$ 关注事件发展，1),(B[寻求事件真相，了解事件始末]关注  
事件发展， ${ \delta } _ { { \gamma } _ { 2 } } ^ { + }$ ）$\Rightarrow \mathrm { D C }$ . $\left( \mathbf { D } ^ { + } \right.$ [寻求事件真相，了解事件始末]关注事件发展，  
$\mathrm { f } _ { \mathrm { D } } ( 1 , \delta _ { \gamma _ { 2 } } ^ { + } )$ ）  
愿望3: $\left( \mathrm { D } ^ { + } \right)$ 关注事件发展，1),(B[怀疑政府行为，对政府不信任]关注  
事件发展， $\delta _ { \gamma _ { 1 } } ^ { - }$ ）$\Rightarrow \mathrm { D C }$ . $\left( \mathbf { D } ^ { + } \right)$ [怀疑政府行为，对政府不信任]关注事件发展，  
$\mathrm { f _ { D } } ( 1 , \delta _ { \gamma _ { 3 } } ^ { - } )$ ）

意图1:DC： $\left( \mathbf { D } ^ { + } \right)$ [支持政府行为，希望传播正能量]关注事件发展，${ \boldsymbol { \delta } } _ { \gamma _ { 1 } } ^ { * }$ )，PC:(plan(支持政府行为，希望传播正能量), $\delta _ { \gamma _ { 1 } } ^ { * } > 0$ ）$\Rightarrow \mathrm { I C }$ (I[支持政府行为，希望传播正能量]关注事件发展， $l _ { \boldsymbol { \gamma } _ { \mathrm { _ { l } } } }$ ）意图2:DC: $\left( \mathrm { D } ^ { + } \right)$ [寻求事件真相，了解事件始末]关注事件发展， ${ \boldsymbol { \delta } } _ { \gamma _ { _ { 2 } } } ^ { * }$ ）PC:(plan(寻求事件真相，了解事件始末)， $\delta _ { \gamma _ { 2 } } ^ { * } > 0$ ）$\Rightarrow { \mathrm { I C } } :$ (I[寻求事件真相，了解事件始末]关注事件发展， $l _ { \gamma _ { _ { 2 } } }$ ）意图3:DC: $\left( \mathrm { D } ^ { + } \right)$ [寻求事件真相，了解事件始末]关注事件发展, $\delta _ { \gamma _ { 3 } } ^ { - }$ ）PC:(plan(寻求事件真相，了解事件始末)， $\delta _ { \gamma _ { 3 } } ^ { - } > 0$ ）$\begin{array} { r l } { \Rightarrow } & { { } \mathrm { I C } \mathrm { : } } \end{array}$ (I[寻求事件真相，了解事件始末]关注事件发展, $l _ { \gamma _ { 3 } }$ ）

<html><body><table><tr><td>IC:(I[支持政府行为，希望传播正能量]关注事件发展，lγ),</td></tr><tr><td>IC:(I[寻求事件真相，了解事件始末]关注事件发展，lγ),</td></tr><tr><td>IC:(I[寻求事件真相，了解事件始末]关注事件发展，l)</td></tr><tr><td>→ CC: (p),max</td></tr></table></body></html>

(2）媒体Agent

媒体Agent因其存在目的与自身发展的需要，它的愿望就是搜寻社会中的热点事件进行报道，以扩大自身影响力，获得更多的受众。媒体Agent 各个信念的信念度 $\beta _ { \gamma }$ 由媒体自身特性—媒体信度的效用函数R决定(见表3)。将媒体Agent的信念推理成具体愿望(见图5)，根据桥接规则2推理出媒体Agent的意图(见图6)，生成媒体Agent的行为意向(见图7)。

表3媒体Agent的抽象愿望和信念以及计划  

<html><body><table><tr><td>名称</td><td>属性</td></tr><tr><td>抽象愿望(DC)</td><td>(D+扩大自身影响力,1)</td></tr><tr><td>信念(BC)</td><td>(B[传达政府态度]扩大自身影响力，βyi) (B[反馈民意]扩大自身影响力，βy2)</td></tr><tr><td rowspan="2">计划(PC)</td><td>PC:(plan (传达政府态度))</td></tr><tr><td>PC:(plan (反馈民意))</td></tr></table></body></html>

愿望1:(D+扩大自身影响力,1),(B[传达政府态度]扩大自身影响力， ${ \boldsymbol { \delta } } _ { \gamma _ { 1 } } ^ { * }$ ）$\Rightarrow$ DC: $\left( \mathrm { D } ^ { + } \right)$ [传达政府态度]扩大自身影响力， $\mathrm { f } _ { \mathrm { D } } ( 1 , \delta _ { \gamma _ { 1 } } ^ { * } )$ ）愿望2:(D'扩大自身影响力,1),(B[反馈民意]扩大自身影响力， ${ \boldsymbol { \delta } } _ { \gamma _ { 2 } } ^ { * }$ ）$\Rightarrow$ DC: $\left( \mathrm { D } ^ { + } \right)$ [反馈民意]扩大自身影响力， $\mathrm { f } _ { \mathrm { D } } ( 1 , \delta _ { \gamma _ { 2 } } ^ { * } )$ ）

意图1:DC: $\mathrm { ^ { ( D ^ { + } } }$ [传达政府态度]扩大自身影响力， ${ \boldsymbol { \delta } } _ { \gamma _ { 1 } } ^ { * }$ ),PC: (plan (传  
达政府态度)， ${ \delta } _ { \gamma _ { 1 } } ^ { * } > 0$ ）$\Rightarrow { \mathrm { I C } } ;$ (I[传达政府态度]扩大自身影响力， $l _ { \gamma _ { 1 } }$ ）  
意图2:DC: $\left( \mathrm { D } ^ { + } \right)$ [反馈民意]扩大自身影响力， ${ \boldsymbol { \delta } } _ { \gamma _ { 2 } } ^ { * }$ ),PC:(plan (反馈民  
意）， $\delta _ { \gamma _ { 2 } } ^ { * } > 0$ ）$\Rightarrow { \mathrm { I C } } :$ (I[反馈民意]扩大自身影响力， $l _ { \gamma _ { 2 } }$ ）

<html><body><table><tr><td>IC:(I[传达政府态度]扩大自身影响力，),</td></tr><tr><td>IC:(I[反馈民意]扩大自身影响力，l)</td></tr><tr><td>⇒ CC :(po)， lmax</td></tr></table></body></html>

(3）政府Agent

政府以官方微博、微信为代表在社交媒体和网民、媒体交互，其抽象愿望、信念和行为计划如表3所示，BDI 结构应用的第一步就是根据规则1将政府 Agent的抽象愿望转化为具体符合现实的愿望(DC)(见图 8),政府Agent将根据已经存在的计划选择最切合实际的愿望转化为政府 Agent 的意图(IC)(见图9)。最终，政府Agent选择最期望的动作执行(见图10)。

表4政府Agent抽象愿望和信念以及计划  

<html><body><table><tr><td>名称</td><td>属性</td></tr><tr><td>抽象愿望(DC)</td><td>(D+社会稳定,1)</td></tr><tr><td>信念(BC)</td><td>(B[消极处理]社会稳定,βγ) (B[积极应对]社会稳定,βγ2)</td></tr><tr><td>计划(PC)</td><td>PC:(plan (消极处理)) PC:(plan (积极应对))</td></tr></table></body></html>

愿望1: $\mathrm { \Delta ^ { D ^ { + } } }$ 社会稳定,1),(B[消极处理]社会稳定, ${ \boldsymbol { \delta } } _ { \gamma _ { 1 } } ^ { * }$ ）$\Rightarrow \mathsf { D C }$ $\left( \mathrm { D } ^ { + } \right)$ [消极处理]社会稳定, $\mathrm { f } _ { \mathrm { D } } ( 1 , \delta _ { \gamma _ { 1 } } ^ { * } )$ ）愿望2: $\left( \mathrm { D } ^ { + } \right)$ 社会稳定,1),(B[积极应对]社会稳定， ${ \boldsymbol { \delta } } _ { \gamma _ { 2 } } ^ { * }$ ）$| \Rightarrow \mathrm { { D C } } \qquad |$ $\left( \mathrm { D } ^ { + } \right)$ [积极应对]社会稳定, $\mathrm { f } _ { \mathrm { D } } ( 1 , \delta _ { \gamma _ { 2 } } ^ { * } )$ ）

意图1:DC: $\left( \mathrm { D } ^ { + } \right)$ [消极处理]社会稳定， ${ \boldsymbol { \delta } } _ { \gamma _ { 1 } } ^ { * }$ ),PC:(plan (消极处理),  
${ \delta } _ { \gamma _ { 1 } } ^ { * } > 0$ ）$\Rightarrow { \mathrm { I C } } ;$ (I[消极处理]社会稳定, $l _ { \gamma _ { 1 } }$ ）  
意图2:DC: $\left( \mathrm { D } ^ { + } \right)$ [积极应对]社会稳定, ${ \boldsymbol { \delta } } _ { \gamma _ { 1 } } ^ { * }$ ),PC:(plan (积极应对),  
${ \delta } _ { \gamma _ { 1 } } ^ { * } > 0$ ）$\Rightarrow { \mathrm { I C } } :$ (I[积极应对]社会稳定, $l _ { \gamma _ { 1 } }$ ）

IC:(I[消极处理]社会稳定, $l _ { \gamma _ { 1 } }$ ),IC:(I[积极应对]社会稳定， $l _ { \gamma _ { 2 } }$ ）⇒CC:(p@)， lmax

# 4.3 Agent交互规则设计

(1）网民Agent之间的交互规则设计T时刻网民j对网民i的影响函数如下：

$$
\mathrm { f } ( \mathbf { j } , \mathbf { i } , \mathbf { t } ) = \left\{ \begin{array} { c c } { 0 } & { \frac { \left| \mathrm { E } _ { \mathrm { i } } - \mathrm { E } _ { \mathrm { j } } \right| } { \mathrm { E } _ { \mathrm { i } } } > p _ { \mathrm { l } } } \\ { \sqrt { \frac { \mathrm { D e s i r e } ( \mathbf { j } ) } { \mathrm { X } _ { \mathrm { i } } } } } & { \frac { \left| \mathrm { E } _ { \mathrm { i } } - \mathrm { E } _ { \mathrm { j } } \right| } { \mathrm { E } _ { \mathrm { i } } } \leqslant p _ { \mathrm { l } } } \end{array} \right.
$$

其中 $\mathrm { E _ { i } , \ E _ { j } }$ 分别为网民i和网民 $\mathrm { ~ j ~ }$ 的态度, $X _ { \mathrm { i } }$ ，Desire(j)为网民i的属性和网民j的愿望行为指数。如果二者的个体差异过大, $\mathrm { ~ j ~ }$ 不会对i产生影响，如果二者差异小于等于阈值 $\mathfrak { p } _ { 1 }$ 则会产生影响。 $_ { \mathrm { t } + 1 }$ 时刻，网民i的情感 $( \mathrm { E _ { i } } ) _ { \mathrm { t + 1 } }$ 为：

$$
( \mathrm { E _ { i } } ) _ { \mathrm { t + l } } = ( \mathrm { E _ { i } } ) _ { \mathrm { t } } + \mathrm { f } ( \mathrm { j } , \mathrm { i } , \mathrm { t } ) [ ( \mathrm { E _ { j } } ) _ { \mathrm { t } } - ( \mathrm { E _ { i } } ) _ { \mathrm { t } } ]
$$

(2）媒体Agent与网民Agent交互规则设计

根据媒体Agent的属性：广度、信度和报道情感，他们对网民情感有着正向的影响。t时刻，媒体 $\mathbf { m }$ 对网民i的影响函数为：

$$
\mathrm { { h } ( n , i , t ) = \left\{ \begin{array} { c c } { \mathrm { { b } _ { 1 } W \cdot R + b _ { 2 } i \big ( D e s i r e ( i ) \big ) + b _ { 3 } R } } & { \frac { \big | A _ { n } - A _ { m } \big | } { A _ { n } } \gtrsim p _ { 2 } } \\ { 0 } & { \frac { \big | A _ { n } - A _ { m } \big | } { A _ { n } } < p _ { 2 } } \end{array} \right. }
$$

其中,W、R分别为媒体n的广度和信度，Ei、Em分别表示网民与媒体的情感，Desire(i)为网民的愿望行为指数。 $\mathsf { b } _ { 1 } , \mathsf { b } _ { 2 } , \mathsf { b } _ { 3 }$ 为权重，取值可以根据实际情况调整，且 $\mathsf b _ { 1 } + \mathsf b _ { 2 } + \mathsf b _ { 3 } = 1$ 。当媒体的信度大于等于某一阈值 ${ \tt p } _ { 2 }$ 时会对网民产生影响。反之，不会产生影响。在 $\mathrm { t } + 1$ 时刻网民的情感和态度为：

$$
\mathrm { i ( E _ { n } ) _ { t + 1 } = i ( E _ { n } ) _ { t } + h ( n , i , t ) [ n ( E _ { m } ) _ { t } - i ( E _ { n } ) _ { t } ] }
$$

(3）政府Agent与网民之间的交互规则设计t时刻，政府主体 $\mathbf { g }$ 对网民i的影响函数为:

$$
\mathrm { d ( j , i , t ) = \left\{ \begin{array} { l l } { \displaystyle \frac { a _ { 1 } } { X _ { i } } + a _ { 2 } [ 1 - C _ { g } ] + a _ { 3 } [ 1 - S _ { g } ] + a _ { 4 } [ 1 - P _ { g } ] } & { \displaystyle \frac { \left| E _ { i } - E _ { g } \right| } { E _ { i } } \geqslant p _ { 3 } } \\ { \qquad } & { \displaystyle \frac { \left| E _ { i } - E _ { g } \right| } { E _ { i } } < p _ { 3 } } \end{array} \right. }
$$

其中, $\mathrm { \Delta X _ { i } }$ 为网民的网民属性, $\mathrm { E _ { g } }$ 为政府的态度, $\mathrm { C _ { g } }$ 、$\mathrm { S _ { g } }$ 、 $\mathrm { \Delta P _ { g } }$ 分别为政府 $\mathbf { g }$ 的公信力、传播力和议程设置引导力、政府传播力，当政府的公信力大于等于某一阈值时会对网民产生影响。反之，不会产生影响。在 $^ { \mathrm { t } + 1 }$ 时刻网民的情感为：

$$
( \mathrm { E _ { i } } ) _ { \mathrm { t + l } } = ( \mathrm { E _ { i } } ) _ { \mathrm { t } } + \mathrm { d } ( \mathrm { g } , \mathrm { i } , \mathrm { t } ) [ ( \mathrm { E _ { g } } ) _ { \mathrm { t } } - ( \mathrm { E _ { i } } ) _ { \mathrm { t } } ]
$$

# 5仿真系统实现与验证

# 5.1 系统设计

依据应急响应中网络舆情中的主体将角色分为策划人员、控制人员、评估人员、演练军官、演练指挥官、个体网民Agent、媒体Agent 以及政府Agent，本文从系统的需求分析中提取出系统建模中的用例以及角色与用例的关系如图11所示，系统建模实现的网络舆情主体类图如图12所示。

<<ext end>> 推理行动 演练执行 启动演练 控制人员 接突发事件报警 个体网民Agent (frc J e C se) (frcm \* Case) (frcm Ufe C=.-) (from Actors) (frcn Cue) <<include>> <<extend>> <<extend>> 4 Y <<ext end>> 吴吴 <<extend>> 媒体Agent BDI推理 执行演练命令 演练军官 演练总指挥 确定演练目标 报告突发事件 (from Actors) (frcq Use Case) (fr on Uεe Case) (from Actors) (from Actors) (frcn Use Case) 7 (frcn Use Care) 查询知识库 ? (fxon Use Case) <<include>> <Kinclude>> 义 V <<extend>> 大 <<include>> 演练结束与终止 政府Agent 心 调取物资 演练评估、 考核与惩罚 (frcm e Cue) 策划人员 (from Actors) (fron Use Care) (fron Use Case) (fron Use Case) <<extend>>: (from Actors) <<ext end>> 推理意图 2 W 1 (fron Use Ca) 推理现实愿望 演练记录 评估人员 文件归档与备案确定演练计划 (fron Use Care) (frcn Ure Care) (from Actors) (fr cn Use Case) (fron Use Care)

# 5.2 系统实现

在仿真实验中抽取漳州PX 爆炸(2015年4月6日-4月20日)相关的新浪微博舆情数据，新浪微博中所有涉及该事件的网民发贴、跟帖和评论在情感倾向性分析后[25-26]，结果数据在仿真过程中动态载入程序中进行仿真，其中在仿真界面设置可调节参数如图13所示，网络舆情发生后，在没有政府以及媒体介入的情况下，网民的情感倾向性如图14所示，根据对该事件过程中相关政府官方微博、微信内容的分析，政府态度的阈值区间是[0.27,0.7]，政府情感的阈值是[0.28,0.7]，媒体态度的阈值区间是[0.21,0.43]，媒体情感的阈值区间是[-0.55,0.26]。当政府Agent开始介人，开始设置政府态度为0.27，政府情感为0.28，经过一段时间后设置，政府态度为0.7，政府情感为0.7时，网民的情感倾向性变化如图15所示；当媒体介入，政府Agent不介入时，开始时设置媒体的态度和情感分别为0.21和-0.55，一段时间后调整媒体Agent的态度和情感为0.43和0.26,网民Agent的情感倾向性变化如图16所示。

网民Agent 关注者 政府AgentString 理oub元 ：String ： String String 敏感事件侦控能力：Double 反恐机制健全制度：Double  
被转/nteer 粉丝数：Inleger 显示原 4推意图 减力度：Doub1计算政府引导媒体Agent  
敬感信总发数：Inter 专业素质：Double计算命题信度R（)

![](images/1becf41a191ae4a7d6110d3dfe651f6fb89970f16bb1215875b572d13abc918e.jpg)  
图13仿真界面参数设置

![](images/96ddc7d835d0809184a1b2b87c5a8f2bad68c2def45cb0f1782c5acc72381e70.jpg)  
图14无政府和媒体介入下网民的情感倾向

![](images/2de031772cf63397b87a3e9685755a7da3e88255614ec53871d846ccca4deee7.jpg)  
图15政府介入前后网民情感倾向性变化趋势

![](images/e495365daec21555ab161f17c46237e77e42bb4b575e29f0d83872dd0448a942.jpg)  
图12 网络舆情主体类  
图16媒体不同介入方式网民情感倾向性变化趋势

从图14中的仿真结果可以看出，当政府Agent和媒体Agent没有介入时网民的正面情感和负面情感随着时间的增长不断上升，发帖数量的不断增加，中立情感的网民不断转化具有为正面和负面情感的网民。当网民对舆情事件的情感陷人焦灼状态时政府仍为消极处理的状态，网民的信念(BC)倾向于不相信政府行为，希望寻求事件的真相，网民情感倾向朝着负面发展，此时媒体Agent意图反馈民意，督促政府积极应对网络舆情事件。从图15可以看出，随着政府对待突发事件网络舆情的态度由消极处理变为积极应对时网民的情感倾向性朝着积极的方向发展。从图16可以看出，当媒体Agent的情感比较消极时，网民的情感倾向性朝着消极的方向发展，当媒体Agent的情感向正面转变时，网民的情感倾向性朝着积极的方向发展。在突发事件网络舆情应急指挥中可以通过观察多仿真的网民情感倾向性趋势做出应对措施，政府官微发布有效信息或者让媒体配合发布信息来达到消减网民负面情绪，进行舆情调节的目的。

# 6结语

本文基于BDI-Agent模型设计了突发事件网络舆情应急响应概念模型、实证模型，并结合实际案例进行系统设计和仿真，其理论贡献在于将复杂的网络舆情映射为一个可以规约推理的计算模型，其实践贡献在于为研究突发事件网络舆情演变趋势的预测和应急策略的制定提供一套可参考的实证模型。

当然，本文也有不足之处，例如仿真结果如何验证，大规模数据下不同Agent之间语义通信如何规约和解决，这也为未来的研究指出了新的挑战，一是在于结合统计方法和人工智能方法进行BDI规则在突发事件网络舆情领域的预测验证[24]，二是结合本体进行基于本体的 BDI语义推理[27]。

# 参考文献：

[1] Stephens KK,MalonePC.If the Organizations won't Give Us Information:The Use of Multiple New Media for Crisis Technical Translation and Dialogue [J]. Journal of Public Relations Research,2009,21(2): 229-239.   
[2] Jin Y,Liu B F.The Blog-mediated Crisis Communication Model: Recommendations for Responding to Influential External Blogs [J].Journal of Public Relations Research, 2010,22(4): 429-455.   
[3] LiuBF,Jin Y,Briones R,etal.Managing Turbulence in the Blogosphere:EvaluatingtheBlog-mediated Crisis Communication Model with the American Red Cross [J]. Journal of Public Relations Research,2012,24(4):353-370.   
[4] 王昌伟．网络危机信息传播机理与仿真研究[D].哈尔滨: 哈尔滨工程大学，2012.（Wang Changwei.Network Crisis Information Propagation Mechanisms and Simulation[D]. Harbin:Harbin Engineering University,2012.)   
[5] 岳峰，胡晓峰，李志强，等．多智能体涌现生成的群体行 为仿真[J]．系统仿真学报,2008,20(S):205-208.(Yue Feng, Hu Xiaofeng,Li Zhiqiang,et al.Generating Crowd Behavior Simulation from Multi-agent's Emergence[J]. Journal of System Simulation,2008,20 (S):205-208.)   
[6] DeAnaelis D L,Mooij W M. Individual-based Modeling of Ecological and Evolutionary Processes [J].Annual Review of Ecology Evolution & Systematics,2005,36:147-168.   
[7] Johnson WL,Beal C,Fowles-Winkler A，et al．Tactical Language Training System: An Interim Report [C]. In: Proceedings of the International Conference on Intelligent Tutoring Systems. Springer Berlin Heidelberg.2004: 336-345.   
[8]Oser R L.A Structured Approach for Scenario-based Training [C].In: Proceedings of the 43rd Annual Meeting of the Human Factors and Ergonomics Society， Houston,TX, USA.1999: 1138-1142.   
[9]Van Den Bosch K, Riemersma JB J.Reflections on Scenariobased Training in Tactical Command [A] .// Schiflett S,Elliot L,Salas E,et al. Scaled Worlds: Development, Validation and Applications [M].Burlington,VT: Ashgate Publishing,2004: 1-21.   
[10]Cohen PR,Levesque HJ. Intention is Choice with Commitment [J].Artificial Intelligence,1990,42(2-3): 213-261.   
[11] Wooldridge M. Reasoning about Rational Agents [M]. Cambridge,MA: The MIT Press,2003.   
[12] Rao A S, Georgeff M P. Decision Procedures for BDI Logics [J]. Journal of Logic and Computation,1998,8(3): 293-343.   
[13]Norling E,Sonenberg L.Creating Interactive Characters with BDI Agents [C]. In: Proceedings of the Australian Workshop on Interactive Entertainment IE 2004，Sydney，Australia. 2004: 118-209.   
[14] Magerko B,Laird J E.Towards Building an Interactive, Scenario-based Training Simulator [C]. In: Proceedings of the Behavior and Representation and Computer Generated Forces Conference.2002: 15-34.   
[15] Magerko B,Laird JE,Assanie M, et al. AI Characters and Directors for Interactive Computer Games [C]. In: Proceedings of the 16th Conference on Innovative Applications of Artificial Intelligence. AAAI Press,2004: 877-883.   
[16] Niewiadomski R,Bevacqua E,Mancini M,et al.Greta: An Interactive Expressive ECA System [C]. In: Proceedings of the 8th International Conference on Autonomous Agents and Multiagent Systems-Volume 2. International Foundation for AutonomousAgentsandMultiagent Systems, 2009: 1399-1400.   
[17]刘芳．基于过程本体的异质Agent协作技术研究[D]．长沙: 国防科学技术大学,2006.(Liu Fang.Research on Process OntologyBasedHeterogeneousAgentCooperation Technology [D]. Changsha: National University of Defense Technology, 2006.)   
[18]Casali A，Godo L，Sierra C.A Logical Framework to Represent and Reason about Graded Preferencesand Intentions [C]. In: Proceedings of the 1lth International Conference on Principles of Knowledge Representation and Reasoning.2008:27-37.   
[19] Criado N,Argente E,Botti V. Normative Deliberation in Graded BDI Agents [C]. In: Proceedings of the 8th German Conference，MATES 2010,Leipzig，Germany.2010,6251: 52-63.   
[20] Giunchiglia F, SerafiniL.Multilanguage Hierarchical Logics, or:How We can do without Modal Logics[J]. Artificial Intelligence,1994,65(1): 29-70.   
[21] Meyer J-JC.Dynamic Logic for Reasoning about Actions and Agents [A].//Logic-based Artificial Intelligence [M]. Springer US,2000: 281-311.   
[22]Casali A.On Intentional and Social Agents with Graded Attitudes [D].Universitat de Girona,2008.   
[23]Criado N,Argente E,Botti V. Rational Strategies for Norm Compliance in the n-BDI Proposal [C]. In: Proceedings of the COIN 2010 International Workshops，Toronto，Canada. Springer Berlin Heidelberg,2011:1-20.   
[24] Criado N,Argente E,Noriega P,etal.Human-inspired Model for Norm Compliance Decision Making [J]. Information Sciences,2013,245:218-239.   
[25]Das D,Bandyopadhyay S.Extracting Emotion Topics from Blog Sentences:Use of Voting from Multi-engine Supervised Classifiers [C]. In: Proceedings of the 2nd International Workshop on Search and Mining User-generated Contents. ACM,2010:119-126.   
[26]Paltoglou G, Gobron S,Skowron M,et al. Sentiment Analysis of Informal Textual Communication in Cyberspace [C].In: Proceedings of Engage 2010.2010:13-25.   
[27]Fonte F A M,Burguillo JC,Nistal M L.An Intelligent Tutoring Module Controlled by BDI Agents for an e-Learning Platform [J]. Expert Systems with Applications,2012,39(8): 7546-7554.

# 作者贡献声明：

吴鹏：提出研究思路，设计研究方案，论文起草;  
金贝贝：采集、清洗和分析数据，仿真实验;  
强韶华：指标体系设计、模型设计。

# 利益冲突声明：

所有作者声明不存在利益冲突关系。

# 支撑数据：

支撑数据由作者自存储,E-mail:wupeng@njust.edu.cn。  
[1]吴鹏.漳州PX爆炸(2015年4月6日-4月20日)新浪微博舆情原始数据.txt.原始数据，  
[2]吴鹏.漳州PX爆炸(2015年4月6日-4月20日)新浪微博舆情BDI模型仿真数据.txt.BDI模型仿真数据.

收稿日期:2016-06-12  
收修改稿日期:2016-07-15

# A BDI-Agent Based Model for Public Opinion Crisis Response

Wu Pengl2,3JinBeibei123QiangShaohua4   
1(School of Economics and Management, Nanjing University of Science &Technology, Nanjing 210094,China)   
2(Jiangsu Collaborative Innovation Center of Social Safety Science and Technology, Nanjing 210094, China) 3(Hubei Collaborative Innovation Center for Early Warning and Emergency Response Technology, Wuhan 430070, China) 4(School of Economics and Management, Nanjing Universityof Technology, Nanjing 211800, China)

Abstract:[Objective]This paperanalyzes the motivation and evolution of netizensbehavior in crises with the helpof the“Belief-Desire-Intention (BDI)”model to guide netizens’emotion,and then builds a computing model for crisis response in the complex network environment.[Methods]First, we designed a model for interaction among netizens, govermment and media in public opinion crisis to simulate the netizens’emotional changes,based on the BDI-Agent theoretical model.This modelcould reveal reasons for the changing of public opinion and help us create better crisis response strategies.Second, webuilt an experimental model with the Agent property,reasoning rules and interaction designs to examine the algorithm with real world cases.[Results]Our empirical study showed that the proposed model was feasible.[Limitations] More real world cases were needed to further optimize the new model.[Conclusions] The proposed BDI-agent model could map the complicated public opinion context to a reasonable computing model, which could help us predict the future development of the public opinion crises and design beter response strategy.

Keywords:Emergency affairsPublic opinion Crisis response Belief-Desire-Intention model

# CopyrightClearanceCenter宣布推出RightFind内容决策支持解决方案

Copyright Clearance Center于近日宣布推出其基于云的RightFind 内容决策支持(Content Decision Support,CDS)解决方案,这是一个易于使用的数据分析平台，可以帮助信息中心的管理者充分利用内容的使用情况数据，以在内容采购上做出明智的决策。

RightFind CDS 在综合使用数据和支出数据的基础上，利用预测分析和数据可视化技术，以及预算、预测和规划工具，形成了一个完整的解决方案，旨在为信息管理者的内容采购战略提供可操作的情报信息。

在信息中心的预算下调的压力下，信息中心管理者不得不证明其内容订阅、许可协议、令牌包和文献传递服务的商业价值。大多数出版商都为他们的期刊和信息管理人员提供COUNTER统计数据，以便他们为自己订阅的期刊生成报表并分析和证明其内容投资策略的正确性。这一手工操作过程可能需要数天至数周的时间，这些时间本可以更好地用于支持组织的研究需求。

RightFind CDS 是唯一一个能将平台细粒度统计数据和COUNTER统计数据进行结合，为信息中心管理员提供整个单位的内容使用和支出情况的解决方案。通过部署 RightFind CDS，信息管理员可以专注于更高价值的工作，并充分利用RightFind CDS来:

(1）通过挖掘汇总数据源，让用户能够在数秒内访问内容使用和支出情况;(2）快速轻松地创建演示文稿，用数据为利益相关者演示内容投资回报情况;(3）确定内容覆盖范围，发现内容使用趋势，并使用商业价值指标来展示信息中心在内容上的投资如何支持该组织的研  
究工作;(4)通过强大的能简化和自动化预算过程的预测和规划工具，来缩短年度预算周期。“我们的客户越来越依赖于数据和分析，来帮助他们证明自己的内容支出和投资策略的正确性。”Copyright Clearance  
Center产品和服务总监Lauren Tulloch说:“只需轻轻点击几下鼠标,RightFind CDS 就能使他们能够查看全球以及他们本单位  
的内容使用数据，并利用这些数据来讲述他们自己的内容投资回报故事。”(编译自:htp://ww.copyright.com/copyright-clearance-center-announces-launch-rightfind-content-decision-support-solutio/)

(本刊讯)