# 实现家庭服务机器人中文指令解析问题研究

徐园园，孔令富，高胜男

(燕山大学 信息科学与工程学院 河北省计算机虚拟技术与系统集成重点实验室，河北 秦皇岛 066004)

摘要：为了实现家庭服务机器人在无人干预的情况下自主地执行中文指令中蕴涵的服务任务，提出一种基于回答集的中文指令任务规划方法，将组块标注和回答集编程(answer set programming，ASP)应用于家庭服务机器人任务规划。首先通过组块标注对中文指令进行预处理，然后根据转换规则将关键信息转换为谓词集，并将它转写成 ASP 规则。此外，给出中文服务指令处理的各个环节的实验结果，并结合实例展示从谓词集到机器人可以执行的动作序列的映射过程。最后，通过合并部分原子动作的方式对回答集进行改进，提高了求解效率，并在任务规划时加入了成本规划，确认求得最优动作序列，该方法对促进自然人-机器人交互技术的发展有重要的意义。

关键词：回答集编程；任务规划；组块标注；谓词集 中图分类号：TP391 doi:10.3969/j.issn.1001-3695.2017.07.0690

# Study on Chinese instruction parser issues for home service robot

Xu Yuanyuan, Kong Lingfu, Gao Shengnan (KeyLaboratoryforComputer VirtualTchnology&SystemIntegrationofHebeiShoolofInformationScience&Engineering, Yanshan University,Qinhuangdao Hebei O66oo4, China)

Abstract:Toaddressthe problemofhome servicerobot whichcanautonomously execute servicetaskcontained inthe Chinese instruction,androbot whichcanautonomouslydeal with Chinese instruction without needingartificial interference,this paper usedchunk tagsandAnswer SetProgramming(ASP)toresearchthe planing taskofChinese instruction.Firstly,through chunktags preprocessingofChinese instructions wereusedforkeyinformationextraction.Secondlyaccording totransform rules,converted keyinformationintopredicatesets,andthentraslatedittoASPrules.Moreover,theexperimentalresultsof everystepare provided,and some examplesaregiven toilustrate howmappingproce frompredicate sets toactionsquence, which enables the execution ofrobot.Finally,te solving eficiencyofASPhas been improved by mergingatomic motions, and joining thecost in planingtask inorder toconfirmtheoptimal action sequence. Our proposed methodis verysignificant for promoting development ofNature Human-Computation Interaction.

Key Words: answer set programming; planning task; chunk tags; predicate sets

# 0 引言

未来几年，随着人工智能技术的迅速发展，越来越多的机器人将走进普通家庭，代替人类来照顾老人、孩子以及行动不便的残疾人，以提升他们的生活质量。为了更好地实现自然人-机器人交互(human-robot interaction,HRI)，通常借助人-人交互方式，通过自然语言向机器人发布任务指令是较理想、较有效的HRI方式。因此，面向家庭服务机器人的中文指令任务规划问题已成为HRI领域的一个重要研究内容。

任务规划旨在将服务指令转换为机器人可以执行的动作序列或动作序列的描述。目前，在家庭服务机器人研究领域中，关于HRI的语言均以英语为主，而且在英文指令任务规划领域已有不错的研究成果。相较之下，对于中文指令任务规划的研究比较滞后。对于以中文为母语的人来说，并不是所有的人都能够用英文与家庭服务机器人进行交流，因此，本文对中文指令任务规划问题进行一系列的研究工作。在该领域中，中国科技大学使用回答集编程(Answer SetProgramming,ASP)对英文指令任务规划研究取得较大的进展。在文献[12\~15]，陈小平等人提出了一种家庭服务机器人体系结构，并将ASP与自然语言处理(natural language processing,NLP)相结合，实现人类与自主代理的交流，与当前主要通过语音识别和语义识别技术的人-机器人交互方式比较，有更好的扩展性和强大的规划及推理能力。文献[14]从程序结论的方面，给出提高ASP求解效率的方法，提高了家庭服务机器人的自动任务规划的能力，并在“可佳”

家庭服务机器人上实现相应的系统，对服务机器人中智能问题求解进行细致和系统性的测试，“可佳”在仿真测试中表现优异，能够自主的完成一些基本任务和复杂任务，并且从人机对话中获取因果知识，结果表明ASP能够有效的实现服务机器人的部分认知功能；在文献[17]，高胜男等设计了一种服务任务解析模板，机器人可以通过模板信息将中文服务指令映射为动作序列，并通过仿真实验验证了该方法的有效性和可行性。

综上所述，使用ASP求解英文指令任务规划问题可以得到一组动作序列，但求解效率低及如何求得最优规划仍是目前存在的问题。此外，中文指令解析与英文指令相较，前者在预处理和任务规划问题上均有一定的难度，主要有三个方面的原因：a)国内外学者对英文指令的研究较早且成熟，中文指令的研究起步较晚，并且英文指令的处理方法并不完全适用于中文指令；b)中文指令的表达比较随意，一种语义可能有多种表达方式；c)中文指令的同一种表达方式放入不同的语境中，语义有所不同。在文献[17]中使用服务任务解析模板方法处理的中文服务指令类型比较固定，灵活性不够高。针对上述存在的问题，本文对ASP进行改进并使其适用于中文服务指令的任务规划处理，通过合并一些原子动作的方法简化了ASP的实例化求解过程，提高了ASP的求解效率。此外，本文试图明确执行动作规划的最小成本，即找到最优规划，从而更好地实现中文服务指令任务规划过程。本文以家庭环境和服务机器人为背景，解决中文指令预处理及使用ASP编程解决中文服务指令的任务解析问题。

# 1 家庭服务机器人系统架构

为了解决家庭服务机器人的中文指令任务规划的问题研究，本文提出一种支持家庭服务机器人中文指令自主处理体系结构，如图1所示，将中文服务指令解析过程分为下面两个模块。

![](images/8cf5880eb2e94c04fc36a5b9bba06ac996622baa715782d403481aa2e35c6e76.jpg)  
图1中文服务指令自主处理体系结构

指令预处理模块包含组块标注和谓词集转换，以及一个语言知识库(LanguageKB)，该层的主要功能是对中文指令中用户与机器人对话的理解，通过组块标注和谓词转换等NLP处理技巧，为任务规划做准备。

任务规划模块包含任务信息、场景信息、ASP规则、传感器以及一个领域知识库(DomainKB)，机器人在对指令处理所需的领域知识，可以从领域知识库获取，如某两个位置之间的距离、两物品之间的关系等。用户对任务指令进行解析，获得场景信息和任务信息，编写ASP规则，调用iclingo求解器，最后求解得到一组机器人可以执行的动作序列。

# 2 中文服务指令预处理

# 2.1中文服务指令语料

本课题组搜集了一个小型的语料库，给相关研究提供一个实验平台。总的来说，搜集的中文指令都是用户在家庭环境中向服务机器人发布较频繁的服务指令，结构比较简单，但其中均包含机器人执行中文指令需要的关键信息，如机器人操作的物品，物品放置的位置以及服务的人等。A、B、C类指令包含了不同形式的任务信息，D类指令较特殊，除了任务信息外，还有对环境的描述信息。其中，A类指令结构是机器人-人-物品交互指令；B类指令是机器人-物品-位置交互指令；C类指令是机器人-物品交互指令。4类典型的中文服务指令如下：

A类：(1)给我一瓶矿泉水  
(2)给 Anne 一个苹果  
B类： (1)把碗放到餐桌上  
(2)搬一把椅子到电视机前面  
C类： (1)关客厅的门  
(2)打开电视机  
D类：(1)给Jack一个苹果，苹果在桌子上  
(2)把书放在书桌上，给Tom一杯水

# 2.2 句法分析

借鉴文献[19]，通过组块标注的方法对中文指令进行句法分析。限于篇幅，本文仅对上述每类指令中的第一条服务指令进行预处理操作。服务指令中的基本组块分别有目标组块tc、服务组块sc、位置组块lc、动作组块ac，若不满足基本组块规则，标注为null。

对4条典型中文指令分别针对4种对象类型进行组块标注，句法分析过程如表1～4所示。

表1A类指令的句法分析过程  

<html><body><table><tr><td>过程</td><td>表现形式</td></tr><tr><td>指令识别</td><td>给我 一瓶矿泉水</td></tr><tr><td>词性标注</td><td>给/v， 我/r，一/m，瓶/q，矿泉水/n</td></tr><tr><td>组块标注</td><td>给/ac， 我/sc，一瓶矿泉水/tc</td></tr></table></body></html>

表2B类指令的句法分析过程  

<html><body><table><tr><td>过程</td><td>表现形式</td></tr><tr><td>指令识别</td><td>把碗放在餐桌上</td></tr><tr><td>词性标注</td><td>把/p，碗/n，放/v，在/p，餐桌/n，上/f</td></tr><tr><td>组块标注</td><td>把/null，碗/tc，放/ac，在/null，餐桌上/lc</td></tr></table></body></html>

表3C类指令的句法分析过程  

<html><body><table><tr><td>过程</td><td>表现形式</td></tr><tr><td>指令识别</td><td>关客厅的门</td></tr><tr><td>词性标注</td><td>关/v，客厅/n，的/u，门/n</td></tr><tr><td>组块标注</td><td>关/ac，客厅的门/tc</td></tr></table></body></html>

表4D类指令的句法分析过程  

<html><body><table><tr><td>过程</td><td>表现形式</td></tr><tr><td>指令识别</td><td>给 Jack一个苹果，苹果在桌子上</td></tr><tr><td>词性标注</td><td>给/v，Jack/nr，一/m，个/q，苹果/n，苹果/n，在/p，桌子 /n，上/f</td></tr><tr><td></td><td>组块标注给/ac，Jack/sc，一个苹果/tc，苹果/tc，在/null，桌子上/lc</td></tr></table></body></html>

# 2.3谓词转换规则

面向机器人的中文指令任务规划问题，首先要理解中文指令中的任务信息。本文处理的中文指令大都是简单的自然语言，指令中的词汇基本都是受限的，所以要做的预处理操作比较简单。在上一节中，实现了对中文指令的词性标注和组块标注，得到指令中的关键词及语义组块的关系。此外，目标组块在语义上对应的是机器人要操作的物品；服务组块在语义上表示的是需要服务的人；位置组块在语义上表示的是物品要放置的位置；动作组块在语义上表示的是机器人需要对目标组块所做的操作。

本文谓词转换方法与文献[18]相似，都是解决如何将关键信息转换为谓词集的问题，后者仅是按照指令中出现的关键词转换为相应的谓词集，本文的方法是根据关键词与语义组块的组合关系对应为谓词集，如关键词“去/到”和位置组块的组合才能对应为谓词集move $( \boldsymbol { X } )$ ，其中X表示位置组块表示的位置信息。关键词“放入/放到”和其前后两个目标组块的组合关系对应谓词集putin(objA,objb)，其中objA，objb表示两个目标组块的信息。这样使转换规则更严谨，准确性提高，避免了简单对应造成的错误。

通过上述中文指令中关键词与各类语义组块组合的关系，得到关键词及语义组块转换为谓词集的规则，如表5所示。

表5谓词集转换规则表  

<html><body><table><tr><td>序列</td><td>关键词及语义组块</td><td>谓词集</td></tr><tr><td>1</td><td>去/ac+lc</td><td>move(X)</td></tr><tr><td>2</td><td>给/ac+sc</td><td>give(human, objA)</td></tr><tr><td>3</td><td>拿起/ac+tc</td><td>pickup(objA)</td></tr><tr><td>4</td><td>tci+放在/ac+tc2</td><td>putdown(objA, objB)</td></tr><tr><td>5</td><td>tc1+在/null+tc2+上/lc</td><td>on(objA,objB)</td></tr><tr><td>6</td><td>放下/ac+tc</td><td>putdown(objA)</td></tr><tr><td>7</td><td>关闭/ac+tc</td><td>close(objA)</td></tr><tr><td>8</td><td>打开/ac+tc</td><td>open(objA)</td></tr><tr><td>9</td><td>tci+放入/ac+tc2</td><td>putin(objA, objB)</td></tr><tr><td>10</td><td>tci+取出/ac+tc2</td><td>takeout(objA, objB)</td></tr><tr><td>11</td><td>抓住/ac+tc</td><td>catch(objA)</td></tr></table></body></html>

其中：

move $( X )$ ：表示机器人移动到X位置。执行的条件是机器人在除X的其他位置。执行后，机器人的位置是X位置，不受此动作影响的其他属性不变（若机器人的手爪或者盘子中有小物体，则小物体的位置也跟随机器人一起移动）。

give(human,objA)：机器人将物品A给人。执行的条件是机器人的手爪不为空，物品A为小物品（小物品是可以移动的）。执行后，机器人的手爪为空，机器人与用户在的相同位置。

putdown(objA)：机器人将物品A放下。执行条件为物品A在机器人的手爪中，物体A为小物品。执行后机器人的手爪为空，物品A的位置不变。

putdown(objA,objb)：机器人将物品A放在物品B上。执行条件为机器人的手爪中有物品A，机器人的位置与物品B的位置相同，物品A为小物品。执行后，机器人的手爪为空，物品A和物品B在相同的位置。

$\mathrm { o n } ( o b j _ { A } , o b j _ { B } )$ ：物品A在物品B上。此谓词仅是对场景信息的描述，不做任何执行。

pickup(objA)：表示机器人拿起物品A。执行条件是机器人的手爪为空，物品A为小物品，机器人与物品A在同一位置。执行效果为机器人的手爪不为空，其他状态属性不变。

catch(objA)：表示机器人抓住物品 $\mathbf { A } _ { \circ }$ 执行条件是机器人的手爪为空，机器人与物品A在同一位置，物品A为小物品。执行效果为机器人的手爪不为空，机器人的位置为物品A的位置，其他状态属性不变。

open(objb)：机器人打开容器B的门。执行条件为物品B是容器（内部可以放入小物品），容器B的门是关闭的，机器人和容器B在同一位置上。执行后，容器的门是打开的，其余属性不变。

close(objb)：机器人关上容器B的门。执行条件为机器人和容器B在同一位置上，容器B的门是打开的。执行效果为容器的门是关闭的，其他属性不变。

putin(objA,objb)：机器人将小物品A放入容器B中。执行条件物品B为容器B（内部是可以放入小物品），机器人和容器B在同一位置，小物品A在机器人的手爪中，并且容器B的门是开着的。执行效果为小物品A在B的内部，机器人的手爪为空，其他属性不变。

takeout(objA,objb)：机器人将小物品A从容器B中取出，执行条件为机器人和容器B在同一位置，小物品A在容器 B中，B的门是打开的。执行效果为小物品在机器人的手爪中，小物品A不在B的内部，其他属性不变。

# 3 中文服务指令任务规划

# 3.1中文服务指令流程图

在家庭环境中，面向机器人的中文指令由场景描述(scenariodescription)和任务描述(taskdescription)组成。其中，场景描述确定家庭环境的初始状态，提供的信息包括场景中的物品的类型、位置及其他的属性，同时也包括机器人当前的状态；

任务描述是用户下达任务的详细信息，包括一个或多个任务、约束和其他的信息。例如D类服务指令“给Jack一个苹果，苹果在餐桌上”中，前者是对用户所下达的任务的描述，后者就是对家庭环境中场景的描述。使用ASP求解中文服务指令任务序列的流程，如图2所示。

![](images/472ae6e0be93e1e1a54cbb8addd82c5802bf2fbef47a1aaaf5a30bd089e89030.jpg)  
图2求解中文服务指令流程图

从图2中可以看出，基于ASP对中文指令求解动作序列的过程如下：

a)对指令中的信息进行判定，如果是任务信息，则对任务信息进行处理，将任务信息以事实或规则的形式添加到ASP程序；若是场景信息，则对场景信息处理。并按照谓词转换规则转换为谓词集。

b)根据ASP求解状态及初始、目标状态，对ASP求解，调用iclingo求解器进行求解。

c)求得最优的动作序列。如果时间超过5s则显示超时，需要对场景信息重新规划，查看是否有错误的或遗漏的信息，直到得到最优的序列为止。

# 3.2中文服务任务规划

任务规划旨在根据环境描述，初始、目标状态及原子动作的相关内容，将中文指令映射为机器人可执行的最优动作序列。首先，将服务指令转写成指令完成后的状态描述，并将这些状态描述以约束的形式添加到ASP程序中。机器人运行过程中，中文指令预处理模块将用户指令转换为内部逻辑公式，任务规划模块将这些公式以事实的形式添加到ASP程序中，激活相应的约束，最终形成满足的目标状态。在此基础上，计算回答集相当于通过经典的任务规划方法，得到机器人从初始状态到目标状态的动作序列。其余的信息也通过上述的方式，作为事实或规则添加到ASP程序中，利用领域知识从这些信息中推导出更多的知识[[2]。

ASP作为具有非单调推理能力的知识表示和推理的一般工具[12]，可以用ASP刻画机器人内部信息，包括机器人对环境的感知和其行动能力，将自然语言等外部输入信息转换为相应的ASP规则，并利用这些信息进行解析和诊断，解决中文服务指令任务规划的问题。ASP的求解包括两个步骤：

a)实例化，将程序中含有的变量实例化为相应的实例。

b)模型搜索，计算实例化后程序的回答集。

本文使用的iclingo，是一种增量式的ASP求解器，基于clasp 和Gringo两种方法，利用划分序列的方法增量式的求解逻辑程序。由于在实际问题中，单独计算前部分的回答集可能太多，划分序列的方法效率不高。iclingo不再直接计算前面程序的回答集，而是根据估计出的原子来实例化后面的程序。

在任务规划中的每个子任务叫做一个ASP行动。行动和环境特征在ASP中用谓词集表示。例如，在家庭环境中，引入$\mathrm { o n } ( A , B , { \cal T } )$ 表示在T时刻，小物体A在物体B的上面;location(A,$X , T )$ 表示在 $\mathrm { \Delta T }$ 时刻，小物体A处于X位置；holding $( A , T )$ 表示在T时刻，物体A在机器人手爪或盘子中。例如，机器人的“move”动作与谓词“location”表述如下所示：

$h o l d s ( l o c a t i o n ( A , X ) , T + 1 ) \gets o c c u r s ( m o \nu e ( A , X ) , T ) ,$ $o b j ( A ) , n u m b e r ( X ) , t i m e ( T ) , T < l a s t t i m e .$   
（20 $ \mathit { o c c u r s } ( m o \nu e ( X ) , T ) , h o l d s ( l o c a t i o n ( Z , X ) , T ) ,$ $a g e n t ( Z ) , n u m b e r ( X ) , t i m e ( T ) , T < l a s t t i m e .$   
$h o l d s ( l o c a t i o n ( A , X ) , T + 1 ) \gets h o l d s ( l o c a t i o n ( A , X ) , T ) ,$   
（20 $n o t \_ h o l d s ( l o c a t i o n ( A , X ) , T + 1 ) , o b j ( A ) , n u m b e r ( X ) ,$ $t i m e ( T ) , T < l a s t t i m e .$

# 3.3成本规划

在上节中，将服务指令转写为ASP规则，调用求解器可以求得大小不等的规划，任意地选择其中一个去执行。但在实例中，这些规划是不等价的，因为在现实生活中，不同的动作有不同的成本（比如执行该动作所用的时间、所耗费的能量、所做的功等）。本文将动作在执行中所用的时间作为成本规划的首要确定要素。

在这一节中，展示如何将成本与动作相结合，这样可以选择一个成本最小的规划来实现这个目标。本文将成本定义为一个函数，包含动作被完成和动作开始的状态两个参数。在本项目中，为了计算简便，假定除了move之外的所有动作有下面的固定成本：

$c o s t ( 1 , T ) \colon - g i \nu e ( h u m a n , A ) , s m a l l ( A ) , o b j ( A ) ,$ T<lasttime.   
（20 $c o s t ( 2 , T ) \colon - p i c k u p ( A ) , s m a l l ( A ) , o b j ( A ) , T < l a s t t i m e .$   
cost(2,T):-putdown(A),small(A),obj(A),T<lasttime.   
（204 $c o s t ( 1 , T ) : - t o p l a t e ( A ) , s m a l l ( A ) , o b j ( A ) , T < l a s t t i m e .$ （20   
cost(1,T):-fromplate(A),small(A),obj(A),T<lasttime.   
cost(1,T):-open(B),obj(B),container $( B ) , T <$ lasttime.   
cost(1,T):-close(B),obj(B),container(B),T<lasttime.   
$c o s t ( 2 , T ) \colon - p u t i n ( A , B ) , s m a l l ( A ) , o b j ( A ) , o b j ( B ) ,$ （2 $c o n t a i n e r ( B ) , T < l a s t t i m e .$ （2   
$c o s t ( 2 , T ) \colon - p u t u p ( A , B ) , s m a l l ( A ) , o b j ( A ) , o b j ( B ) ,$ $c o n t a i n e r ( B ) , T < l a s t t i m e .$

现在定义move动作的成本，该成本取决于机器人执行该动作前的初始位置。计算从位置Y移动到位置X的成本如下：

$$
c o s t ( @ t i m e ( \mathbf { X } , \mathbf { Y } ) , T ) : - m o \nu e ( X , T ) , l o c ( X ) , l o c ( Y ) ,
$$

T<lasttime.

在现实生活中，在每次执行move动作时，机器人的初始位置是无法确定的，故评估动作move(A)的真实值是困难的，当机器人的初始位置无法确定时，则本文假定move 动作的固定成本：

$$
c o s t ( 4 , T ) \colon - \ m o \nu e ( X , T ) , l o c ( X ) , T < l a s t t i m e .
$$

根据上述成本规划，可以发现最优规划不一定是最短规划。在成本规划中，仅需要调用一次iclingo，增量 $\mathfrak { n }$ 直接分配为max_len。使用上面的优化语句，本文根据iclingo找到最优的回答集，最优规划的大小在max_len之内。

# 3.4人机交互的任务规划

机器人有一个感知动作，如果机器人不知道某人X或者某物品A的位置，机器人可以在时刻T询问用户它们的位置信息。

动作askloc(A，T)表示在时刻T，机器人询问物品A的位置。动作 $\operatorname { a s k l o c } ( X , \ T )$ 表示在时刻 $\mathrm { \Delta T }$ ，机器人询问人X的位置。当进行任务规划的时候，可以通过人机对话的方式来获取物品的位置，执行后是得到某人或某物的位置回答，ASP规则如下：

answe $\boldsymbol { \mathfrak { r } } ( a t ( A , X ) , 1 ) : - o c c u r s ( a s k l o c ( A ) , 1 ) ,$ $h ( a t ( A , X ) , 0 ) , o b j ( A ) .$   
ans $\begin{array} { r } { \mathinner { \mathopen { : } \mathclose \bgroup \left( a t ( 0 , X ) , 1 \aftergroup \egroup \right) } : - o c c u r s ( a s k l o c ( 0 ) , 1 ) , } \end{array}$ $h ( a t ( 0 , X ) , 0 ) , l o c ( X ) .$ （204   
answer(inside(A,B),1) :-occurs(askloc(A),1), $h ( i n s i d e ( A , B ) , 0 ) , o b j ( A ) , s m a l l ( A ) , o b j ( B ) ,$ container(B).

# 4 实例分析

# 4.1环境信息

在本节中，以4类典型的中文服务指令为例，使用ASP求解最优动作序列如下：

环境信息以下面的形式存放在知识库中，家庭环境中的物品和机器人位置被分别分配一个正整数表示。为简单起见，数字0表示“nothing”，数字1表示机器人在1号位置。不同的位置用一个非负整数表示。家庭环境中机器人及物品信息如下所示：

$r o b o t : = s o r t ( 1 ) \mid l o c ( 1 , 1 ) \mid p l a t e ( 0 ) \mid h o l d i n g ( 0 ) .$ $m e : = s o r t ( 2 ) \mid l o c ( 2 , 2 ) .$   
$x i a o h o n g : = s o r t ( 3 ) \mid l o c ( 3 , 3 ) .$   
$w a t e r : = s o r t ( 5 ) \mid l o c ( 5 , 1 0 ) \mid s i z e ( s m a l l ) \mid$ type(mineral).  
$b o w l : = s o r t ( 1 3 ) \mid l o c ( 1 3 , 6 ) \mid s i z e ( s m a l l ) .$   
$t a b l e : = s o r t ( 1 6 ) \mid l o c ( 1 6 , 1 0 ) \mid s i z e ( b i g ) .$   
$d o o r : = s o r t ( 2 3 ) \mid l o c ( 2 3 , 1 3 ) \mid s i z e ( b i g )$ |type(drawingroom).  
$a p p l e : = s o r t ( 1 8 ) \mid l o c ( 1 8 , 1 0 ) \mid c o l o r ( r e d )$ |size(small).

# 4.2 回答集求解

4.2.1用回答集求解A指令

在A类指令中，“给我一瓶矿泉水”，通过预处理操作，可以得到指令的关键词以及语义组块，根据谓词集转换规则，可转换为下面的谓词集形式：

$$
\left\{ g i \nu e ( \mathbf { x } , y ) , m e ( x ) , m i n e r a l ( y ) , w a t e r ( y ) \right\}
$$

将谓词 $g i \nu e ( m e , w a t e r )$ 以事实的形式添加到ASP规则中，同时还有两条对应的约束如下：

give(me,water).   
$\begin{array} { r } { \mathrm { ~ : ~ } - n o t l o c ( B , X , T ) , l o c ( A , X , T ) , g i \nu e ( A , B ) , } \end{array}$ $o b j ( A ) , o b j ( B ) , s m a l l ( B ) , T < l a s t t i m e .$   
$\because n o t e m p t y ( T ) , g i \nu e ( A , B ) , o b j ( A ) , o b j ( B ) , s m a l l ( B ) ,$ $n u m b e r ( X ) , T < l a s t t i m e .$

结合领域知识库中的场景描述信息求解得到如下动作序列为：

# 4.2.2用回答集求解B指令

在B类指令中，“把碗放到餐桌上”，转换为谓词集形式：

$$
\left\{ p u t d o w n ( x , y ) , b o w l ( x ) , t a b l e ( y ) \right\}
$$

将putdown(bowl,table)以事实的形式添加到ASP规则，同时还有两条对应的两条约束如下：

putdown(bowl,table).   
:-location(A,X,T),location $( B , X , T )$ ,putdown $( A , B )$ 5 small(A),obj(A),obj(B),number(X),T $\prec$ lasttime.   
:-handempty(T),putdown $( A , B )$ ,small(A),obj(A), obj(B)， $\Gamma <$ lasttime.

上述条件结合领域知识库中的场景信息可得到下面的动作序列：

# 4.2.3用回答集求解C指令

在C类指令中，“关客厅的门”，转换为谓词集形式：$\{ c l o s e ( x ) , d r a w i n g ( x ) , r o o m ( x ) , d o o r ( x ) \} .$

将 $c l o s e ( d o o r )$ 以事实的形式添加到ASP规则，同时还有与其对应的约束如下：

$$
\begin{array} { r l } & { c l o s e ( d o o r ) . } \\ & { : - n o t o p e n ( x , T ) , \longrightarrow o p e n ( x , T ) , d r a w i n g \left( x \right) , } \\ & { \qquad r o o m ( x ) , d o o r ( x ) , T < l a s t t i m e . } \end{array}
$$

同上，求得动作序列为$o c c u r s ( m o \nu e ( 1 3 ) , 1 ) , o c c u r s ( c l o s e ( 2 3 ) , 2 ) .$

# 4.2.4用回答集求解D指令

在D类指令中，“给Jack一个苹果，苹果在桌子上”，不仅包含一条任务信息，还有一条对场景信息的描述信息。根据谓词集转换规则转换为下面的两组谓词集形式：

$$
\begin{array} { r l } & { \left\{ g i \nu e ( x , y ) , J a c k ( x ) , a p p l e ( y ) \right\} , } \\ & { \left\{ a p p l e ( x ) , o n ( x , y ) , t a b l e ( y ) \right\} . } \end{array}
$$

任务规划模块将任务描述“给Jack一个苹果”转换为谓词give(Jack,apple),作为事实加入到ASP程序中，同时还有与它相应的两条约束如下所示：

$$
\begin{array} { r l } & { g i \nu e ( J a c k , a p p l e ) . } \\ & { \mathrel { \mathop : } \ - n o t \ l o c ( B , X , T ) , l o c ( A , X , T ) , g i \nu e ( A , B ) , } \\ & { \quad o b j ( A ) , s m a l l ( B ) , o b j ( B ) , n u m b e r ( X ) , T < l a s t t i m e . } \\ & { \mathrel { \mathop : } \ - n o t e m p t y ( T ) , g i \nu e ( A , B ) , o b j ( A ) , s m a l l ( B ) , o b j ( B ) , } \\ & { \quad n u m b e r ( X ) . } \end{array}
$$

将上述场景描述“苹果在桌子上”的原子动作转换为谓词$o n ( a p p l e , t a b l e )$ ,作为事实加入ASP程序中，通常领域知识库中还有表达领域知识的其他规则，例如

on(book,table). small $\operatorname { \_ { \rho } } o b j ( A ) : - o n ( A , B ) , o b \mathrm { j } ( B ) .$ $l o c ( A , X , 0 ) : - l o c ( B , X , 0 ) , o n ( A , B ) , n u m b e r ( X ) .$

后两条规则表明，如果小物品A在物品B的上面，则物体A的位置与物体B在相同的位置。从服务指令“苹果在桌子上”得出，苹果与桌子在相同位置。

从领域知识库中可以得到以下知识：物品18是苹果，苹果在桌子上并且桌子在位置10，Jack的位置是3，机器人的位置为1。默认任何两位置之间是可以到达的。当没有明确说明目标对象的数量时，默认为1。通过计算ASP程序的回答集，可以得到动作序列：

occurs(move(10),1),occurs(catch(18),2), occurs(move(3),3),occurs(give(3,18),4).

其中18表示"苹果"的编号。整个过程为，首先移动到位置10,接着抓住物品18(即“苹果”)，然后移动到位置3，最后把手中的物品给Jack。该ASP程序的回答集中包含一条行动序列，这一条序列就是机器人完成该指令的行动步骤。

家庭服务机器人可以从领域知识库中获得两个位置之间的距离，然后规划出最短的路径，传递到动作执行层去操作，最后完成整个机器人行为规划的过程。

# 4.3宏动作回答集求解

经过国内外学者多年的研究，回答集理论研究已经较成熟，但是由于常例化穷举的过程，让ASP的求解效率较低，限制了其广泛应用。在上一节中，对4类典型的服务指令使用ASP进行了求解，得到指令执行的序列。通过观察发现在任务序列中有大量move动作的规划，其影响了任务规划的效率。据此，本项目通过将某些常规动作指令在进行规划前，进行原子动作的合并操作，这样可以有效的减少任务规划的时间，从而提高其求解效率。例如，在A类指令中，在拿起矿泉水前，必须满足机器人与矿泉水必须在同一位置，并且在将矿泉水给“我”时，必须要求机器人要与“我”在同一位置。因此，对服务指令进行任务规划前，可以将move(A)动作与catch(A)动作进行原子的动作的合并，从而得到mcatch(A)动作。相应的ASP规则

如下：

$$
\begin{array} { c } { { o c c u r s ( m { \bf c a t c h } ( A ) , T ) : - o c c u r s ( m o \nu e ( X ) , T ) , } } \\ { { { } } } \\ { { o c c u r s ( c a t c h ( A ) , T + 1 ) } } \end{array}
$$

同上，可将move $( X )$ 动作与give(human, $\cdot \cdot$ 动作合并为动作mgive(A)，相应的ASP规则为：

$$
\begin{array} { c } { { o c c u r s ( m \mathbf { g } i \nu e ( A ) , T ) : - o c c u r s ( m o \nu e ( X ) , T ) , } } \\ { { { } } } \\ { { o c c u r s ( g i \nu e ( A ) , T + 1 ) . } } \end{array}
$$

当机器人操作的对象为一个容器时，比如需要向容器B中放入一个物品A，执行的条件是机器人与容器B在同一位置，并且取物品前需要先执行打开容器的门，执行open $( B )$ 动作，然后把物品A放入容器B中，执行 $\mathrm { p u t i n } ( A , B )$ 动作，最后需要执行关闭容器B的门，执行close $( B )$ 动作，所以可以将上面的4个动作合并为2个复合动作mopen $( B )$ 和piclo $( A , B )$ ，相应的回答集规则是：

$o c c u r s ( m o p e n ( B ) , T ) : - o c c u r s ( m o \nu e ( X ) , T ) ,$ occurs(open(B),T+1). $\begin{array} { r l r } & { } & { o c c u r s ( p i c l o ( A , B ) , T + 1 ) : - o c c u r s ( p u t i n ( A , B ) , T ) , } \\ & { } & { o c c u r s ( c l o s e ( B ) , T + 1 ) . } \end{array}$

通过上述对ASP中部分原子的合并操作可以减少实例化的过程，提高了ASP的求解效率，从而减少对服务指令任务规划的时间。

# 5 实验结果及分析

# 5.1家庭服务机器人仿真平台

仿真平台把家庭服务机器人模拟为3D仿真机器人，并且以家庭环境作为测试环境。机器人通过感知器获得的信息以及通过人机对话得到的信息使用场景信息表示；用户使用中文指令对机器人发出的任务指令使用任务信息描述。平台采用客户端-服务器模式，服务器提供环境描述和评分功能，客户端程序根据这些信息在规定的时间内(不超过5s)进行任务规划，规划后得到的结果返回服务器并对获得的行动序列进行评估。

# 5.2中文服务指令任务规划实验

依据中文指令类型的不同，本文选取4类典型的服务指令，在家庭服务机器人仿真平台上进行实验验证。为了测试对 ASP改进后的求解效率，将本文方法与文献[6]方法比较，通过得到的执行时间和成本规划可以直观地说明本文方法的有效性。

在A类指令，“给我一瓶矿泉水”执行的条件是机器人的手爪中有一瓶矿泉水并且机器人与“我”在同一位置，所以在执行give(me,water)动作前，需要先移动到“矿泉水”的位置，接着抓起一瓶矿泉水，然后移动到“我”所在的位置，最后将矿泉水给“我”。从上述描述可知，在服务指令中，对目标对象进行操作时需要机器人先移动到目标对象的位置。在进行任务规划时，规划序列中有大量的move动作严重的影响了ASP的效率。因此，本文将move(A)与下一服务动作进行合并处理，减少了任务规划的时间，提高了ASP的求解效率。其他的3类指令同上述原理进行部分原子动作合并的操作。

本文从4类指令选取具有代表性的4条服务指令，分别使用文献[6]中简单的ASP方法与改进后的ASP方法求解，结果

如表6所示。

表6实验对比结果表  

<html><body><table><tr><td>指令类型</td><td>典型指令</td><td>ASP 程序回答集</td><td>改进的ASP 程序回答集</td></tr><tr><td>A类</td><td>给我一瓶矿泉水</td><td>occurs(move(10),1),occurs(catch(5),2), occurs(move(2), 3), occurs(give(2,5), 4).</td><td>occurs(mcatch(5),1),occurs(mgive(2,5),2).</td></tr><tr><td>B类</td><td>把碗放在餐桌上</td><td>occurs(move(6),1),occurs(pickup(13),2),</td><td>occurs(mpickup(13),1),occurs(mputdown(13),2).</td></tr><tr><td>C类</td><td>关客厅的门</td><td>occurs(move(10),3),occurs(putdown(13),4). occurs(move(13),1),occurs(close(23),2).</td><td>occurs(mclo(23),1).</td></tr><tr><td></td><td>给Jack一个苹果，</td><td>occurs(move(10),1),occurs(catch(18),2),</td><td></td></tr><tr><td>D类</td><td>苹果在桌子上</td><td>occurs(move(3),3),occurs(give(3,18),4).</td><td>occurs(mcatch(18),1),occurs(mgive(3,18),2).</td></tr></table></body></html>

通过表6可知，两种方法均能求得一组动作序列，并且两组动作序列机器人都是可以执行的，但是从在图3发现改进后的 ASP方法的任务规划时间有明显的减少。本文研究的是每次仅对单条中文指令进行规划，实验结果没有明显的差距，但如果同时对多条指令规划时，减少大量move动作会使执行效率有很大的提高。

在家庭服务机器人仿真平台用两种方法对A类服务指令进行了10次实验，服务指令规划时间如图3所示。

![](images/e74a01e42f08e5a9afd3355614a3b730c9ed6c1e2b91bdd899b2d7b3baa054a3.jpg)  
图3简单ASP方法与改进后ASP方法求解时间比较

通过图3可知，改进后的ASP方法对A类指令的求解时间大约在 $0 . 3 { \sim } 0 . 4 \ \mathrm { s }$ ；未作处理的ASP方法的求解时间变化幅度较大，大约在 $0 . 7 { \sim } 0 . 9 \mathrm { s }$ 。第3次和第8次实验中，任务规划的时间较长，主要原因在于从领域知识库获取场景信息时，获取的信息有遗漏或者错误造成的。由此可知，对ASP使用合并部分原子的方法进行改进，可以有效的提高ASP的求解效率。

实验结果证明，ASP方法可以规划得到家庭服务机器人可以执行的动作序列，也证明了本文中提出的合并部分原子操作的方法能够有助于提高ASP对中文指令进行任务规划的效率。

# 5.3中文服务指令成本规划实验

本节将成本规划加入ASP中，通过对动作序列进行成本计算，可以获得最小成本的规划结果，使得到的任务规划序列为最优结果。此外，还加入了感知动作askloc $( A , X )$ ，可以通过人机交互的方式获取物品或人的位置。

在家庭仿真环境中，机器人与服务对象Tom 在同一个房间中，物品A和物品B在隔壁的另一个房间中，有下面场景信息：robot(1)，location(1，1)，Tom(2)，location(2,2),A(3),location(3,3), B(4),location(4,4)。

对于任务指令“把物品A给Tom"和"把物品B给Tom”，物体及环境信息位置如图4、5所示：

根据上述指令任务信息及环境，可以得到如下两种动作规划：动作序列(1)，执行效果如图4所示。move(1),pickup(3),move(4),give(4,1),move(2),pickup(2),move(4), give(4,2).动作序列(2)，执行效果如图5所示。move(1),pickup(3),toplate(3),move(4),pickup(4),move(2), give(4,2), fromplate(3), give(4,2).

![](images/9b75dd1ad8bc3dd2fead7104027ceff7b4d328ab61632ba7a5abd90a078498c2.jpg)  
图4动作序列1)

![](images/12c7f26eca47ec2b9b124475a36ae6172f2ad4e607690434e927f968febb8be2.jpg)  
图5动作序列2)

按照在4.3节中对动作成本的规定，对动作序列的成本规划进行计算。为了简单起见，在本实验中将move动作的成本规定为固定成本。上述服务指令中求得的动作序列(1)的成本为24。动作序列(2)的成本为22。故按照成本消耗选择成本低的动作序列(2)。由此可知，最优规划不一定是最优规划，加入成本规划有助于找到服务指令的最优规划序列。

# 6 结束语

中文指令由于其语法灵活，结构较随意，对指令进行任务规划时，有一定的难度，故本文首先对其进行了预处理操作，将其结构简化，并按照谓词集转换规则转换为谓词集合，对ASP方法进行改进使其适用中文服务指令任务规划的研究，并且从最后的求解结果观察动作序列，发现求得的任务序列有大量的 move 动作，影响了求解效率。因此，本文对 ASP中的move 动作与其他执行动作进行了合并原子操作，明显提高了求解效率。此外，有一些约定俗成的指令动作也可以进行合并原子的操作，缩短任务规划时间，提高了ASP的求解效率。在此基础上，本文加入了成本规划，对求得的动作序列进行成本消耗的计算，选择成本代价小的而不是任务规划短的动作序列，作为最优动作序列。最后通过仿真实验及实验结果，证明其方法的有效性。

# 参考文献：

[1]任福继，孙晓．智能机器人的现状及发展[J].科技导报,2015,33(21): 32-38.   
[2]Kollar T,Perera V,Nardi D,etal.Learning environmental knowledge from task-based human-robot dialog[C]//Proc of IEEE International Conference on Robotics and Automation.2013: 4304-4309.   
[3]Duvallet F,Kollar T, Stentz A.Imitation learning for natural language direction following through unknown environment [Cl// Proc of IEEE International Conference on Robotics and Automation.2013:1047-1053.   
[4] Johnson D O,Agah A.Human robot interaction through semantic integration of multiple modalities,dialog management,and contexts [J]. International Journal of Social Robotics,2009,1(4):283-305.   
[5]Wu Junhua,Liu Longxia. Chunk parsing and entity relation extracting to chinese text by using conditional random fields model [J].Journal of Intelligent Learning Systems & Applications,2010,2(3): 139-146.   
[6]王凡，范文斌，张雪艳，等.提高回答集编程在家庭机器人仿真上求解 效率初探[J].赤峰学院学报：自然科学版,2014,30(3):19-21.   
[7]Perera V,Veloso M.Handling complex commands as service robot task iequests[CJ/rioc oienauc Hvc. 1.] :AAAI Press,2015: 1177-1183.   
[8]李素建，刘群，白硕．统计和规则相结合的汉语组块分析[J].计算机 研究与发展,2002,39(4):385-391.   
[9] 谢炯坤．面向人机互动的自然语言理解的研究[D].合肥：中国科学 技术大学,2015.   
[10]靳国强，陈小平．面向智能服务机器人任务规划的行动语言扩展[J]. 软件学报,2013,24(7):1614-1625.   
[11] Ivanov K S.Action of robot with adaptive electric drives of modules [M]// Advances on Theory and Practice of Robots and Manipulators.[S.1.] : Springer International Publishing,2014: 563-569.   
[12]陈小平，吉建民，姜节汇，等．一种支持个性化协调的服务机器人体系 结构[J]．南京大学学报：自然科学版,2010,46(2):131-139.   
[13] Chen Xiaoping,Jiang Jiehui, Ji Jianmin,et al. Integrating NLP with reasoning about actions for autonomous agents communicating with humans [C]// Proc of IEEE//WIC//ACM International Joint Conferences on Web Intelligence and Intelligent Agent Technologies.2009:137-140.   
[14]吉建民.提高ASP效率的若干途径及服务机器人上应用[D].合肥： 中国科学技术大学,2010.   
[15] Chen Xiaoping, Xie Jiongkun,Ji jianmin,et al. Toward Open Knowledge Enabling for Human-Robot Interaction [J].Journal of Human-Robot Interaction,2013,1(2): 100-117.   
[16] Cho J, Kim H, Sohn J. Implementing automated robot task planning and execution based on description logic KB [M]/ Simulation, Modeling,and Programming for Autonomous Robots. Berlin: Springer, 2010: 217-228.   
[17]高胜男，孔令富，吴培良．面向室内智能机器人的中文服务指令自主 处理方法[J].机器人,2015,37(4):424-434.   
[18]张博雅．家庭服务机器人中文语音指令解析的研究[D].秦皇岛：燕 山大学,2015.   
[19]李新德，张秀龙，戴先中．一种基于受限自然语言处理的移动机器人 视觉导航方法 [J]．机器人,2012,33(6):742-749.   
[20] Yang F,Khandelwal P,Leoneti M,et al.Planning inanswer set programming while learning action costs for mobile robots [C]// Proc of AAAI Symposium. 2014.