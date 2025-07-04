# 基于生成对抗网络的配网单线图网络结构特征表示学习

张翔

（国网信通亿力科技有限公司，福建，福州）

摘要：对于配电网的规划设计、运行检修、调度管理等业务，配网单线图是一种必不可少的常用工具。配网单线图在使用过程中对于布局规范性有严格要求，不同的配网网架结构配网单线图的成图布局各不相同，传统的自动成图算法无法适配网架结构的变化，自动根据网架类型生成对应布局的单线图。深度学习算法具备强大的耦合性，它能够自动总结内部成图规律，生成符合所需成图布局的配网单线图。为了将深度学习算法应用于配网单线图自动成图领域，需要考虑建立一个能够表示配网单线图网络结构特征的算法，该算法核心是能够适应深度学习算法需要，实现配网单线图网络特征的低维度表达。现有的网络特征表示学习方法研究多是针对于社交网络的特有属性进行特征表示。电力设备网络与社交网络相比，设备间的连接关系受电气物理特性限制，并没有针对电力网络的特有属性进行学习。因此，本文在已有的网络特征表示学习研究的基础上，提出了一个针对配网单线图的网络特征结构表示学习算法，利用构成配电网基础的配电设备电气联接关系来建立数学模型，定义网络节点间一阶、二阶和零阶连接特性，然后通过生成对抗网络来实现低维度网络特征表示。论文结尾在实验中通过样本数据验证网络特征的一阶和二阶相似性，证明算法在实现的效率和准确性上，更贴近电力业务的特点。

关键词： 配网单线图；网络特征；生成对抗网络

# 1.引言

在电力行业，配电网的高效运行和管理需要借助多种辅助信息，其中配网单线图就是电力运行调度人员日常工作重要基础，其需要展现单一线路范围内的所有主分支设备，包括变电站、电缆、架空线、开闭所、环网柜、配电变压器等的示意专题图形，线路及其相关设备采用正交布局算法进行无交叉重叠布局。从日常运行检修、故障分析定位到配电电网调度等业务都围绕着描述电网结构的配网单线图来实现。

![](images/09b0dcc426a53f3c8ea3bce76067330d7911f5779e22ba7ca4a9f3b8c468d8dd.jpg)  
图1配网单线图

实际生产中由于配网的更新十分频繁，对于单线图生成和更新都要求快速准确，同时单线图的成图风格要求保持一致美观，以便于用户进行方便的浏览查看。而且在电力日常生产中，配网作为电力输送的末端环节，其电网结构跟当地的城市建设情况，经济水平、人文环境密切相关，下图是两种不同风格网架结构形成的有差异性的单线图布局风格;

![](images/8646d13e1e895fbe3daf9bd62c971e612d448c95519d9497a219828dc6b9462a.jpg)  
图2两种布局风格的单线图

因此如果单线图成图布局单纯通过人工维护，其工作量十分巨大，并且容易出现问题。传统的自动成图算法如退火算法、树图算法、遗传算法、引力-斥力算法等各种算法在单线图布线上的结合应用也进行了研究和实践对于单线图自动生成方法都有一定的参考价值，但是其成图风格无法跟随实际情况进行智能调整，风格变动后只能重新修改成图的程序近几年随着人工智能领域深度学习算法的爆发，在人工智能推理，风格学习方面展现出良好的性能并体现出优异的成果；如下面基于深度学习中生成对抗网络的风格学习，生成对抗网络能够自动根据A画的特征绘制出具有A风格特征的B画。

![](images/b956c3fc33ee1ae7c67dc647b096324dbdaa8adbd40f367ae5c3a7faa966c320.jpg)  
图3绘画风格的转变

在配网单线图自动成图领域也可以借鉴深度学习网络强大的自动推理能力，通过建立深度学习模型，来根据需要自动推理出合适的单线图风格。深度学习模型能够应用于配网单线图自动成图的前提条件就是要有一个合适的数学模型来描述所要学习的配网单线图网络结构。在深度学习领域网络表示学习（Network Embedding）正是为了应对这种挑战出现的，网络表示学习就是表示学习在网络研究领域的特称，可以将网络中每个节点自动学习的所需的表示向量空间中。它是任何在深度学习领域开展网络特征研究的基础。表示学习将网络中各种繁琐的特征属性，通过无监督/监督学习，从原始数据中自动的识别出有价值的信息，并将其编码到一个低维、稠密、连续的向量空间中。

具体网络特征表示学习算法的演进历史和特点可以参考文献【1】。这些算法在主要出发点都是基于社交网络的分析和表示，相对于社交网络节点间交互的不确定性和灵活性，配网单线图作为一种网络结构图，里面蕴含着大量的电气物理特性，其节点间的连接关系，与传

统的如社交网络图、生物网络等大大不同。为了将深度学习算法能够应用到电力专题图领域，最大的挑战是需要一种简单高效的网络模型表示算法。  
在配网单线图中，可以将电力设备视为网络节点，设备间的连接线路视为网络的边，这些设备间是否连接或者连接的方式是否可行，受限于电力设备的物理特性以及电力业务的自身需要。这些限制条件隐藏了非常丰富的信息，如一个断路器两边连接大概率是隔离开关，一个跌落只能存在进线和出线两个连接关系。在配网单线图网络结构特征表示学习中，如果能够充分利用这些限制条件及配网单线图的电气特性，将大大提升算法的表示效率，降低计算的复杂度，并且能够更加精确的体现电力线路的特点。

# 2．相关工作

本文从配网单线图的自身网络特点出发，提出适应配网单线图自身特点的网络表示方法，工作将分为两个阶段：第一个阶段是建立配网单线图的节点间节点序列表示，这个是网络表示的基础性工作，要将一个网络从高维度映射到低维度，先要确定该网络特性，如何来表示网络节点关系；为了保持配网单线图特有的网络特性对于传统的一阶相似性和二阶相似性进行了改进，使其能更充分利用设备的连接电气特性，并提出了零阶相似性的定义；第二阶段是结合深度学习的生成对抗算法，将第一阶段建立的节点关系作为输入，建立一个生成对抗网络；为每个设备节点学习一个低维度的表示。在这个生成对抗网络中，将充分利用线路的主线支线关系和设备连接的电气物理特性，来建立生成对抗网络的输入张量。

本文主要贡献：

1）以配电网设备间电气连接关系为出发点，通过数理统计方法，提出建立配网单线图的节点序列模型，及节点序列权重值的通用算法；2）基于配网单线图的设备间的电气联接特性，对于主要网络特征的描述，摒弃传统一阶相似性和二阶相似性来描述网络特征，而是通过在分支节点相似性和节点序列递归相似性描述上，来阐述主要网络特征，重新定义了节点间的零阶、一阶和二阶相似性；3）重新设计了生成对抗网络，使其与auto-encode 结合起来，能够利用配网单线图的特性，来进行学习，从而能够更有效的将设备节点映射到低维度向量空间中。

本文将组织如下：首先探讨配网单线图节点序列建立和权重值算法，在此基础上介绍如何结合电气连接特性，来定义适合配电网网络的零阶、一阶和二阶相似性表示方案，完成以上两个基础性工作后，介绍如何重新设计满足配网单线图网络表示的生成对抗学习网络。最后是介绍使用t-SNE实现高维度和低维度特征比对，验证了本文所提出方法的有效性。

# 3．研究内容

# 3.1配网单线图网络特性分析

配网单线图是以单条配网线路（馈线）为单位的，采用一定布局算法自动生成从变电站出线到配电变压器或线路联络开关之间的线路相关所有设备，所呈现的电气设备主要包括变电站、环网柜、开闭所、柱上负荷开关、柱上断路器、柱上隔离开关、跌落式熔断器、中压架空线、中压电缆、配电变压器、配电室、箱式变、分支箱、杆塔（包括杆塔附属设备跳档、接地环）等。主要是开关、站房、线缆、变压器、杆塔这五类设备，其中开关、线缆和变压器一般含有两个端子，站房和杆塔可以视为多端子的设备。线路在杆塔或站房处产生分支。根据单线图的业务特性，单线图分为主干线和分支线。

![](images/bd1fee7b7ccddacc68a8206b1126022848181cfe88982deb114fbd2a4cc6a03f.jpg)  
图4配网单线图图例

配网单线图作为描述馈线的图示，其核心特性是线路的电气物理特性，即电流从高电压设备流向低电压设备。配网单线图主要是电气设备节点，以及设备间的物理连接线路构成的，其设备间连接的权重如何表示，是一个关键的问题，因为单线图连接的层次不同，设备间连接的权重也不一样，不能像简单的邻接矩阵那样，认为其权重都是相等的，如相连的用“1”表示，不相连的用“0”表示；这样的表示方法无法体现出设备间的电气连接关系的重要性。配网单线图的电源点都是从变电站或开关站的出线开关开始，电流依据欧姆定律逐级流动，因此在建模时需要依据电气物理特性来体现的是设备与电源点及设备间的连接权重。

# 3.2配网单线图连接关系模型建立

配网单线图中设备连接依靠的是线路，如果单纯依据线路的长短来设置其权重值，并无法说明其设备间连接关系的重要性，只能说明设备在实际地理空间中位置远近。由于单线图是从电力设备地理接线图中依据一定的规则抽取设备连接关系生成的，对于设备在实际地理空间中的位置信息在单线图生成后已经消失了，在单线图建模中设备空间位置信息并不需要关注。

配网单线图中还有一个重要的特性是设备之间的连接关系，即设备的拓扑关系。对于配网单线图设备间的拓扑关系，在电力生产中有统一的模型规范来表示，即基于 IEC61968 和IEC61970 的 SG-CIM模型规范。在很多论文中讨论关于SG-CIM 模型在配网单线图中的应用，实际中通过SG-CIM描述的是电网拓扑连接关系，其适合作为配网单线图的数据源规范格式，满足在不同系统间传输配网单线图的数据，实质是描述配网单线图的设备ID，部分简单的台账信息以及设备端子间的连接关系。但是SG-CIM模型主要定义了各个设备用于连接的端子特性，以及体现的设备间的是否存在拓扑连接关系，其并不定义设备间连接的权重值。本文在进行验证是所使用的数据都是基于SG-CIM模型来进行描述的。

电力设备的联接权重值需要从电力设备的种类和设备连接电气特性出发，设备原则上可以连接的设备跟其端子有关（为了讨论方便限定一个端子上只能连接一个设备)，设备端子上能连接的设备种类跟设备的电气特性有关系。

对于两个设备的连接特性可以通过设备连接概率来描述。以如下方式进行计算：

首先限定单线图设备的范围F（F里面包含了所有在单线图上进行展示的设备类型）。利用设备A与某一设备连接关系概率来定义设备间连接的权重值。

设设备A上存在N个连接端子（先限定每个端子上只能连接一个设备)，每个端子可以与M种设备连接。则一个连接端子上连接另外一个设备的概率为 $1 / \mathsf { M }$ ，符合一个二项分布的$\mathsf { P } ( \mathrm { X } = \mathrm { n } ) { \sim } \mathsf { B } ( \mathrm { N } , 1 / \mathrm { M } )$ ；因此在设备A联接时与n个设备B的概率为 $C _ { N } ^ { n } ( 1 / \mathsf { M } ) ^ { n } ( 1 - 1 / \mathsf { M } ) ^ { N - n }$ 在设备A中一个端子上出现设备B的概率为1/MN。设备间的连接概率从设备的电气物理特性上正好说明两个设备间连接的可能性。

# 3.3配网单线图节点序列模型

在配网单线图中同一种设备会出现在不同的位置，相同两种设备的连接情况也会出现在不同的位置，如果单纯考虑两种设备的连接特性无法全面描述配网单线图的网络特征。因此还需要考虑设备在全局中的位置，在配网单线图中各设备获得功率的核心在供电电源，可以利用这一点描述设备在全局中的位置，以电源点为出发点，获得配网单线图中各个设备与电源点的连接权重。

在单线图中设备归集的粒度是主干线和分支线；因此描述完整的配网单线图需要使用序列的方法描述主干线和分支线的连接关系，才能完整的描述整体的配网单线图网络特征。根据主分支线都是由电源点供电这一物理特性,每个序列可以用来描述单线图中的一个线路路径。在每个线路路径中，序列中的每个元素正好可以描述电流流经路径上每个流经设备与母线间的权重关系。

如果通过一个节点序列来进行描述的话，则可以通过以下的数学模型进行描述。

![](images/c643c0cc92065bbbfb130b31c4f7fd5aaec733951bbe77ea35d1f3b566160092.jpg)  
图5单线图线路

图5 所示，其中主干线序列为A-B-C-D；由于分支线的供电也是跟主干线从同一个电源点开始，因此分支线的序列为A-B-C-E-F；各节点的连接权重如图例中所示。

节点序列的计算以线路的母线为出发点，由于在单线图母线作为整个线路的电源点，是整体线路的起点，由于存在这个特殊性，这里指定其与从母线出发，电流流经的第一个设备连接概率固定为“1”。对于线路中第N个设备，可以设母线为S，则其概率为 $\mathrm { P } ( N | S )$ ，由于设备间的连接关系与上一个设备相关，具备连接上的独立性，因此根据链式公式，$\mathrm { P } ( \mathrm { N } | \mathrm { S } ) = \mathrm { P } ( N _ { 1 } | \mathrm { S } ) \mathrm { P } ( N _ { 2 } | N _ { 1 } ) \ldots \mathrm { P } ( N _ { n - 1 } | N ) ,$ 0

主干线和分支线从网络拓扑结构上基本相同。但是在业务应用上却有极大的不同，如果均视为线路路径一并看待的话，无法区分两者的不同，因此在分支线的处理上需要对分支线路进行单独处理，不然从节点序列的角度，分支线与主干线的分叉是一样的，从单纯的节点序列上是无法进行判断的。按照业务分析在配网单线图中主干线为主要的供电路径，分支通常作为线路的搭接等。因此在表示上可以在节点序列中在主分支线的分叉点处通过权重值乘以一个 $\mathsf { a } = 0 . 9$ 的常数来区分主干线和分支线的区别。

根据节点序列模型定义，计算图例中的主干线和分支线的节点序列为：

$A \cdot > B$ ：节点A为电源点，其节点权重值为1；节点B，根据定义为： $1 \times 0 . 5 = 0 . 5$ ，节点[的权重值为0.5，因此节点序列为：{1，0.5}

$B - > C$ ：根据定义节点C权重值为： $1 \times 0 . 5 \times 0 . 2 { = } 0 . 0 1$ ，节点序列为： $\{ 1 , ~ 0 . 5 , ~ 0 . 0 1 \}$ 其他节点权重值按照此方式进行计算即可。可得主干线的节点序列为： $\{ 1 , 0 . 5 , 0 . 0 1 , 0 . 0 0 3 \}$ 对于分支线从跟主干线一样从电源点开始，共有的部分权重值是一样的，对于分支部分需要乘以一个权重值0.9，即{1，0.5，0.01，0.0027，0.00054}；注意是按主干线权重值算法计算完分支线各节点后，再将分支线部分乘以0.9。

# 3.4配网单线图网络节点相似性

根据上文的分析由于电力设备的物理特性和电气特性，在配网单线图中设备节点构成的网络跟传统社交网络中各个节点的构成关系是不同的，在社交网络中的节点，一个节点可能性上跟网络中其他节点都会可能发生连接关系。但是在配网单线图网络中节点的连接上随机性由于受限于本身特性，基本不存在随机性，节点间的连接要严格遵照线路原始设计的，无法发生随意的连接。

在网络特征学习中网络节点的生成表示需要考虑的是节点间的相似性，在网络表示学习中关于相似性的定义主要是为了说明节点间在网络中局部和全局的关系，在从高维到低维的映射过程中能够保持住这个网络的重要特性。局部信息是指，网络中的边信息，它是一个观测到的一阶相似度，之前很多方法就用了这个信息，如 IsoMap，Laplacian eigenmap。但是实际上在现实网络中，很多合法的边没有被观测到。所以一阶相似度并不能有效的表示全局信息。所以有人就提出了，二阶相似度，不是通过节点周围点的连接强度，而是通过与其他节点间共享邻居节点的结构来表示信息。直觉上，节点之间分享的邻居节点越多，可以认为他们越相似。

相似性的定义对于配网单线图而言其一阶相似性和二阶相似性的定义在需要从网络本身特性出发。由于配网单线图中的节点更加关注的是与其相邻节点的连接关系，而且受限电流从高电压到低电压的流向这一物理特性，相对而言一阶相似性和二阶相似性的定义可以比传统的网络相似性定义简单些，而且不必去考虑更高阶的相似性。

# 定义1：一阶相似性

根据配电网中设备间连接的概率即上文中讨论的设备间连接的权重受到本身物理特性的限制是固定不变的，因此设备节点间无论是高维表示还是低维表示，在同一个单线图中其节点间的连接概率即连接权重应该保持不变；

# 定义2：二阶相似性

根据一阶相似性定义的前提条件是设备的连接权重保持不变，因此高维的节点应该与低维节点具备相似的映射关系；才能保证节点间的连接权重保持不变；对于二阶相似性的定义就是要求同一个节点在高维空间的表示与低维空间表示具有“一致性”

前面讨论了由于配网电线图中节点间还有一个重要的关系，就是节点与电源点的关系，通过这个关系可以体现出节点与电源点间位置上的连接关系—一“远近”，以及设备处在主干线或分支线上等特性，因此补充一个定义，及描述自身节点的特性的定义，此处将其定义为：

# 定义3：零阶相似性

即描述电力设备与电源点间的权重关系，体现电力设备在配网单线图中的位置。

根据对于配网单线图网络节点相似性的定义，在网络特征学习中需要通过特征学习网络来学习网络的相似性以保证，对于网络节点低维空间的表示能够与高维空间在相似性上保持一致。

# 3.5配网单线图特性学习模型

此处及下文将用的公式符号统一说明如下：

![](images/f479c7a0f170d56d5aaf82ae5a5dba9401c980cabd312f478a07c86036f2b70e.jpg)  
图6单线图公式符号示例

$N _ { o n e - h o t }$ ：表示节点N使用one-hot来表示;  
$N _ { v e c }$ ：表示节点N的低维空间表示;

$\mathsf { P } ( N | S )$ ：表示节点N与电源点S的连接权重值;

$\mathsf { P } ( \mathsf { M } | N )$ ：表示节点M与节点N的连接权重值，其中节点N为起点，节点M为终点;

$N _ { o }$ ：配网单线图在高维度中要表示一个节点，首先用这个节点所属设备类型的one-hot向量来表示这个设备，第二个需要表示的是设备的在单线图中的位置，此处可以使用前面定义的零阶相似性来表示，因此可以对one-hot所表示的向量进行拓展，在one-hot中增加一维，这样一个设备节点的向量就可以这样表示： $\left( \operatorname { N } _ { o n e - h o t } , P ( N | S ) \right)$

$P _ { x \sim N _ { o } }$ ：表示配网单线图在高维节点的分布；  
（20 $P _ { x \sim N _ { \mathrm { v e c } } }$ ：表示配网单线图在低维节点的分布。

先给出整个特征学习网络的模型：

![](images/45da0a5a2184e9fe0fe33f883f77a8f84095a957d9b371583ef1a19ec8f870a7.jpg)  
图7网络特征学习模型

整个学习网络的模型由三大部分构成。第一部分是 Encoder编码器，将所要生成的节点从高维空间映射到低维空间对应于生成对抗网络中的生成器（Generator)；第二部分判定器（Discriminator）用于区分低维空间节点和高维空间节点，根据一阶相似性定义让生成器生成的低维度节点与实际的高维度节点要尽量保持整体的一致性；第三部分是一个深度学习网络用于判定新的低维节点与上级的低维节点在二阶相似性上与两者的高维度节点保持一致，即低维度的节点间的连接权重与高维度节点间的连接权重保持一致。

如果按照传统深度学习中自动编码器是一种数据的压缩算法，其中数据的压缩和解压缩函数是数据相关的、从样本中自动学习的。在大部分提到自动编码器的场合，压缩和解压缩的函数是通过神经网络实现的。如果使用这种传统的编码模式存在最大的问题是由于缺乏对一阶相似性相似性和二阶相似性的学习，从数据上来讲这是简单的将高维的表示映射向低维表示，整个学习模型就是一个映射函数的模拟，没有从体现节点在高维空间的中的节点间的关系。为此需要网络整体具备特征保留特性，在映射过程中对于节点间的关系也能够同步进行归纳。由于配网单线图的输入是一个不定长的序列，因此需要使用 LSTM（Long Short-TermMemory，长短期记忆网络）来进行数据输入。

在生成对抗网络中，判决器通过学习真实的数据分布来逐步的调整生成器生成的数据，

![](images/b3499bdd82f156689f4862656181227c5355cf5a8bead399c5df3fe02ae3dc7d.jpg)

如图8所示，假设在训练开始时，真实样本分布、生成样本分布以及判别模型分别是图中的黑线、绿线和蓝线。可以看出，在训练开始时，判别模型是无法很好地区分真实样本和生成样本的。接下来当我们固定生成模型，而优化判别模型时，优化结果如第二幅图所示，可以看出，这个时候判别模型已经可以较好的区分生成数据和真实数据了。第三步是固定判别模型，改进生成模型，试图让判别模型无法区分生成图片与真实图片，在这个过程中，可以看出由模型生成的图片分布与真实图片分布更加接近，这样的迭代不断进行，直到最终收敛，生成分布和真实分布重合。

借鉴这个思路在配网单线图网络一阶相似性的保留上可以通过Discriminator使 Encoder的编码在空间分布上逐渐与高维空间分布一致。设在高维空间中设备的分布为 $P _ { x \sim \mathrm { N } _ { o } }$ ；由低维空间生成的设备分布是由生成器生成的可以设为 $P _ { x \sim N _ { v e c } }$ ；从分布上我们希望 $P _ { x \sim \mathrm N _ { o } }$ 和$P _ { x \sim N _ { v e c } }$ 能够一致。由于在高维空间的节点映射的低维空间上，两者在特征表示即所蕴含的信息量上应该是一致的，因此在概率空间的分布上也是应该一致的，因此希望两者在期望上尽量相近，可得：

(1) $E _ { x \sim P _ { x \sim N _ { o } } } \geq E _ { x \sim N _ { v e c } } ;$ （

$$
\begin{array} { r l } & { \theta ^ { * } = a r g \operatorname* { m i n } _ { \theta } \left( E _ { x \sim P _ { x \sim N _ { o } } } - E _ { x \sim N _ { v e c } } \right) ^ { 2 } = \arg \operatorname* { m i n } _ { \theta } E _ { x \sim P _ { x \sim N _ { o } } } - E _ { x \sim N _ { v e c } } } \\ & { \quad = a r g \operatorname* { m a x } _ { \theta } E _ { x \sim N _ { v e c } } - E _ { x \sim P _ { x \sim N _ { o } } } } \\ & { \quad = a r g \operatorname* { m a x } _ { \theta } \int _ { x } \ P _ { x \sim N _ { o } } \log P _ { x \sim N _ { v e c } } ( x ; \theta ) d x - \int _ { x } \ P _ { x \sim N _ { o } } \log P _ { x \sim N _ { o } } ( x ; \theta ) d x } \end{array}
$$

$$
= \arg \operatorname* { m i n } _ { \theta } \mathrm { K L } \left( P _ { x \sim N _ { o } } ( x ) | | P _ { x \sim N _ { v e c } } ( x ; \theta ) \right)
$$

$$
E _ { x \sim P _ { x \sim N _ { o } } } < E _ { x \sim N _ { v e c } }
$$

此处可以用极大似然法（参考传统的生成对抗网络）可以证明argming $K L \big ( P _ { x \sim N _ { o } } | | P _ { x \sim N _ { v e c } } \big )$ ；从而推导出 $\begin{array} { r } { G ^ { * } = { a r g } \operatorname* { m i n } _ { G } \operatorname* { m a x } _ { D } V ( G , D ) } \end{array}$ 从而证明配网单线图的二阶相似性可以通过对抗生成网络予以保证。

# 3.6损失函数

通过建立利用生成对抗网络来保持函数的一阶相似性，因此在对抗网络中，对于对抗网络损失函数定义如下：

$$
\mathcal { L } _ { \mathrm { G A N } } ( \mathrm { G } , \mathrm { D } , N _ { o } , N _ { v e c } ) = \mathbb { E } _ { y \sim P _ { y \sim N _ { o } } } [ l o g D ( y ) ] + \mathbb { E } _ { x \sim P _ { x \sim N _ { v e c } } } \left[ l o g \left( 1 - D \big ( G ( x ) \big ) \right) \right]
$$

对于一阶相似性根据其定义，需要保持两个节点在高维的连接概率和在低维的连接概率保持一致，因此其一致性的损失函数应该保持如下：

$$
\mathcal { L } _ { \mathrm { c o n s i s t e n c y } } ( N _ { o } , N _ { v e c } , M _ { o } , M _ { v e c } ) = | | N _ { o } - M _ { o } | | _ { 2 } - | | N _ { v e c } - M _ { v e c } | | _ { 2 }
$$

通过这两个损失函数，从而获取到网络特征表示中从高维向低维映射时，满足相似性的定义。

# 3.7算法描述

设高维节点序列为： $\left\{ \ A _ { o } , B _ { o } , C _ { o , \dots \dots } \right\}$ 低维节点序列为： $\left\{ { B _ { v e c , } } C _ { v e c , \dots } \right\}$

1）计算第一个低维节点 $B _ { v e c , }$ ，取高维节点 ${ \sf A } _ { 0 }$ 和 $B _ { o }$ 输入生成器，得到低维节点 $B _ { v e c , }$ ；

2）计算低维节点Bvec,和高维节点A的一阶相似性，即Lconsistency(Ao,Avec,B,Bvec);  
3）计算二阶相似性 $B _ { o }$ 和 $B _ { v e c , }$ 的二阶相似性，即 $\mathcal { L } _ { \mathrm { G A N } } ( \mathrm { G } , \mathrm { D } , B _ { o } , B _ { v e c } )$ （204号  
4）取低维节点 $B _ { v e c , }$ 和高维节点 $C _ { o }$ ，输入生成器，得到低维节点 $C _ { v e c , }$ ;  
5）重复步骤2）和3)，直到生成所有的低维节点序列;

# 4．实验

# 4.1验证

对于本文提出的配网单线图网络表示算法的验证所采用的数据以某一地区电网10KV馈线为例；为了便于读取先统一使用 SG-CIM模型文件来描述设备和设备间的拓扑关系；根据上文的推导流程，首先需要计算出配网单线图的节点序列；然后根据节点序列来计算各节点的低维表示，为了验证算法的效果，使用 $t - S N E$ 比对在高纬度和低维度上节点分布大致一致，说明网络的二阶相似性；通过比对两个节点间（一个高纬度，一个低维度）的连接权重值，证明一阶相似性。

现以图1的配网单线图为例，进行网络特征计算，可得如下的计算结果：

![](images/49af589310aa0ed13d7748ebfc67fa57ca4017f7b66f7bd32167ee7494c604d2.jpg)  
图9网络特征t-SNE图，红色为高维度点，绿色为低维度点

![](images/44a658fddf60e90242a7b6277a7d7a243f486f7d8fca3cbee6f341da7fa84a6d.jpg)  
图10网络连接权重值红色为高维度，绿色为低维度

# 4.2节点权重值改进

在实验过程中可以发现，部分节点的在低维度空间通过 $t - S N E$ 方法进行表示时，出现节点值趋近于0,在表示连接权重值时，越远离的电源点的值在低维度表示中值也越趋近于0。这主要是节点的权重值随着电流的流动方向，节点的权重值以 $1 0 ^ { - 1 }$ 依次下降。由于一条主干线或分支线上配网单线图的节点少则十几个多则几十个，这样节点权重值在数量级上可能相差10的负几十次幂，对于越远离的电源点的节点其权重值基本上已经趋近于0；在计算时其值已经基本失真了，这样不利于表达网络特征。因此需要对网络的权重值表达方式进行改进。

对于权重值的表达可以根据对数的定义，将权重值改为使用对数进行表达，缩减节点数列的权重值间的数值差距；如节点权重值为： $\{ 1 , 1 0 ^ { - 1 } , 1 0 ^ { - 2 } , 1 0 ^ { - 3 } , 1 0 ^ { - 4 } , 1 0 ^ { - 5 } , 1 0 ^ { - 6 } \dots \}$ ，取对数后就变为： $\{ 1 , - 1 , - 2 , - 3 , - 4 , - 5 , - 6 \dots \}$ ，节点序列中第一个节点为电源点，为了体现其重要性，值保持为1。

除了第一个节点外，其他节点为负值，为了在后续进行网络特征计算的简洁快速，可以采用如下方式进行计算：

定义数组V，其中 $V _ { i }$ 表示数组中的i个元素，那么这个元素的值就可以按以下方式进行计算：

$$
W _ { \mathrm { i } } = 1 - { \frac { V _ { i } } { \sum _ { j } V _ { j } } }
$$

也就是说，是该元素的权重值，与所有元素权重值和的比值，并与1相减。如序列：$\{ 1 , - 1 , - 2 , - 3 , - 4 , - 5 , - 6 \}$ ，采用该方式结算结果为：{1,0.952,0.904，0.856，0.808，0.76，0.712},采用该方式进行计算节点权重值的收敛速度大大的降低了，并且明确的表达了层次间节点与电源点权重的递减关系。

通过新改进的权重值表示方法，对于配网单线图的网络特征重新进行了计算，以图1的计算结果为例，可以看到整体的效果有了大大的提升。

![](images/2e3a46e51084dd4803a7e74476d74f640d16fee969df9627fc5c3b011159d8c8.jpg)  
图11网络特征t-SNE图，红色为高维度点，绿色为低维度点

![](images/dd525c2c9287e98bb409d271b50fe32652c50da6272b8b4f47da77a3a9538871.jpg)  
图12网络连接权重值红色为高维度，绿色为低维度

# 5结束语

在本文中通过对于配网单线图的电力连接特性为出发点，详细的讨论了如何建立配网单线图的连接模型，通过建立节点序列定义了构成配网单线图各设备节点的连接关系权重，并以设备与电源点的连接关系建立了节点序列，通过重新定义了配网单线图的零阶、一阶和二阶相似性，来构建基于生成对抗网络的网络特性学习网络，并通过对实验数据的分析证明了算法的有效性，为后续基于深度学习的配网单线图自动布局算法奠定了基础。作者：张翔（1978-），男，系统分析师、PMP，主要研究方向：电力系统信息化。E-mail:zhangxiangfjxm@163.com

# 参考文献

[1] 涂存超，杨成等．网络表示学习综述．中国科学 2017(8)   
[2] 宋适宇，何光宇，徐彭亮等.输电网单线图的自动生成算法.电力系统自动化，2007， 31(24):12-15   
[3] 章坚民,楼坚.基于CIM/SVG 和面向对象的配电单线图自动生成.电力系统自动化,2008, 32(22):61-65.   
[4] 张奇峰，闫红漫，于文鹏，等．基于引力斥力模型的配电网单线图自动生成[J]．计算机 应用与软件,2014,31（4）:59-61,65.   
[5] Blei,D.M.;Ng,A.Y.；and Jordan,M.I.2O03.Latentdirichlet allocation.Journal of machine Learning research3(Jan):993-1022.   
[6] Cao, S.; Lu,W.; and Xu, Q. 2O16. Deep neural networks for learning graph representations. In AAAI, 1145-1152.   
[7] K.Bousmalis,N.Silberman,D. Dohan,D. Erhan,and D. Krishnan.Unsupervised pixel-level domain adaptation with generative adversarial networks.arXiv preprint arXiv:1612.05424,2016. [8] J.-Y.Zhu,P. Kr"ahenb"uhl,E.Shechtman,and A.A.Efros. Generative visual manipulation on the natural image manifold.In ECCV, 2016.