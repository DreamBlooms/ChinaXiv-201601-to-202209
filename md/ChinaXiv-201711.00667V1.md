# 小型液氮零蒸发系统运行特性研究

张洋洋‘²，赵雅楠l\*，闫涛¹，洪国同¹，李洋³（1.中国科学院理化技术研究所，北京，100190；2.中国科学院大学，北京，100049;3.国网山东禹城市供电公司，251200)

摘要：本文介绍的小型液氮零蒸发系统主要由脉冲管制冷机、低温热虹吸管和小型液氮杜瓦等部件组成。其既可以用于低温液体的长期无损存储，也可以作为一种稳定可靠的复合式低温冷源；具有超长寿命、温度均匀稳定、无需补液以及隔离振动和电磁干扰等优点。文中简要介绍了该套小型零蒸发系统的结构设计与热设计，重点对该系统的运行特性进行了初步分析和实验研究，包括启动过程、运行动态、稳态平衡以及变工况运行等，掌握了低温液体零蒸发系统的运行规律。

关键词：零蒸发系统；脉冲管制冷机；热设计；无损存储中途分类号：TB658 文献标识码：A

# Operating Characteristics Study on Small Liquid Nitrogen Zero Boil-off System

ZHANG Yangyang1,², ZHAO Ya-nan1, YAN Tao1, HONG Guotong1,LI Yang3 (1.Technical Institute of Physics and Chemistry, Chinese Academy of Sciences,Beijing,100190, China 2.University of Chinese Academy of Sciences,Beijing,10oo49, China 3.Power Company of Shandong Yucheng of State Grid, Yucheng,251200, China )

Abstract: The small liquid nitrogen Zero boil-off (ZBO） system mainly consists by a pulse tube cryocooler, a thermosyphon and a liquid nitrogen Dewar. It can be used for long-term lossless storage of cryogenic liquids,and also as a reliable integrated cooling source, with advantages of long lifetime, temperature uniformity and stability，while isolate vibration and electromagnetic interference. The structure and thermal design of the ZBO system is briefly introduced,then with a preliminary analysis and a complete experimental study on the operating characteristics of the system,including the process of startup，dynamics running， homeostasis and the dynamic changes. Eventually the operating characteristics of the cryogenic liquids ZBO system are known.

Key words: zero boil-off system; pulse tube cryocooler; thermal design; cryogen lossless storage

# 0引言

由于低温液体工质（液氮、液氮等）的沸点低，其在存储过程中难以避免各种蒸发损耗。在一些不便于补充的特殊场合会带来极大的使用不便，如野外偏远地区、复杂空间或特殊设备、深空探测等[1-3]。同时，随着机械式低温制冷机技术的发展，其制冷高效持久及便利性使其得以广泛应用，但是其不可避免的会有机械振动、电磁干扰以及温度均匀性和稳定性等问题。面对一些特殊的冷却需求，单一的低温工质浸泡式冷却或机械制冷机冷却都无法满足，而两者集成于一体的零蒸发系统取长补短，具备两种冷却方式的优点并避免了各自的不足。

零蒸发存储系统是采用低温制冷机与杜瓦相结合，通过制冷机主动制冷来冷却或冷凝杜瓦中低温工质，抵消杜瓦系统漏热，实现低温液体工质在杜瓦中长期无损保存。零蒸发系统一方面可以用于各种低温液体工质的长期的存储方案，其能够完全消除低温工质蒸发损失、杜绝排放，如地面上大型液氢、液氦无排放存储，或长期太空任务所需的液氢液氧等低温推进剂存储。另一方面，零蒸发系统还可以作为一种复合式低温冷源，其具备了低温液体浸泡蒸发冷却和机械式制冷机两种冷却方式的优点，可实现长寿命、高可靠，冷却温度均匀稳定 [4-5] 0

据此，中科院理化技术研究所研制了一台小型液氮的零蒸发系统装置，该装置主要包括高频脉冲管制冷机、2.5L液氮杜瓦以及热虹吸管等部件，用于研究液氮零蒸发方案的效果及其运行规律。在地面重力环境应用背景下，这套零蒸发系统采用了两相闭式低温热虹吸管（简称热管）实现制冷机与杜瓦的远距离连接和传热。其不仅可以实现远距离的高效冷却，同时有效地隔离了电磁与振动干扰。本文对该系统零蒸发运行状态进行了初步分析，并进行了多次实验研究，验证设计方案的可行性。同时，还探索了变工况下零蒸发系统的运行特性与规律，为将来的实际应用奠定了基础。

# 1结构与热设计简介

整个液氮零蒸发装置的结构示意图如图1所示，其包括三个部分：上部的脉冲管制冷机、中部的低温热虹吸管和下部的零蒸发杜瓦。脉冲管制冷机作为冷源，其包含线性压缩机和小型高频脉冲管冷指等部件；氮工质的热管作为远距离传热部件，其包含冷凝器、蒸发器和气液管路等部件；杜瓦储罐存储一定量的低温液氮并被冷却，其包含液氮储罐、传输管路及悬吊支撑等部件；制冷机冷指、热管和液氮储罐等低温部件都位于的真空罩内。制冷机的冷端与热管的冷凝器直接接触，热管的蒸发器伸入到杜瓦储罐中用于冷却或冷凝储罐中液氮或氮蒸汽，并在其外侧设计了一体的肋片结构以加强换热，热管的冷凝器和蒸发器之间由2根长约 $1 . 2 \mathrm { ~ m ~ }$ 薄壁不锈钢管连接形成封闭回路。杜瓦中液氮储罐采用了高强度低热导率的凯芙拉纤维绳来悬吊支撑于真空罐内，并由长约0.5m的薄壁不锈钢螺旋盘管作为进液和排气的传输管路，大大的减少了固体支撑结构和管道引起的漏热量。

热设计计算主要是对杜瓦低温储罐的漏热进行分析计算，并设计具有匹配传热量的热管，再选择适当制冷量的脉冲管制冷机作为冷源。

基于杜瓦结构分析可知，其漏热途径主要有三个：包覆多层绝热材料的低温储罐与室温真空罐壁间的辐射漏热、输液排气管道传导漏热和悬吊支撑的凯芙拉线的传导漏热。根据传热公式和相关物性参数可计算出三者约为0.53W、0.19W和0.001W，再考虑温度传感器的引线等少量漏热，杜瓦液氮储罐的总漏热量约 $0 . 7 5 \mathrm { ~ W ~ } ^ { [ 5 ] }$ 。

由此要求热管在液氮温区的传热量至少应不小于 $0 . 7 5 \mathrm { ~ W ~ }$ ，并且传热温差应尽可能小。为保证实际运行可靠并具备充裕的余量，以及考虑未来可能增加的冷却负载，因此热管的设计传热量为5W，最大传热温差不超过 $3 \mathrm { K }$ 。再考虑到热管较长低温管路的沿程漏热，因此选择匹配的制冷机为 $5 \mathrm { ~ W ~ } / 8 0 \mathrm { ~ K ~ }$ 型脉冲管制冷机，其在120W电功输入、80K制冷温度下具有最大约5W制冷量，并随着输入电功减小其制冷量可在0至5W间调节，完全可以满足该零蒸发系统的冷却需求。

1 制冷机压缩机，2制冷机冷指，3冷凝器，4上真空罩，5波纹管，  
6 热管液体管，7热管气体管路，8杜瓦传输管路，9凯芙拉线，

![](images/a77ba8c31a95bb902effcbafd6d1122b23c0be592d5b9d0511de5ef0b6e8c2b1.jpg)  
10 蒸发器，11杜瓦液氮储罐12 杜瓦外真空罐图1液氮零蒸发系统结构示意图fig.1 Schematic diagram of the ZBO system

# 2运行规律的初步分析

对液氮零蒸发系统的工作流程初步分析如图2所示。首先向液氮储罐充注一定量液氮（过程0-1)，稍后封闭杜瓦的进液和排气管路出口(状态2)。与此同时开启脉冲管制冷机，由于制冷机冷端和热管本身及其气态工质降温液化的热容较大，所以制冷机从启动到冷端降至液氮温区需要一定的时间，此间杜瓦系统漏热引起储罐内的液氮温度和压力逐渐升高 (过程2-4)。当制冷机把热管整体降至液氮温度（状态3-4)，热管正常启动工作，热管内氮工质在冷凝器中被冷凝成液体流向蒸发器，并吸热蒸发成气体回流到冷凝器中，如此循环工作将杜瓦的热量传递给制冷机。

在热管启动并正常工作初期，其传递的制冷机冷量大于杜瓦储罐的漏热量，储罐内液氮的温度和压力转而开始下降(状态4)。由于制冷机在输入电功不变的情况下，其制冷量随制冷温度的降低而减小，同时杜瓦漏热量随液氮的温度降低而增加，因此储罐中液氮温度和压力的下降的速率是渐渐减缓的。如果等待足够久的时间，在某一温度下制冷量与漏热量相等，即液氮的温度和压力保持在这一状态下不变，达到长期稳定的零蒸发存储。如图2 中的过程（4）到（6）阶段。

![](images/235521fb2670bf16d076f0b8a39b509dad560ccd99d3114dddf60d4a69fa9dfa.jpg)  
图2零蒸发系统启动运行分析

Fig.2 Startup and running analysis of the ZBO system

当液氮零蒸发系统处于稳态运行过程中，如果改变制冷机的输入电功，其制冷量也随之变化，此时零蒸发系统转而进入非稳态的运行状态。储罐中液氮的温度和压力也随之改变，并逐渐调整到某一新的平衡状态下，以使得杜瓦漏热量与制冷量再次匹配。即杜瓦零蒸发运行状态具有自适应调节功能，当外界条件发生变化后，其通过调节液氮的存储温度和压力，以适应新环境条件并达到新平衡。这就是零蒸发系统的变工况运行规律。如图3所示，在时刻（1）减小制冷机输入电功（或外界漏热增加)，储罐液氮温度逐渐升高，至时刻（2）达到新的平衡并稳定运行；类似的在时刻（3）增加制冷机输入电功（或外界漏热减少)，经历一段时间到（4）点又达到新的平衡状态点。

![](images/a570b1f0e36af403ddf972282895ebbc9ae1dc2296139d20078f663baa4f8d5d.jpg)  
图3零蒸发变工况运行规律   
Fig.3 Variable operating rules of the ZBO system

# 3零蒸发实验研究

将脉冲管制冷机、热管及杜瓦等部件组装成零蒸发系统，在杜瓦储罐上部、中间和下部空间位置以及热管蒸发器、冷凝器等关键位置上安装PT100铂电阻温度传感器，储罐排气管口安装压力传感器和安全阀。按照实验流程，首先对系统抽真空后向储罐充注一定量的液氮工质(约2/3储罐容量)；然后封闭杜瓦储罐的输液和排气口，再启动脉冲管制冷机，观测实验过程中各点温度及储罐压力变化。

实验结果如图4所示，可以看出系统运行状态和变化规律：首先在 $1 0 \ \mathrm { m i n }$ 时开始向杜瓦中充入液氮，位于杜瓦储罐内的3个温度传感器和热管蒸发器上2个温度传感器迅速到达77K附近；随后停止工质充注，储罐上部的温度逐渐升高，说明此处没有液氮仅有蒸发的冷氮气，而中部和下部温度值均稳定在液氮沸点 $7 7 \mathrm { ~ K ~ }$ ，说明液氮工质的充注量约为储罐容积2/3；然后将杜瓦静置30min，以便于其内部达到相对稳定的状态；在60min时开启脉冲管制冷机并封闭杜瓦传输管道进出口，可看到热管冷凝器温度开始逐渐下降，而储罐液氮的温度和压力由于漏热从初始77K和 $0 . 1 \mathrm { M P a }$ 逐渐升高；到170min时冷凝器温度到达液氮温度，此时热管开始启动，冷凝器出口开始有液氮流出，图中可见其出口温度迅速下降到液氮温区，同时冷凝器入口由于气体管回流来较热的氮气（因为管路温度较高，冷气流吸收其热量）而出现升温。

![](images/325b588d090301416ba1566e7b179c0f6f36125df9c2d4eb77c55d0c06461465.jpg)  
图4零蒸发系统实验  
Fig.4 Experimental curve of the ZBO system

为便于观察分析，图5是图4中底部区域的放大情况并包含杜瓦内部压力变化情况。随着热管启动工作并传递冷量，储罐内液氮的温度和压力上升速率减缓，在 $2 0 0 \ \mathrm { m i n }$ 时由峰值（温度约87K、压力 $0 . 3 5 \mathrm { \ : \ : M P a } ,$ ）开始转为下降。随着制冷机和热管的持续工作，液氮的温度和压力逐渐下降并越来越慢；

在 $4 2 0 \ \mathrm { m i n }$ 时液氮的温度和压力逐级趋于平稳，稳定值分别为 $8 0 ~ \mathrm { K }$ 和 $0 . 1 6 ~ \mathrm { M P a }$ ，从而实现了液氮的零蒸发无损存储。此时制冷机的制冷量约2W，比理论计算值偏大，可能是由于未考虑冷指和热管等低温部件的漏热量。

图5零蒸发系统实验（局部放大）  
Fig.5 Experimental curve of the ZBO system (Enlarged)   
图6零蒸发系统变工况运行  
![](images/83f917a493aad380debac073c6334b321c13515b18b929ffe4469df46df7dba8.jpg)  
Fig.6 Dynamic changes of the ZBO system

112 0.5 UpofDewar 108 —MiddleofDewar —Bottom ofDewar 104 0.4 —Outlet ofCondenser 100 ←Condenser K —Inlet of Condenser Prassssssd -Pressure 0.3 92 □ □ □ 88 0.2 T 84 80 0.1 76 72 0.0 180 240 300 360 420 480 540 Time/min

图6为该液氮零蒸发系统的变工况运行特性实验结果。开始过程与前面实验类似，零蒸发系统各部件启动并正常工作，经历 $^ \textrm { \scriptsize 4 h }$ 达到零蒸发稳定状态。此时改变制冷机的输入电功，观察系统的各点温度及压力的变化。在280min时将制冷机输入电功从50W增加到 $5 5 ~ \mathbb { W }$ ，随之冷凝器和液氮等温度都开始下降，并经10分钟左右达到新的稳态，液氮温度和压力从之前平衡态‘ $\langle 8 6 \ \mathrm { ~ K ~ . ~ } \ 0 . 3 \ \mathrm { ~ M P a } \rangle$ 调节到新平衡态（83K、0.24 MPa)。在 360 min、450 min和 $4 9 0 \mathrm { { m i n } }$ 时分别增加制冷机输入功率至60W、65W和 $7 0 \mathrm { ~ W ~ }$ ，零蒸发系统均能够很快（10分钟左右）自动调节并达到新的平衡态。

# 4结论

设计搭建了一台小型液氮的零蒸发系统实验装置，该装置包括高频脉冲管制冷机、液氮杜瓦以及热虹吸管等部件。介绍了该小型零蒸发系统的结构参数，对该系统的整体运行特性进行了理论分析和实验研究，得到了系统的启动过程、运行变化、稳态平衡以及变工况运行等特性，实现了制冷机远距离冷却的液氮零蒸发存储。

研究结果验证了该零蒸发方案的可行性并获得良好的运行效果，热虹吸管实现了最大约2K的传热温差并传递了2W左右的冷量。液氮零蒸发系统能够长期稳定运行并且在变工况下自适应调节达到新平衡态。这些零蒸发系统的运行特性与规律，为将来的实际应用奠定了基础。

# 参考文献

[1] Hastings L J,et al,An overview of NASA efforts on zero boil-off storage of cryogenic propellants [J]. Cryogenics，2001，Volume 41:833-839   
[2] Plachta D, Kittel P， An updated zero boil-off cryogenic propellant storage analysis applied to upper stages or depots in an LEO environment [C]// 38th Joint Propulsion Conference and Exhibit, Indiana，2002: NASA/TM-2003-211691   
[3] Plachta D,Results of an advanced development zero boil-off cryogenic propellant storage test [C]// 40th Joint Propulsion Conference and Exhibit, Florida，2004:NASA/TM—2004-213390   
[4]史俊茹，基于脉管制冷机的液氢无损贮存系统研究[D]， 杭州：浙江大学，2007 SHI Junru，Investigation on zero boil-off system of liquid hydrogen based on Pulse tube cooler[D], Hangzhou:Zhejiang University，2007   
[5］张洋洋，赵雅楠，闫涛，洪国同，冷却 SQUID 的零蒸发 液氮杜瓦装置设计与初步实验[C]//遵义，第11届全国 低温工程大会，2013:90-93 ZHANG Yangyang， ZHAO Ya-nan，YAN Tao，HONG Guotong, Device design and preliminary experiments of zero boil-offliquidnitrogen dewar forSQUID cooling[C]// Zunyi: The 11th cryogenic engineering conference，2013:90-93