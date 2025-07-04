# 利用一种新的类脑人工神经网络实现恐惧学习和经典条件反射学习

位东涛1\*，王国清²（1.西南大学心理学部，认知与人格教育部重点实验室，重庆北碚，400715;2.云南昆明，650000)

摘要：神经科学对人工智能有很大的启发作用，通过借鉴上述学科的研究成果，我们设计了一种新的人工神经网络来对人脑内的杏仁核进行模拟。人工神经网络包含长时记忆网络和激活网络两个部分，记忆网络记录了发送信号和接收信号的神经元以及二者之间的权重，激活网络则记录了发送信号和接收信号的神经元及其信号发送的时间点。激活网络仅保留了事件发生时的一小段记忆，并会根据设定好的规则修改长时记忆网络中的权重。利用此类方法，我们成功地让智能体拥有了恐惧情绪学习和经典条件反射式学习的能力，这与生物体内杏仁核的能力非常类似。

关键词：类脑人工神经网络；杏仁核；恐惧情绪；恐惧条件反射；SDTP

# Using a new brain-like artificial neural network to realize fear learning and classical conditioning

Abstract: Neuroscience have great inspiration for artificial intelligence.By drawing on the research results of these disciplines,we designed a new artificial neural network to simulate the amygdala in human brain. The neural network consists of two parts,a long-term memory network and a activation network. The memory network records the neurons sending and receiving signals and the weight between them，while the activation network records the neurons sending and receiving signals and the time point when the signals were sent. The activation network retains only a short time memory of the event and modifies the weights in the long-term memory network according to the set rules. Using this approach, we have successfully endows the agent the ability of fear emotion learning and classical conditioning learning, which is very similar to the ability of amygdala.

# Keywords: brain-like artificial neural network; amygdala; fear; fear conditioning; SDTP

# 作者简介：

通信作者：位东涛，博士，副教授，研究方向为焦虑和恐惧情绪的神经基础及计算机模拟（E-mail:dongtao @ swu.edu.cn）。  
共同第一作者：王国清，硕士，毕业于西南大学心理学部，目前研究方向为神经科学与人工智能的结合(E-mail: wgg_wgq@163.com）。

# 1引言

人类的大脑大约有860 亿个神经元[1]，每个神经元都做着简单的工作：接收信息；按照简单的规则作出"决定”；将信息发送出去。但正是由这些简单的神经元组成的神经网络让人类拥有了多种能力，例如情感、创造力、语言和思维等。

在人工智能的研究中，构建一个与生物神经元类似的人工神经元模型，并将其组成人工神经网络（artificial neural networks，ANNs)，用其实现智能是一个重要的方向。最早尝试在计算机上模拟生物神经元的是神经科学家麦卡洛克和数学家皮兹，，他们在1943年提出了人工神经元最初的模型[2]（MP 模型)，MP 模型及其随后的不同种类改进型[34模拟了生物神经元很多重要的特点，例如神经元可以接收和发送信号、信号会受到神经元之间联结强度的影响、联结强度可以改变等。但在关于神经元之间的联结是如何改变的问题上，人工神经网络却与生物神经网络有着很大的区别，在人工神经网络（监督学习类）中，权重改变的方向是降低预测值与真实结果的之间误差[5]，这种算法与时间无关。但在生物大脑的神经网络中，不同神经元之间权重的调节却与时间因素密切相关[6-9]，例如当神经元在某个时间点处于放电状态时，会对与其连接并处于激活状态的突触产生影响，如果突触的激活早于神经元的放电，那么此突触就会被增强，反之，突触就会被削弱，这类效应被称为脉冲时间依赖的突触可塑性[9]（Spike-Timing-Dependent Plasticity，SDTP）。1997 年提出的脉冲神经网络[10]（Spikingneural networks，SNNs）包含了时间要素。在脉冲神经网络中，神经元发送的是一种包含时间信息的离散信号，也因此而言，脉冲神经网络具备了模拟 SDTP的能力[11-16]。

无论是ANNs还是SNNs，强调的均是人工神经元与生物神经元的相似性，而忽略了神经网络层面上与生物体的相似性，然而不同物种的智力差异却可能来自于神经网络不同[17,18]，而非神经元的差异。这里我们提出了一种新的神经网络的表达方式，这类神经网络更加强调与生物大脑内神经网络的相似性。借助此类神经网络，我们模拟了大脑中一个特殊的神经结构——杏仁核（amygdala）。

多方面的证据表明杏仁核是恐惧情绪记忆和恐惧经典条件反射的学习中心。例如，向实验动物呈现威胁物时会激活杏仁核，相反，如果杏仁核遭受到损伤，动物将不会有害怕的表现[19,20]。正常的猴子面对蛇类通常会露出胆怯，但杏仁核损伤的猴子却没有[21]。在人类身上，杏仁核损毁的患者不仅难以识别恐惧表情[22],也会影响到恐惧经典条件反射的学习[23]，脑成像发现，恐惧经典条件反射的学习通常需要激活杏仁核[24]。

我们发现，拥有了此类神经网络的智能体能够表现出恐惧情绪学习和经典条件反射式的学习能力，这与杏仁核的功能非常类似。

# 2 实验设计

# 2.1模拟场景及智能体的设计

为了模拟智能体（agent）在真实场景中的情况，我们首先利用 python 语言中的tkinter包来设计模拟场景，模拟场景为一个 $1 2 \times 1 2$ 的方阵，每格50个像素。

智能体的主体是 $3 0 \times 3 0$ 像素的矩形，并具备四个方向的触手，触手用于模拟智能体的感觉器官，其功能是可以使其感知周边一格范围内物体的颜色。

设置两个物体，分别是红色的威胁物和灰色的中性物。当且仅当威胁物与智能体的主体在同一方格中时，威胁物会对智能体造成伤害，但中性物无论何时都不会对智能体造成伤害。实验条件与现实世界中类似，尽管威胁物可以对智能体造成伤害，但智能体需要通过学习才能获取这类经验。

智能体受到伤害或者感受到威胁时，便会逃开，每次能够跳跃三格。

![](images/bc6226c222bf348a9a824719623e6c1d609997f436aa0cf9206257d4372c8cb5.jpg)  
图1智能体、威胁物和中性物的设置

2.2智能体内神经元和神经元网络的设计（1）杏仁核特性及其神经联结

在本次实验中，我们模拟了大脑内一个特殊的脑结构——杏仁核。在恐惧情绪学习以及经典条件反射式的学习中，杏仁核扮演了重要的角色[25-27]。

杏仁核由大约12个神经核团组成，与恐惧最为相关的是三个神经核团[28.29],包括外侧核（lateral amygdala）、基底核（basal nuclei）和中央核（central nucleus），外侧核与大脑皮层所有的区域均有神经联系，负责接收感知到的信息[29-32]，其神经元会投射至基底核，并由基底核进一步投射至中央核[25.33]。中央核负责情绪的执行，其神经元会投射至下丘脑（hypothalamus）、腹侧被盖区（ventral tegmentalarea）以及位于脑干的蓝斑核（locuscoeruleus）等更低级的脑区，这些脑区分别与交感神经等自主神经成分，生物的行为成分以及激素成分有关，其中行为成分负责生物体恐惧反应行为（僵化、逃避等)，自主成分（血压升高、心率上升等）和激素（肾上腺素分泌等）成分则为行为成分作出支撑[2，如图2。

![](images/9267ba97fca6e1fed48875f2b65d473d9781b7c115a53f612a663cf24ab47f39.jpg)  
自主神经成分  
图2杏仁核的神经联系简图

# （2）杏仁核中存在的学习过程

生物大脑中的突触会被其活动所修饰，这类变化通常会被认为是生物学习和记忆的基础。由神经元活动引起的突触变化有一个显著的特点是时间上的不对称性，当某个神经元处于激活状态时，会产生两种截然相反的效果，一方面会对在其之前激活的突触产生强化作用，另一方面，会对在其之后才激活的突触有抑制作用[6-9]，即脉冲时间依赖的突触可塑性（SDTP)。

尽管并未有明确的证据显示杏仁核中存在着SDTP式的学习，但一些实验发现恐惧学习和恐惧经典条件反射学习往往会增强感觉神经元与杏仁核外侧核神经元之间的突触联结[34-38]，说明二者的关系十分密切。

# （3）杏仁核的神经网络模型

正如上面所述，很多证据表明感知神经元与杏仁核神经元之间突触的强化与恐惧学习和经典条件反射学习之间强烈相关[34-38]，然而目前为止，尚未有一种模型可以说明为什么二者会有如此有趣的关系。

关于经典条件反射的模型有很多[39-41],这些模型试图用统一的数学模型来解释实验发现的经典条件反射现象，但由于未将模型置于某个具体的神经网络，因此很难说明为什么突触变化会导致生物行为的具体变化。这里我们提出了一种新的模型，用于解释杏仁核突触的变化与生物体之间行为的关系。

# $\textcircled{1}$ 恐惧学习的原理探讨

恐惧情绪在生物体的进化当中起了非常大的作用，经过恐惧学习后，生物体会对曾经伤害过自己的物体形成逃避反应，这种在伤害来临前提前逃避的做法会减少生物体遭到重复攻击的可能性，从而提高其生存几率。

为了更好地说明杏仁核的模型，我们先设想一个典型的恐惧学习的场景：

一只新生的猴子从未见过蛇类，所以在其偶尔看到蛇后，并不感到害怕，也不会逃避，所以这只猴子被蛇攻击，并感到疼痛，产生回避反应（逃跑)。

通过这次事件，这只猴子产生了学习，学习的结果是猴子再次看到蛇会感到恐惧，并立即逃避，逃避行为避免了猴子再次遭受到蛇的攻击。

以下模型解释了上述恐惧学习的场景，如图3所示。

![](images/6ea78a92a603ea74e6b7ef8ce9a46e80d51063a4b0fe5554bfffef419ea5a955.jpg)  
图3恐惧学习的神经网络模型

左图为猴子学习之前杏仁核的神经网络，右图为学习之后的神经网络。

t代表猴子视觉系统感知到蛇的时间点，此时感知神经通路至杏仁核的神经通路（神经通路 $\alpha$ ）被激活，但由于这条神经通路未经强化，因此感知神经元并不会激活杏仁核，所以也难以激活神经通路γ，引发逃避反应。

t代表猴子感知到疼痛的时间点，此时疼痛神经元至杏仁核的神经通路（神经通路 $\beta$ ）被激活。通常疼痛会引发杏仁核的强烈放电[42]，所以我们假设这条神经通路无需强化便可以引发逃避反应。

t代表神经通路 $\gamma$ 激活的时间点，此时杏仁核神经元的激活引起了猴子的逃避反应。

通常情况下，猴子是先看到蛇，后被攻击，因此存在时间关系， $\mathbf { t } _ { 1 }$ 早于 $\mathbf { t } _ { 2 }$ $\mathbf { t } _ { 2 }$ 早于 $\mathbf { t } _ { 3 }$ 。其中 $\mathbf { t } _ { 1 }$ 和 $\mathbf { t } _ { 2 }$ 之间的时间差代表了猴子由看到蛇类至受到蛇类攻击的时间。

由于视觉感知神经元和痛觉神经元均投射至杏仁核神经元，因此当杏仁核神经元被激活时，根据 SDTP的学习规则，会导致激活时间更早的神经通路 $\mathfrak { a }$ 得到强化，于是产生了学习。

在学习之后，神经通路 $\mathfrak { a }$ 受到强化，因此当猴子的视觉感知系统再次被蛇激活，就会引发杏仁核神经元的激活，并进一步引起逃避反应，由此猴子便避免了遭受到蛇的再次攻击，所以图3右半部分中的 $\mathbf { t } _ { 2 }$ 是一个假设的时间点（图中用红色框覆盖）。

t与 $\mathbf { t } _ { 1 }$ 的时间差代表了猴子大脑中感知到蛇并开始逃避的时间，而t2与ti的时间差则代表了在客观世界中，猴子看到蛇至受到蛇攻击的时间，通常情况下，$\mathbf { t } _ { 3 }$ 与 $\mathbf { t } _ { 1 }$ 的时间差要更短，所以恐惧学习能够增加猴子在面对蛇时的生存几率。

$\textcircled{2}$ 经典条件反射的原理探讨

恐惧型经典条件反射实验通常设置一个条件刺激(conditioned stimulus,CS）和非条件刺激（unconditioned stimulus，US）。

经典条件反射训练之前，条件刺激并不会引起生物的逃避反应，而非条件刺激会引起逃避反应，训练时条件刺激与非条件刺激多次配对出现，训练后生物体学会条件刺激出现时作出逃避反应。

![](images/b503918a925d00823972a6383fd336025d729626ab3f5525134998a02e7121f0.jpg)  
图4恐惧型经典条件反射

与神经元STDP的现象非常类似，行为学研究发现，在恐惧型经典条件反射的训练中，时间因素非常重要，条件刺激必须要出现在非条件刺激之前或同时出现，相反，如果条件刺激出现在非条件刺激之后，则生物永远无法学会经典条件反射[43]，所以一些研究者认为条件刺激其实是起到了一种预警的作用[44]。由此看来，经典条件反射与与恐惧学习非常类似，略有不同的是，由于US和CS 均是感觉信息，所以模型中的信号均来自于感知神经元。如图5所示，对于经典条件反射来说，不同时间被激活的均是感觉信息，其中 $\mathbf { S } _ { 1 }$ 是条件刺激（CS）， $\mathbf { S } _ { 2 }$ 是非条件刺激（US）。

![](images/8680bbe8c48b6dec9ee5989d32b8fcaec00f4e9870bec765de36dd4492766865.jpg)  
图5经典条件反射的神经网络模型

$\textcircled{3}$ 习惯化和经典条件反射的消退

在真实的世界中，无论是恐惧学习还是经典条件反射均是动态和可逆的。

与恐惧学习相反的效果叫做习惯化（habituation)，习惯化是指生物体逐步习惯无害刺激，并减少逃避反应。对于本次恐惧学习而言，习惯化是指一个之前曾对智能体造成过伤害的物体此后多次出现且不再造成伤害，智能体逃避反应逐步消失的过程。

与恐惧经典条件反射学习相反的效果叫消退，当一个条件刺激单独出现多次，且智能体并未感知到随后将会出现对其造成伤害的非条件刺激时，生物体会逐渐失去对于条件刺激的逃避反应。

与之前的强化相反，这两种效果可能来自于神经通路权重的降低。

$\textcircled{4}$ 杏仁核的神经网络模型

综合上面关于恐惧学习和经典条件反射的原理，并结合杏仁核神经联结，我们设计了与杏仁核类似的神经网络模型，如图6。

![](images/f9c3670ef5464ac9860f94cb8486022018c5538780a23dccd06a21083889eb3f.jpg)  
图6恐惧记忆网络的设计

所有的感知神经元均投射至杏仁核，其中也包括痛觉神经元。与其他感知神经元不同的是，痛觉神经元与杏仁核神经元之间的联系更强(图中表示为实线）。此外，杏仁核神经元的激活会直接导致智能体产生逃避反应。

# （4）神经元以及神经网络设计

为了模拟智能体在真实环境中的表现，我们首先对智能体的感知进行了模拟。

$\textcircled{1}$ 智能体感知能力的模拟

智能体有两种感觉能力，其一为利用触手感知外界物体颜色的能力，这意味着一旦威胁物或者中性物与触手接触，便会激活智能体的感知神经元。

其二为感知痛觉的能力，当威胁物的位置与智能体的主体重合时，智能体便会受到伤害，此时智能体的感知神经元会被激活。

在人类的大脑中，按照时间的长短，记忆通常分为感觉记忆、短时记忆和长时记忆[45]。感觉记忆（sensory memory）又称感觉登记（sensory register)，其保留时间非常短（视觉感觉记忆大约为 50ms [46.47]，听觉感觉记忆约为 $\mathrm { 1 } { \sim } 2 \mathrm { s } ^ { \left[ 4 8 , 4 9 \right] } ,$ )’但可以保留大量的信息，多数的感觉记忆在超过保留时间后均被摒弃，只有那些经过注意的信息才能得到进一步的加工，从而进入短时记忆，并进一步进入长时记忆。受此启发，我们设置两个网络，分别代表类似长时记忆的网络（称为恐惧记忆网络)，和类似感觉记忆的网络（称为激活网络)，恐惧记忆网络用于保留智能体的长时记忆，而激活网络的作用是智能体面对某个事件时存储感觉记忆。

$\textcircled{2}$ 恐惧记忆网络的设计

恐惧记忆网络用来模拟未经历事件之前生物体大脑内稳定的神经网络。正如图6所示，一个类杏仁核神经网络包括杏仁核神经元，感知神经元（包括痛觉神经元）以及杏仁核激活会引起的逃避反应。

我们设置了初始的神经连接权重，其中痛觉神经元与杏仁核神经元的投射权重设置为3，其余感觉神经元的连接权重为1。

利用python语言中的pandas 包对记忆神经网络进行描述，内容包括三方面的内容：信号发起神经元，信号接收神经元以及它们之间的连接权重。在最初的神经网络中，我们仅设置了痛觉神经元与杏仁核神经元之间的联结。

我们采用了一种特殊的方法来表达其余感觉神经元投射至杏仁核神经元时联结：当智能体感知到刺激时，会首先到记忆网络中检测是否存在这个刺激至杏仁核的通路，如果在记忆中未检测到，说明这类刺激是初次感知，此时会在记忆网络中增加这条通路，并按照权重规则，将权重设置为默认值1，如图7所示。

neurons_start neurons_end weight neurons_start neurons_end weight 0 pain_neurons amygdala_neurons 3.0 0 pain_neurons amygdala_neurons 3.0 1 red amygdala_neurons 1.0 恐惧记忆网络 (初始) 恐惧记忆网络(检测到物体后增加)

我们将杏仁核神经元的激活阈限设置为1.5，当杏仁核神经元接收到的信号超过阈限值时，会引起逃避反应。相反，如果杏仁核神经元接收到的信号并未超过阈限值，则不会引发逃避反应。

在生物的大脑中，神经元发送的信号是有强度差异的，更强的刺激会引发频率更高的动作电位，但不同方面的证据显示，强度的差异并不能区分不同的物体，相反，大脑通常采用不同的神经元来标注不同的物体，例如一些实验发现[50],对于同样的物体，注意会导致猴子视觉区中较高等级的皮层（V4等）相同神经元更强烈的放电，另外，很多实验发现，不同类别的物体通常存储在颞叶不同的脑区[51-57]，这些都说明神经元的放电频率与物体标签的关系较小。

出于上述原因，在本次实验中我们忽略了感知信号强度这一要素，所以对于接收信号的神经元来说，激活与否全部取决于其与信号发出神经元之间的权重，因此在未进行学习的情况下，只有痛觉神经元激活时会导致杏仁核神经元的激活，引发逃避反应。

# $\textcircled{3}$ 激活网络的设计

我们设置了一个激活网络用来模拟生物体在面对一个事件时所发生的情况。

激活网络记录了外界刺激进入智能体"大脑"时产生的即时信号，激活网络记录了以下三个方面的内容：信号发起神经元，信号接收神经元以及信号发起的时间。在未有刺激进入到智能体的神经网络时，激活网络是空的，一旦有信号进入神经网络，激活网络便会进行记录（图8）。

![](images/2c1f4d55fae0566e4483d0e98c62b2cb83eb34966c3e5f7f0517b5ad425a8fce.jpg)  
图8激活网络的表达

$\textcircled{4}$ 神经网络改变的规则

此次神经网络中权重的改变规则借鉴了SDTP原理。在激活网络中，如果某两个信号之间的间隔较小，且后面的信号会激活杏仁核，便会引发前面信号与杏仁核联系的增强。

我们假设增强的规则是：

$$
\mathrm { w e i g h t } = ( 1 + 0 . 5 ^ { \mathrm { t } } ) \times \mathrm { w e i g h t } ( \mathrm { p r e } )
$$

（公式1）

其中t为在激活网络中前后信号之间的间隔时间，weight(pre)是记忆网络中在未学习之前的权重。

时间间隔代表了强化的时间窗口，此处我们设置为 $2 0 0 \mathrm { { m s } }$ ，这要比生物脑内的真实的时间窗口长很多[9。需要说明的是，此处的公式及窗口并不是固定的，可以根据真实的场景进行修改。在本次实验的模拟环境中，智能体的移动需要进行刷新，刷新的时间间隔为 $1 0 0 \mathrm { { m s } }$ ，所以为了显示的方便，在此我们设置了更长的时间窗口。

对于习惯化，我们假设的规则是：

$$
{ \mathrm { w e i g h t } } = 0 . 9 \times { \mathrm { w e i g h t } } ( { \mathrm { p r e } } )
$$

对于经典条件反射的消退，我们假设的规则是：

$\mathrm { w e i g h t } = ( 1 - 0 . 5 ^ { \mathrm { t } } ) \times \mathrm { w e i g h t } ( \mathrm { p r e } )$ （公式3）

$\textcircled{5}$ 参数的设计及其意义

在实验中，我们固定了两类神经元的联结，包括疼痛神经元与杏仁核神经元之间的联结，以及当杏仁核神经元与逃避反应之间的联结，这类联结代表着智能体"大脑”内部先天的神经联结，意味着智能体对于这些反应都是不学而能的。

杏仁核神经元激活的阈限值则代表了生物对于疼痛的忍受程度，其值越低，则意味着生物体对于疼痛的忍受度越低，尽管会让智能体产生更快的学习行为，有更多的逃避反应，能够增加智能体在实际场景中生存几率，但相反的效果是，过多的逃避反应会相应地减少智能体的工作时间。

公式1中的间隔时间（t）意味着产生强化的时间窗口，这个窗口的长短面临着一种矛盾，更长的窗口时间意味着生物体可以在更长时间范围内进行神经元的强化，但耗费的内存空间也会增多，相反，越短的窗口时间在节省资源的同时，也意味智能体可能难以学习到现实世界中CS和US的配对规律。

无论是上述公式还是公式中的参数均不是完全固定的，智能体可以根据其工作的真实场景进行修改，以期让智能体能够在生存和工作的矛盾中找到最佳的平衡点。

# 2.3信号在神经网络中的加工过程

当智能体的感知发生变化时，感知神经元和杏仁核神经元之间的通路便会被保留在激活网络当中，这个过程称为"感觉登记”。

感觉登记发生后，智能体会根据激活网络中记录的神经通路来查看记忆网络，如果在记忆网络中存在相同的神经通路，便会提取此类神经通路的权重，并根据权重是否大于已设置的阈限值来进行反应，如果权重不大于阈限制，则将此通路记录在记忆网络，并将权重赋值为默认值1。

智能体的感知每发生一次变化时，便会重复上述过程一次，这称之为“一次循环”。

当整个过程结束之后，智能体的感知在较长的一段时间内不会发生变化，从开始变化至过程结束称为"一次事件”。在一次事件之后，智能体根据权重调整规则修改记忆网络中的权重，并清空激活网络，整个过程见图9，其中蓝色箭头代表一次循环中的加工，而橙色箭头代表一次事件后的加工。

![](images/a586f6291e39f636264d3c18158e60e462f39d1d636dde64ca38eb17db1def14.jpg)  
图9信号在神经网络中的加工过程

图10表示了整个过程中，激活网络和记忆网络中的变化。

![](images/9c70addb7b99dddce46ea6aeaf69b1d2a05950c6926aa3959f3a26a08b4100e3.jpg)  
图10记忆网络和激活网络在不同阶段信号变化（以恐惧学习为例）

# 3实验结果

我们在这个部分中展现恐惧学习、经典条件反射学习以及消退后的效果，实验效果的视频文件以及代码见补充材料。

# 3.1恐惧情绪学习

学习前和学习后的实验效果见图11。

对比不同阶段智能体的反应可以发现，学习前的智能体并不会躲避红色的威胁物，当它被威胁物攻击之后便产生了学习，经过学习之后的智能体产生了逃避反应，避免了再次受到伤害。

![](images/f36807a542a1eb0b790cfa22486f47106d1847eca3e2b1fb7f77a32cc0d97fc8.jpg)  
图11恐惧情绪学习前后智能体的表现

# 3.2经典条件反射式的学习

一旦智能体学会了对于红色威胁物的逃避反应，则这类威胁物便可视作经典条件反射的非条件刺激（US)，而灰色中性物则可以视作是条件刺激（CS)。

图12显示了经典条件反射学习前后智能体行为的变化。在学习前阶段，智能体并不会对灰色的中性物产生逃避反应，但中性物与威胁物配对出现，并且总是出现在威胁物之前，就满足了经典条件反射的条件。经过经典条件反射的学习，智能体对于中性物也会产生逃避反应。

![](images/3a7d0f71b46e0f50c0d149f01677d5fbbec057a860219b0c98d271c17df9ce91.jpg)  
图12经典条件反射学习前后智能体的表现

3.3习惯化和经典条件反射的消退

图13表示了习惯化后的结果，从图中可以看出，习惯化导致了智能体对于威胁物逃避反应的消失。

![](images/02491d7d2c5d98e2f4c2df10b0a05ce4c4cf1d502b4478880ff9d82f633e558e.jpg)  
图13习惯化前后智能体的表现

图14表示了经典条件反射消退后的结果，从图中可以看出，经典条件反射消退后，智能体对于作为条件刺激的中性物体的逃避反应消失了，但对于非条件刺激的逃避反应依然存在。

![](images/3f03bba9d790207e1b9972da4b6bcafbcaa392bd4a4cdc3cdb4116648c561c75.jpg)  
图14经典条件反射消退前后智能体的表现

# 4讨论

在本次实验中，我们首先提出了一个模型来解释杏仁核神经元的变化与生物体行为变化之间的关系，并据此模型设计了一种新的神经网络，这个网络模拟了杏仁核的神经结构，同时也使其具有了与杏仁核类似的功能，即恐惧情绪学习和经典条件反射式学习的能力。与人工神经网络和脉冲神经网络常用框架不同的是，我们着重强调了神经网络与人脑的相似性，我们认为在神经网络的设计当中，不应忽略这一重要因素。

与其他灵长类生物相比，人脑的神经元数量与其身体的比例并不特殊[]，但究竟是什么造就了人类独特的智力？一些实验发现，这种差异可能而是来自于神经网络的不同[17,18]，智力更高的物种可能有着更加复杂的神经网络，例如与食肉类动物和啮齿类动物相比，灵长类动物的新皮层中上颗粒层（ⅡI和III）的神经元占比要高出很多[18]，上层颗粒层主要作用是将信号投射至其他皮层[58.59],这意味着在灵长类动物的大脑中，有更多的神经元用于联结其余的脑区，形成复杂的神经网络，所以一些研究者认为这正是灵长类动物，包括人类有用高级认知能力的来源[60.61]。另一个被广为接受的事实是，神经网络也决定了单个神经元所表达的意义[62]。脑内不同部位的神经元所发出的信号均表现为轴突的动作电位，与此形成鲜明对比的是，当相同的信号置于不同的神经网络时，却表达了不同的意义，例如视觉皮层中V1区神经元的放电可能代表了某个朝向的线段[63]、MT皮层中神经元的放电则代表了视觉系统中发现有某种朝向运动[64]、颞叶中某个神经元的放电则带代表了检测到了某个面孔[65]。这些事实表明了神经网络在实现智能中的重要性。

在生物大脑的神经网络中，时间是另一个起着重要作用的因素[6-9]。神经生物学的实验证明，时间因素在影响神经元联结中起着决定性作用，如果某个神经处于放电状态，会强化与其连接且激活时间更早的突触，而会削弱与其连接且激活时间更晚的突触[9。所以我们记录了神经元放电的时间点，并通过比较不同神经网络被激活的时间，模拟出了神经元突触的变化。这一点与脉冲神经网络[10]具有的能力相仿，不同的是，我们并没有在细胞膜水平上对神经元进行模拟，我们忽略了信号在两个神经元之间的传递形式，而仅以一个数值来代替，

这一点又与MP模型类似[2]。

在神经网络的设计当中，我们增加了感觉登记的过程。心理学的研究发现，对于不同的感知系统，存在一种保留时间非常短的记忆[46-49]，称为感觉记忆或感觉登记，只有那些经过注意的感觉记忆信息才能够进入短时记忆，并可能进一步加工进入长时记忆，而那些没有经过注意加工的感觉信息则会被弃用[45]。感觉登记能够让大脑将外界刺激保留一段时间，并根据随后的反馈信息进行突触的调节，从而产生记忆或者学习行为，这种方法特别适用于生物体处理未知的环境。与此形成对比的是，计算机科学中的条件语句（conditional statement）也常用于让计算机基于不同条件执行不同的动作，但条件语句需要设计者需要预先知道智能体所将要面对的场景。在一个开放式的环境下，智能体所需要面对的场景近乎无限（例如在一个陌生星球上进行探测的智能体)，在这种情况下，我们的方法就会显得非常实用。

智能体的学习方式也是跨通道的，在我们的神经网络中，学习并不局限于某种特殊的神经感知通路，无论采用哪种感知方式，只要这些感知神经元都投射至杏仁核，并且满足神经网络的改变规则，均能进行恐惧情绪学习和经典条件反射学习。

在本次设计的神经网络当中，并不存在非常多的计算过程，智能体的学习主要体现在记忆和权重的修改上，所以对于算力的要求很低，这也与大脑的情况类似。人脑能够以非常低的能耗处理问题，所以一些研究者推测，人类的大脑并非一个计算器，而是一个记忆和预测系统[，我们的实验支持了这种假设。

# 参考文献

1 Azevedo,F.A. C., Carvalho,L.R.B., Grinberg,L.T.,Farfel, J.M.& Herculano-Houzel, S. Equal Numbers of Neuronal and Nonneuronal Cels Make the Human Brain an Isometrically Scaled-Up Primate Brain. Journal of Comparative Neurology 513, 532-541 (2009).   
2 Mcculloch,W. S.& Pits,W. H. A logical Calculus of Ideas Immanent in Nervous Activity. The Bulletin of Mathematical Biophysics 5,115-133 (1942).   
3 Nair, V.& Hinton,G.E. in international conference on machine learning. 807-814.   
4 Rosenblatt & F. The Perceptron: A Probabilistic Model for Information Storage and Organization in The Brain. Psychological Review 65,386-408 (1958).   
5 Rumelhart，D.E.，Hinton，G. E.& Williams，R. J. Leaning representationsby back-propagating errors.Nature 323,533-536 (1986).   
6 Markram,H.,Lubke,J., Frotscher, M.& Sakmann, B. Regulation of synaptic eicacy by coincidence of postsynaptic APs and EPSPs. (1997).   
7 Gerstner，Wulfram，Kempter & Richard.A neuronal learning rule for sub-millisecond temporal coding. Nature (1996).   
8 Zhang,L., Tao,H.,Holt, C., Harris,W.& Poo,M. A critical window for cooperation and competition among developing retinotectal synapses. Nature 395, P.37-44 (1998).   
9 Bi,G.Q.& Poo，M. M. Synaptic Modifications in Cultured Hippocampal Neurons: Dependence on Spike Timing, Synaptic Strength, and Postsynaptic Cell Type. The Journal of Neuroence 18,10464-10472 (1998). Maass, W. Networks ot Spiking Neurons: The Third Generation ot Neural Network Models. Neural Networks 10,1659-1671 (1997).   
Ponulak, F., Kasi, A. J. & #x. Supervised learning in spiking neural networks with resume. Neural Computation (2010).   
Guetig,R.& Sompolinsky，H. The Tempotron: a neuron that learns spike-timing based decisions. Reviews in the neuroences 16, S27-S27 (2005).   
Masquelier， T.，Guyonneau，R.& Thorpe,S.J.Competitive STDP-Based Spike Pattern Learning. Neural Computation 21,1259-1276 (2009).   
Diehl，P. U.& Matthew， C. Unsupervised Learning of Digit Recognition Using Spike-Timing-Dependent Plasticity. Frontiers in Computational Neuroscience 9, 99 (2015). Masquelier, T. & Thorpe, S. J. Unsupervised learning of visual features through spike timing dependent plasticity. PLOs Computational Biology 3 (2007).   
Roy，S.& Basu,A. An Online Unsupervised Structural Plasticity Algorithm for Spiking Neural Networks.IEEE Transactions on Neural Networks 28,900-910 (2017).   
Oxnard,C. E.Brain Evolution: Mammals,Primates,Chimpanzees,and Humans.25, 1127-1158 (2004).   
Hutsler, J. J.,Lee,D. G. & Porter, K. K. Comparative analysis of cortical layering and supragranular layer enlargement in rodent carnivore and primate species. Brain Research 1052, 71-81 (2005).   
Pascoe, J.P. & Kapp,B. S. Electrophysiological characteristics of amygdaloid central nucleus neurons during Pavlovian fear conditioning in the rabbit. Behavioural Brain Research 16, 117-133 (1985).   
Serge,C.& Michael,D. Induction of the c-fos proto-oncogene in rat amygdala during unconditioned and conditioned fear. Brain Research (1991).   
Amaral, D. G. The Amygdala, Social Behavior, and Danger Detection. Annals of the New York Academy of Sciences (2003).   
Anderson,A.K.& Phelps,E.A. Intact recognition of vocal expressions of fear following bilateral lesions of the human amygdala. Neuroreport 9,3607-3613 (1998).   
Funayama,E. S.，Grillon,C.,Davis，M.& Phelps,E.A.A Double Dissociation in the Affective Modulation of Startle in Humans: Effects of Unilateral Temporal Lobectomy. Journal of Cognitive Neuroence (2001).   
Phelps,E. A., O'Connor, K. J., Gatenby, J. C., Gore, J. C.& Davis, M. Activation of the left amygdala to a cognitive representation of fear. Nature Neuroence 4, 437-441 (2001).   
Kapp,B. S.， Whalen， P. J.， Supple,W.F. & Pascoe, J.P. Amygdaloid contributions to conditioned arousal and sensory information processing.(1992).   
LeDoux & E, J. Emotion Circuits in the Brain. Annual Review of Neuroscience,155-184 (2000).   
Fanselow,M. S.Neural organization of the defensive behavior system responsible for fear. Psychonomic Bulletin & Review 1, 429-438 (1994).   
Pitkanen, Asla, Savander & Vesa. Organization of intra-amygdaloid circuitries in the rat: An emerging framework for understanding. Trends in Neurosciences (1997).   
Amaral, D., Price,J., Pitkanen,A. & Carmichael, S. Anatomical organisation of the primate amygdaloid complex. Amygdala (1992).   
Turner, B. H., Mishkin, M. & Knapp,M. Organization of the amygdalopetal projections from modality-specific cortical association areas in the monkey. Journal of Comparative Neurology 191, 515-543 (1980).   
31 Mcdonald, A. J. Cortical pathways to the mammalian amygdala. Progress in Neurobiology 55, 257-332 (1998).   
32 Turner,B.H.& Zimmer,J.The architecture and some of the interconnections of the rat\"s amygdala and lateral periallocortex. Journal of Comparative Neurology 227, 540-557 (1984).   
33 Ledoux, J.,Iwata, J., Ciccheti, P. & Reis, D. Different projections of the central amygdaloid nucleus mediate autonomic and behavioral correlates of conditioned fear. Journal of Neuroscience 8, 2517-2529 (1988).   
34 Quirk,G.J.,Armony, J.L.& Ledoux,J.E.Fear Conditioning Enhances Different Temporal Components of Tone-Evoked Spike Trains in Auditory Cortex and Lateral Amygdala. Neuron 19, 613-624 (1997).   
35 Quirk,G.J.,Repa, J. C.& Ledoux,J.E.Fear conditioning enhances short-latency auditory responses of lateral amygdala neurons: parallel recordings in the freely behaving rat. Neuron 15,1029-1039 (1995).   
36 Rogan, M. T., Staubli, U. V. & LeDoux, J. E. Fear conditioning induces associative long-term potentiation in the amygdala. Nature 390, 6O4 (1997).   
37 McKernan, M. & Shinnick-Gallagher, P. Fear conditioning induces a lasting potentiation of synaptic currents in vitro. Nature 390, 6O7 (1997).   
38 Yang,Y., Liu, D. Q., Huang,W., Deng, J. & Poo, M. M. Selective synaptic remodeling of amygdalocortical connections associated with fear memory. Nature Neuroscience 19,1348 (2016).   
39 Sutton, R. S. & Barto, A. G. Toward a Modern Theory of Adaptive Networks: Expectation and Prediction. Psychological Review 88,135-170 (1981).   
40 Klopf,A. H. A neuronal model of classical conditioning. Psychobiology 16, 85-125 (1988).   
41 Schmajuk, N. A. & DiCarlo, J. J. Stimulus configuration， classical conditioning，and hippocampal function. Psychological review 99,268 (1992).   
42 Romanski,L.M. & E.，L. J. Information Cascade from Primary Auditory Cortex to the Amygdala: Corticocortical and Corticoamygdaloid Projections of Temporal Cortex in the Rat. Cerebral Cortex,6 (1993).   
43 Hearst,E.Fundamentals of learning and conditioning.(1988).   
44 Kandel,E.R.In Search of Memory.120-121 (2006).   
45 Atkinson,R. C.& Shiffrin,R.M.[Psychology of Learning and Motivation] Volume 2 Human Memory: A Proposed System and its Control Processes. Psychology of Learning & Motivation, 89-195 (1968).   
46 Sperling，G. The information available in brief visual presentations. Psychological monographs: General and applied 74,1 (1960).   
47 Sperling,G.A model for visual memory tasks. Human Factors 5,19-31 (1963).   
48 Crowder， R.G. & Morton， J. Precategorical Acoustic Storage (PAS). Perception & Psychophysics 5,365-373 (1969).   
49 Darwin, C. J. Turvey, M. T. & Crowder, R. G. An auditory analogue of the sperling partial report procedure: Evidence for brief auditory storage. Cognitive Psychology 3, 255-267 (1972).   
50 Moran, J. & Desimone, R. Selective attention gates visual processing in the extrastriate cortex.

Science 229, 782-784 (1985). 51 Damasio,H.& Grabowski,T.J.A neural basis for lexical retrieval.Nature (1996). 52 Blundo, C.，Ricci，M.& Miller,L. Category-specific knowledge deficit for animals in a patient with herpes simplex encephalitis. Cognitive Neuropsychology 23,1248-1268 (2006). 53 Caramazza,A. Domain-specific knowledge systems in the brain the animate-inanimate distinction. Journal of Cognitive Neuroence 10 (1998). 54 Mahon,B. Z. & Caramazza,A. Concepts and Categories: A Cognitive Neuropsychological Perspective.Annual Review of Psychology 60,27-51 (2009). 55 Chao,L.L.，Jill，W.& Alex，M. Experience-dependent Modulation of Category-related Cortical Activity. Cerebral Cortex,545-551 (2002). 56 Chao,L.L., Haxby, J. V. & Martin, A. Attribute-based neural substrates in temporal cortex for perceiving and knowing about objects. Nature Neuroscience 2, 913-919 (1999). 57 Martin & Alex. The Representation of Object Concepts in the Brain. Annual Review of Psychology 58,25 (2007). 58 Marinpadilla,M. Cajal-Retzius cells and the development of the neocortex. Trends in Neurosciences 21,64-71 (1998). 59 Jr, C.V., Takahashi, T.& Nowakowski,R. S.Numbers, time and neocortical neuronogenesis: a general developmental and evolutionary model. Trends in Neurosciences 18,379 (1995). 60 Mountcastle, V. B. Modality and topographic properties of single neurons of cat's somatic sensory cortex.. Journal of Neurophysiology 20,408-434 (1957). 61 Elston, G.N. Cortex, Cognition and the Cell: New Insights into the Pyramidal Neuron and Prefrontal Function. Cerebral Cortex (2003). 62 Kandel, E.R. et al. Principles of neural science. 33-35 (McGraw-hill New York,2000). 63 D.H.Hubel & T.N.Wiesel. Ferrier Lecture: Functional Architecture of Macaque Monkey Visual Cortex. Proceedings of the Royal Society B Biological Sciences (1977). 64 Maunsell, J.H. & Van Essen, D.C.Functional properties of neurons in middle temporal visual area of the macaque monkey. II. Binocular interactions and sensitivity to binocular disparity. Journal of Neurophysiology 49,1148-1167 (1983). 65 Freiwald,W.A.& Tsao,D.Y. Functional compartmentalization and viewpoint generalization within the macaque face-processing system. Science 330, 845-851 (2010). 66 Hawkins, J.& Blakeslee, S. On intelligence. (Times Books,2004).

# 作者贡献声明：

位东涛：提出研究思路，设计研究方案，论文最终版本修订；  
王国清：提出研究思路，设计研究方案，编写程序，论文起草。