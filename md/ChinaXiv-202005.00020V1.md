# 帕克太阳探测器热防护系统研究及启示

黄善杰，林隽，金振宇，宋腾飞，许方宇（中国科学院云南天文台，云南昆明650216）

摘要：帕克太阳探测器（Parker Solar Probe，简称PSP）是以现代太阳风和磁重联理论的奠基人一一尤金·纽曼·帕克(Eugene Newman Parker）命名的航天器,将穿过太阳的日冕层，探索航天器从未探测过的区域，对日冕和太阳风的起源和动力学特征进行直接探测，有望破解日冕高温之谜和太阳风速度奇高这两大谜团，其热防护系统遇到的困难和挑战远超目前所有航天器。本文首先介绍了探测太阳的意义和PSP的科学目标，然后简述了PSP轨道和轨道热环境并指出了热防护的难点。分析了PSP热防护系统的结构，然后详细阐述了热防护系统的热盾及迎日涂层、太阳能电池板及冷却系统设计，最后给出了PSP热防护系统对我国抵近太阳探测器热防护系统设计方面的启示。

关键词：帕克太阳探测器；热防护系统；热盾中图分类号：P111 文献识别码：A

# 0引言

太阳是距离地球最近的恒星，主宰着包括地球在内的整个太阳系的环境。人类所有的活动几乎都依赖来自太阳的能量，而且太阳上的任何活动与变化，都在以各种各样的方式影响着人类生活与周边环境的安全。特别是太阳上发生太阳耀斑和日冕物质抛射（coronal massejection，简称CME）等剧烈活动现象时，会对地球周围的空间磁场和等离子体环境（也称为空间天气）产生剧烈影响，导致灾害性空间天气出现。随着科技的发展，现代人类建立了规模越来越庞大的高科技系统，包括供电系统、通讯、互联网、卫星导航系统等，人类的日常生活对这些系统的依赖程度也越来越高。太阳耀斑、日冕物质抛射等太阳活动产生的高能带电粒子对人类现代高科技系统有较大影响，类似"卡灵顿事件”、“1989魁北克事件"等强太阳活动事件会严重影响现代人类生活乃至生存质量。为应对太阳活动对人类的潜在影响，需要对太阳活动规律进行监测研究并提前预警。此外，作为宇宙中唯一一个可以供人类近距离探测的恒星，太阳给我们提供了对于其它恒星或宇宙中类似磁化等离子体环境不可能具备的抵近探测的机会[]。

美国东部时间2018年8月12日3:3lam，帕克太阳探测器在Florida Caraveral肯尼迪航天中心发射升空，将穿过太阳的日冕层，探索太空探测器从未探测过的区域，对日冕和太阳风的起源和动力学特征进行直接探测，有望破解日冕高温之谜及太阳风奇高的加速度这两大谜团，其研制的热防护系统保护了PSP 的仪器设备免受太阳辐射的侵害。

随着欧洲的SolarOrbiter项目和俄罗斯的“内太阳探测”项目等近距离探测太阳项目的执行，人类对太阳的探测将掀起一个新高潮。中国科学院云南天文台也提出并开始推进了中国抵近太阳探测的项目，该项目将研制抵近太阳探测器，并对太阳爆发过程及相应磁场结构进行抵近探测。抵近太阳探测器热防护系统用于保护探测器的仪器设备免受超强太阳辐射加热、高能带电粒子侵袭和宇宙冷黑辐射致冷等的影响，是确保探测器任务成功的关键。研究分析帕克太阳探测器的热防护系统，为我国抵近太阳探测器的热防护设计提供一种可借鉴的技术方案。

# 1PSP轨道及热环境

PSP 在远日点位于金星附近，近日点约9.5倍太阳半径的小倾角椭圆轨道上运行。PSP一共7次利用金星的引力助推来逐渐靠近太阳，第一轨时，探测器近日点为35倍太阳半径，接受到的太阳辐射强度相对较低。最后一轨的近日点为9.5倍太阳半径，远日点0.73AU，轨道与黄道面的夹角为3.4度，周期为 88天[2。一共有 24次机会接近太阳,距离日心小于10 倍太阳半径的近日区域内总共停留约 20 小时[1]。PSP 距日最近时，PSP 垂直于太阳光线的受照面单位面积上的辐射通量约为地球附近的 500倍。PSP轨道热环境主要包括：强烈且不断变化的太阳辐射，太阳风长期持续的冲击侵蚀，不定期遭受日冕物质抛射、耀斑等剧烈太阳活动带来的各种高能带电粒子的轰击破坏。此外，轨道上的探测器背对等效温度约为 3K的宇宙背景，承受宇宙冷黑背景的制冷作用。

# 2 PSP热防护系统

PSP 设有直面太阳辐射冲击的热盾，热盾等效直径230 厘米、厚度11.4厘米，用于抵挡强太阳辐射、日冕物质抛射、耀斑、太阳风等侵袭，产生一个保护科学设备的工作区域。防护罩具有耐高温、耐超强太阳辐射、太阳辐射反射率高、耐空间带电粒子辐射、质量密度小、结构强度大等特点。PSP 热盾尺寸大小有一定余量，能容忍2°余量指向误差，即 PSP 指向太阳中心出现2°倾斜角度时，热盾仍能确保科学设备处于热盾的阴影内[2。除了热盾，PSP热防护系统组件还包括辐射制冷器、桁架结构、多层隔热材料（multi-layerinsulation,简称 MLI）、太阳能电池板及其水冷系统等。桁架为PSP 的“骨架”，对热盾、辐射制冷器、太阳能电池板和设备舱等器件起到连接、固定和支撑作用。辐射制冷器安装在热盾下方的桁架结构表面，与宇宙冷背景进行热辐射交换。辐射制冷器内表面和PSP的科学仪器表面均覆盖有银白色MLI材料，MLI外膜具有很低热发射率和高太阳反射率。太阳能电池板为探测器供应电力，其配备水冷系统用于带走电池板发电时产生的热量。热盾用于抵挡强太阳辐射和空间带电粒子侵袭，产生一个供PSP 科学设备长期工作的环境，其中热盾表面的迎日涂层是面对超强太阳辐射的第一道防线，所述迎日涂层是热防护罩的迎日面直面太阳辐射冲击的表面防护涂层。

# 2.1迎日涂层

PSP 的迎日涂层由白色氧化铝陶瓷涂层与钨金属屏蔽涂层（Barriercoating）组合而成。迎日涂层下面是碳/碳复合材料和碳泡沫构成的热盾基层。钨金属屏蔽涂层设置于热盾基层表面，白色氧化铝陶瓷涂层覆盖在钨金属屏蔽涂层表面。白色氧化铝陶瓷涂层在7年任务期间保持白色，在可见光和近红外波段都有较高的反射率，还具有良好抗辐照损伤特性，承受辐射、电子、质子等带电离子轰击能力较强，且涂层的熔点超过两千摄氏度。PSP 迎日涂层表面的太阳吸收率（ $\cdot a _ { s }$ ）与热发射率（ $\displaystyle \langle \varepsilon _ { 1 \mathsf { R } }$ ）的比值 $a _ { S } / \varepsilon _ { 1 R }$ 约0.6，距日最近时迎日涂层最高温度约为 $1 4 0 0 ^ { \circ } \mathrm { C } ^ { [ 3 ] }$ 。探测任务要求PSP需承受24个轨道热循环，第一轨道迎日涂层温度变化范围为 $7 0 ^ { \circ } \mathrm { C }$ 至 $6 0 0 ^ { \circ } \mathrm { C }$ ，最终轨道为 $1 3 0 ^ { \circ } \mathrm { C }$ 至 $1 4 0 0 ^ { \circ } \mathrm { C }$ 。若无迎日涂层，热盾的碳/碳复合材料近似为一个黑体，距日最近时的热盾表面温度可达 $1 6 0 0 ^ { \circ } \mathrm { C }$ 。

普通氧化铝涂层具有脆性大、韧性差等不足，通常添加二氧化钛/氧化镁、稀土元素/其氧化物、碳纳米管和碳纤维等其它硬质相形成复合粉末材料，克服氧化铝涂层的不足[4]。

二氧化钛的熔点低于氧化铝，掺杂于氧化铝中可均匀化组织,改善涂层结构性能。JiaSK、

ZouY 等人发现氧化铝涂层中添加二氧化钛，能提高涂层的致密度、韧性、耐腐蚀性和导热性，可释放应力、减少裂纹[5]，致密度为实际密度与理论密度的比值，而涂层的致密度与涂层表面光学反射率息息相关3。氧化镁可以增加氧化铝陶瓷中的氧空位，促进扩散，有利于烧结。氧化镁对晶粒细化与致密化作用主要是氧化镁固溶在氧化铝晶格中，当氧化镁含量低于固溶极限时，增加氧化镁可同时促进烧结和抑制晶粒长大；当氧化镁含量超过固溶极限时，氧化镁可能与氧化铝反应形成第二相镁铝尖晶石，其作用主要是抑制晶粒长大，而对致密化存在阻碍作用。程诚、纪箴等人发现：添加适量 $\mathtt { M g 0 }$ 可以降低氧化铝陶瓷的烧结温度，抑制晶粒长大，提高致密度，随着 $\mathtt { M g 0 }$ 添加量从 $0 { \sim } 0 . 2 5 \%$ （质量分数）的逐步增加，氧化铝陶瓷的致密度迅速提高，即从 $9 7 . 1 6 \%$ 提高到 $9 8 . 8 7 \%$ ， $0 . 2 5 \%$ 是 $\mathtt { M g 0 }$ 的最佳添加量；当 $\mathtt { M g 0 }$ 含量过多时，会促使部分晶粒的异常长大，并使氧化铝陶瓷的致密度下降。当 $\mathtt { M g 0 }$ 添加量为 $0 . 5 \%$ 时，材料的致密度有所下降。碳纳米管和碳纤维的强度、刚度高，氧化铝粉末添加碳纤维/碳纳米管，可改善涂层内部组织的结合方式，提高力学性能。涂层组织在碳纤维或者纳米碳管相互牵制作用下，涂层的韧性增加，耐磨性、结合强度提高。稀土氧化物/稀土元素作为硬质相分布在涂层中，可改善涂层的微观结构及其性能。李淑华等人研究发现稀土元素可使氧化铝涂层晶粒细化，形成非晶和微晶的混晶结构，改善了涂层结合强度，从而提高涂层的耐蚀性[7]。此外，Ce02 也可以有效降低氧化铝涂层的孔隙率[8]。

PSP 的氧化铝陶瓷涂层添加有氧化镁掺杂剂，作为晶粒生长抑制剂（GGI)。2006年，PSP技术人员的前期研究工作中发现，氧化铝在 $1 1 8 0 ^ { \circ } \mathrm { C }$ 附近发生相变，随着热处理温度的升高而发生晶粒长大，导致太阳吸收率升高，进而导致热盾温度升高[9。氧化铝中加入氧化镁掺杂剂可以阻止这种生长，并能稳定相变后的光学性质，还可以提高氧化铝陶瓷的致密度。表1 对比了有无氧化镁GGI的样品的光学性质3，两样品采用相同的氧化铝粉末和屏蔽涂层，其中氧化铝陶瓷粉末型号为Metco105SFP，屏蔽涂层为厚度约76.2微米的TAN屏蔽涂层。

表1PSP氧化铝陶瓷表面的光学特性  
Tab.1Optical properties of alumina ceramic surface of Ps   

<html><body><table><tr><td>GGI</td><td>αs(RT)</td><td>εIR(RT)</td><td>αs /εIR(RT)</td><td>αs(T1)</td><td>εIR(T1)</td><td>αs /εIR(T1)</td><td>αs(T2)</td><td>εIR(T2)</td><td>αs /εIR(T2)</td></tr><tr><td>No GGI</td><td>34.59%</td><td>58.09%</td><td>59.5%</td><td>27.42%</td><td>50.8%</td><td>54.0%</td><td>35.23%</td><td>51.48%</td><td>68.4%</td></tr><tr><td>GGI</td><td>38.38%</td><td>60.56%</td><td>63.4%</td><td>26.36%</td><td>49.76%</td><td>53.0%</td><td>25.96%</td><td>45.96%</td><td>56.5%</td></tr></table></body></html>

两种氧化铝陶瓷样品中一个加入质量分数为 $5 \%$ 的 $\mathsf { M g O }$ ，另一个没有。如表1所示，首先对比了两种陶瓷样品在室温环境（RT）下光学特性，添加 $\mathsf { M g O }$ 的 $\alpha s / \varepsilon _ { \mathsf { I R } }$ 比值高于后者。然后两种氧化铝陶瓷样品在千分之一托的真空中经6小时 $1 1 8 0 ^ { \circ } \mathsf { C } ( \mathsf { T } 1 )$ 热处理后,其 $\cos , a _ { S } / \varepsilon _ { 1 R }$ 和 $\varepsilon _ { \mid \mathsf { R } }$ 均相似，但经过千分之一托的真空6小时 $1 4 0 0 ^ { \circ } \mathsf { C }$ （T2）热处理后，无氧化镁GGI的样品的αs增加了近 $8 \%$ ，而含氧化镁样品的αs却保持在其原值的 $1 \%$ 以内。氧化镁GGI确实降低了 $\varepsilon _ { \mid \mathsf { R } }$ 值，PSP热盾最高温度约为 $1 4 0 0 ^ { \circ } \mathsf C$ ，经过 $1 4 0 0 ^ { \circ }$ 热处理的掺杂氧化镁的氧化铝陶瓷样品的 $a _ { S } / \varepsilon _ { 1 R }$ 比值，比没有掺杂的低 $1 7 . 4 \%$ ，进而降低了防护罩的热平衡温度。氧化镁掺杂后，不仅提高涂层的太阳吸收率/自身热发射率比值，还降低涂层在高温下热膨胀系数，使之与下方钨金属涂层的热膨胀系数接近，提高两涂层之间的结合能力，使其能承受较大的热梯度而不裂纹、剥落[3]。

真空高温环境下，氧化铝陶瓷会与热盾的碳基层发生反应，变成灰色。PSP氧化铝涂层和碳基层之间设有厚度比头发丝直径还小的屏蔽涂层。PSP设计中考虑的屏蔽涂层包括难熔金属、氮化物、碳化物或氧化物。Elizabeth A.Congdon等人实测发现[3]，在氧化铝陶瓷涂层与碳基层之间增加一层76.2微米的等离子喷涂TAN 后，迎日涂层的太阳辐射吸收率从约 $60 \%$ ，下降为 $30 \%$ 左右，而热发射率基本不变，保持在 $5 5 \%$ 附近。帕克太阳探测器最终选用钨金属涂层，阻挡氧化铝陶瓷和热盾的碳基层在高温下的相互作用。钨的熔点超过3000 摄氏度，是熔点最高的金属可在高温下长期使用。

此外，PSP研发人员测试了氧化铝陶瓷涂层的纯度和初始粉末颗粒尺寸与其太阳吸收率的关系。无热处理的情况下，不同纯度的氧化铝在相同的喷涂条件下的光谱反射率如图1所示[3]：

![](images/6ffd0f794e2ed08b481231efa95023ea8373577ed1efb5a3708c8ebecbadab8b.jpg)  
图1不同纯度的氧化铝陶瓷的反光率曲线

如图1所示， $9 9 . 8 \%$ 氧化铝陶瓷的光谱反射率高于 $9 9 . 9 5 \%$ 纯度的氧化铝，但其太阳吸收率则低于后者。经 $1 1 8 0 ^ { \circ } \mathrm { ~ C ~ }$ 热处理后，两者在室温环境下的光谱反率变得相差不大，如图2所示[3]：

![](images/f091d31d4553f3cc4d988dc82f962e506b9f6fcdcc342098572b17c80adf56fd.jpg)  
Fig.1Spectral Reflectance of Alumina Ceramics of Different Purity   
图2经 $1 1 8 0 ^ { \circ } \mathrm { C }$ 热处理后，不同纯度的氧化铝陶瓷的反光率曲线

PSP 技术人员还研究了不同初始氧化铝粉末颗粒尺寸下制备的氧化铝陶瓷的光学特性差异。相同屏蔽涂层和热处理时，初始颗粒尺寸为 $1 5 ^ { \sim } 4 5 \mu \mathrm { ~ m ~ }$ 的Metco 105NS 氧化铝粉末和初始颗粒尺寸为 $4 { - } 3 0 \mu \mathrm { ~ m ~ }$ 的Metco105SFP氧化铝粉末，制备的氧化铝陶瓷的光谱反射率如图3所示[4]：

![](images/bce9e43c9d0fc48f2a7efc1bd252f6cd1652973ace6aee9288b7d0b410302c7a.jpg)  
Fig.2Spectral reflectance of alumina ceramics of different purity after heat treatment at $1 1 8 0 ^ { \circ } \mathrm { c }$

其中红色曲线对应用Metco105SFP 所制备的陶瓷涂层，蓝色曲线对应Metco 105NS。小尺寸氧化铝粉末颗粒制备的氧化铝陶瓷的光谱反射率低于大尺寸颗粒，且波长越短，反射率差别越大， $7 \mu \textrm { m }$ 以上的长波红外波段，两者反射率相差不大。因此，小尺寸氧化铝粉末颗粒制备的氧化铝陶瓷的太阳吸收率大于大尺寸颗粒，热发射率则相差不大。

PSP 通过控制涂层的微观结构来调节涂层的光学和粘附性能，孔隙率相关效应的建模表明致密度对于短波光学性质比较重要。一定程度上，涂层的光谱吸收率是涂层致密度的函数。PSP采用氧化镁掺杂剂来控制氧化铝的微观结构，进而调整氧化铝涂层的太阳吸收率与热发射率的比值。PSP迎日涂层的发射率是氧化铝陶瓷本身特性和温度的函数。随着温度的增加，迎日涂层的光谱热发射率朝向太阳光谱辐照移动，导致其太阳吸收率与热发射率的比值向1移动，可通过较低的吸收率来降低迎日涂层的表面温度。

# 2.2 热盾

PSP热盾的迎日面和背日面均为 $\mathrm { c / c }$ 复合材料，迎日涂层镀在迎日面的C/C复合材料的表面，底部的C/C复合材料没有迎日涂层，双C/C层之间为低导热的碳泡沫，PSP 热盾的剖面结构示意图如图4所示[10]：

![](images/1676702eabdb17f6b585c9e9f7dee034fa0b893b44c4d16fd0220d0fcbfc0f80.jpg)  
图3不同粉末尺寸的氧化铝陶的光谱反射率  
Fig.3Spectral Reflectance ofAlumina Ceramics ofDifferent Powder Sizes   
图4PSP热盾结构剖面示意图  
Fig.4A picture showing the structure of the heat shield

$\mathrm { c / c }$ 复合材料耐烧蚀、热稳定性好、密度小、强度大、高断裂韧性、导热能力好等特点，多用于弹头、火箭发动机喷管、刹车盘等高温结构件。 $\mathrm { c / c }$ 复合材料是极少数能在 $3 0 0 0 ^ { \circ } \mathsf { C }$ 下使用的材料[11]，也是目前所知唯一一种到 $2 5 0 0 ^ { \circ } \mathrm { C }$ 强度不降低的材料，最大的特点在于其强度随温度的增加不降反升[12]。该材料是一种轻质材料，具有优异的力学性能，作为热盾“龙骨”，可起到支撑作用。帕克探测器的两块 $\mathrm { c / c }$ 复合材料层都很薄，不到十分之一英寸[13],具有良好的柔韧性，即使两层放在一起的，也足以弯曲。太阳辐照会导致树脂挥发，为了保证防护罩的强度， $\mathrm { c / c }$ 复合材料层不能含有树脂和其它任何等杂质，为纯碳纤维缠绕在一起的碳-碳复合结构。

PSP所用的碳/碳复合材料经 $3 0 0 0 ^ { \circ } \mathrm { C }$ 电烤箱反复4-5次高温烘烤。高温下，乱层碳/碳材料结构发生三维层平面的重排现象，使乱层结构的层间距减小和微晶尺寸增加，碳/碳复合材料由乱层结构碳向石墨晶体结构转化。经高温处理后， $\mathrm { c / c }$ 复合材料的强度和耐高温能力可进一步增强。 $\mathrm { c / c }$ 层之间的碳泡沫作为隔热层，用于隔绝热量，阻挡热量传导给桁架和后端设备。碳本身能传导热量，碳泡沫中绝大部分是空的。除了减少航天器的重量以帮助它进入轨道外，泡沫结构还可以大幅度降低热量传导。碳泡沫具有耐高温、耐腐蚀、高抗热冲击、热学稳定性好、密度小、强度大、易加工、低热膨胀等特点，其导热、导电能力和密度在生产环节可调[14]。该设计在降低热盾整体质量的前提下，保证了热盾的强度，直径2.3米、厚度十多公分的PSP热盾重量只有160磅左右。PSP 热盾的剖面图如图5所示，该结构设计保证热盾的强度，并大幅度降低热盾质量。

![](images/88406fa9acfc9aab42c35f97a296d8c8562e7bc6b21ee3e2a3a1b5a1fa195783.jpg)  
图5PSP 热盾的剖面图

C/C 复合材料层的制作工艺类似于网球拍的环氧树脂，首先进行涂抹，然后逐渐固化，最终成强度较高的固态层，如图6所示。

![](images/b8de3a6810e2ea3cb90000e5886f3fc915c265e67f42d19e9aa00e07526ce91e.jpg)  
Fig.5sectional view of Heat Shield of PSP   
图6两张PSP热盾的C/C复合材料层的涂抹过程的图片

# 2.3辐射制冷器

由于不直面太阳，PSP 辐射制冷器工作环境与普通航天器相似，PSP 由多块辐射制冷板拼接而成，外表面涂有高热发射率涂层，内表面贴银白色ML材料，如图7所示：

![](images/b1f0d95a2bfec7f5ab62d96a88cfee394eeb0c2c93f1c7d3edd8873f4a451f4c.jpg)  
Fig.6Two pictures of the smearing process of the C/C composite layer of thermal shield   
图7PSP 的辐射制冷板、辐射制冷器  
Fig.7PSP's Radiation Refrigeration Plates and Radiation Refrigeration Device

# 2.4太阳能电池板及冷却系统

PSP 采用了一种能减轻紫外退化的太阳能电池板供电，其两个电池板总面积约1.55 平方米，每个电池板有主、副电池板两部分，副电池板位于末端，两者由不同尺寸的电池片单元组成。当处于最终轨道近日点时，PSP 附近的太阳辐照度高达 $7 0 \mathsf { w } / \mathsf { c m } 2$ ，是以往任何航天器的50倍以上[2]，如图8所示：

![](images/9418bc4dc41ae362fe445e21db6cebd9b5b74158e6924d3635273ba8a04a72bc.jpg)  
图8PSP 太阳能电池板

PSP 距日9.5倍太阳半径时太阳不能看作点源，其阴影区域分为本影区和半影区。本影区是完全黑暗的，太阳光线完全被热盾阻挡，而没有任何光线到达。半影区内只有部分太阳是可见的，如图9所示[2]：

![](images/bfabd08d83fccdbb25c5166940e253d373955fb32f105edfc1e8f58281ba869f.jpg)  
Fig.8A picture of solar panel of PSP   
图9距日9.5倍太阳半径时热盾的本影区和半影区

Fig.9Apicture showing Theumbra and penumbraof heat shield atadistance fromthesun is 9.5 times the solarradius

与光线垂直的平面，半影区内的太阳辐照强度从本影区边界线上的0个太阳，到半影区外边界线的 $100 \%$ 太阳，此时受照面单位面积上的太阳辐射通量约为地球附近的512倍。虽然处于半影区的太阳能电池板表面的太阳辐照强度不均匀，但电池板内平行于迎日面的电池片线列上有比较均匀的太阳辐照度。为了最小化由局部热流驱动的太阳阵列温度和温度梯度，电池板被设计成在距日最近的地方只能看到 $2 5 \%$ 的太阳。

PSP 还控制电池板与入射太阳光线成一定夹角，以进一步减少电池板的发热量。当入射光线垂直照射到电池板表面时，距日最近时电池板单位面积上的太阳辐射通量是512倍太阳常数，电池板表面法线与入射光线夹角越大，距日最近时的电池板的太阳辐照度越小。PSP太阳能电池板闭环控制电池板表面法线与热盾法线的倾斜夹角，以改变暴露在太阳辐射下的电池板面积。距日较近时，太阳阵列向内倾斜，以减少暴露的电池板面积，只剩余足够的电池板面积吸收太阳能以供电。距日较远时，太阳能电池板完全打开，以使大面积电池板暴露在太阳辐照下[2]。

距日最近时，PSP 电池板每产生1瓦电，会产生约13瓦的热量。PSP最大耗电功率约462瓦特，最大需要冷却约6000 瓦特的热量。太阳能电池板工作温度不能超过 $1 5 0 ^ { \circ } \mathrm { C }$ ，在闭环控制倾斜角基础上，PSP 仍配备了冷却系统进一步降低电池板温度。PSP 技术人员对比研究了热管冷却和单相泵循环液冷两种冷却系统。由于单向泵循环液冷系统的总质量约为$5 5 ~ { \mathsf { k g } }$ ，而热管冷却系统的总质量为 $1 1 5 \mathrm { k g }$ ，最终选择了前者。

PSP 的单向泵循环液冷系统如图10 所示[2],泵机组把冷却水泵入太阳能电池板的水冷通道，然后流经辐射制冷板重新回到泵机组，形成一个闭环水冷系统。把两个太阳能电池板的热量传递给辐射制冷板。每个太阳能电池板的冷却流量为 $3 L / \min$ ，总流量6L/min。两个电池板液冷管路的大小和功能相同，使用3/8英寸直径的连接管，壁厚0.028英寸。辐射散热器所用管子直径为0.25英寸，壁厚为0.028英寸。

![](images/6773b83f2d45ddea536b909a42068b4310e35d37cceb6f8052758c58959affe4.jpg)  
图10PSP太阳能电池板的液冷系统的原理图  
Fig.10Schematic diagram of the liquid cooling system of the solar panel of PSF

零重力、密闭循环液冷系统需要体积补偿装置，即图中的蓄水器。蓄水器有金属板焊接而成，总容量大约320立方英尺，用于克服温度变化引起的密度变化和系统漏水问题。为了防止泵进口出现空穴，蓄水器必须保证系统压力比最高流体温度 ${ 1 6 0 } ^ { \circ }$ C 时的水蒸气压高出15psi。蓄水器的系统最大预期工作压力(MEOP）为 $3 2 5 \mathrm { p s i }$ ，质量为4镑，尺寸直径5英尺，高度11英尺。PSP太阳能电池板单向泵循环液冷系统整体布局如图11所示：

![](images/52c2ef87b5fda201435f37d3b8178d1f6a5e5948f3034a870576035355061482.jpg)  
图11PSP太阳能电池板液冷系统的布局图  
Fig.11A picture showing the Layout of solar panel liquid cooling system of PSP

如图11所示[2]，循环液冷系统的管路采用挠性软管，整个系统质量为 $5 4 . 7 \mathsf { k g }$ ，离心泵最大输入功率不超过43 瓦特。所用离心泵为美国汉胜公司(Hamilton Sundstrand Corporation)的经典之作，多用于各种长寿命飞行应用。特定转速500、流体温度为 $7 0 ^ { \circ } \mathrm { C }$ 时，该泵的效率约为 $40 \%$ 。该泵具有流速、流量控制能力，从而降低PSP非峰值温度运行时的功耗。随着水的运行温度的升高，泵的输入功率减少。当水温为 ${ 1 0 } ^ { \circ }$ C，容积流量为 $6 L / \min$ 时，泵的最大输入功率为43瓦特。水温较高时，泵的输入功率可小于40 瓦特。

PSP 电池片底部焊接有电绝缘且导热良好的陶瓷传热体，陶瓷体通过导热粘合剂连接到背板上。热量通过陶瓷传热体从电池片转移到背板上，然后传给背板内微通道的冷却水。电池板内有两个微通道，为主、副电池板微通道。PSP用离心泵驱动冷却水循环流动，冷却水吸收电池板热量后流经辐射制冷器，把热量辐射到宇宙空间。单相泵循环液冷系统是PSP的“心脏和循环系统”，采用封闭式设计，使用加压去离子水作冷却剂，去离子水无可污染或损害系统的矿物质，总量大约2.53升，沸点超过 $\mathrm { 1 2 5 ^ { \circ } C }$ 。发射后，帕克探测器将经过一次日食，日食时，水冷系统将变得非常冷，辐射器温度可降到 $- 1 5 0 ^ { \circ } \mathrm { C }$ 。为了保证水冷系统存活，发射时水冷系统管路必须是干燥、无充水的，去离子水存储在板载存储罐中，以防止结冰。为保证系统不冻结，日食过后需用电池板对水冷系统进行加热。一旦管路及附件被加热到 $2 0 ^ { \circ } \mathrm { C }$ ，充水阀门打开，当水箱一半的空间装满水时，探测器便可安全运转。水冷系统必须维持最低 $1 0 ^ { \circ } \mathrm { C }$ 以免结冰。为满足7年任务期和3年地面期，水箱、管路和接头等主要浸润材料采用CP级钛合金、 $3 1 6 \mathrm { ~ L ~ }$ 型不锈钢和Inconel合金，降低系统被腐蚀的可能性，保证长期可靠运行。

# 3、启示

PSP 是目前人类研制的第一个飞入太阳日冕层的航天器，其热防护系统设计在热防护能力、体积、质量方面做了很好优化平衡，具有很强的代表性。通过研究PSP热防护系统，有助于更好的探索适合我国抵近太阳探测器热防护方法。本文认为，在以下几个方面对我国抵近太阳探测项目的热防护研究工作具有启示作用：

1)PSP 热盾通过表面与宇宙冷黑的辐射热交换散热，热盾迎日涂层的太阳吸收率 $( { \pmb { \alpha } } _ { s } )$ 、热发射率（ $( \varepsilon _ { 1 \mathsf { R } } )$ 的比值 $a _ { s } / \varepsilon _ { 1 R }$ 是热盾平衡温度的主导因素，比值越低，热盾的平衡温度越低，进而降低热盾基层的设计压力。热辐射本领最大值相对应的波长附近的光谱辐射率越高，其辐射散热效果越好。虽然 PSP采用了调节涂层微观结构来提高涂层的太阳反射率和热发射率，但PSP 迎日涂层在热辐射本领最大值相对应的波长附近的光谱辐射率没有特别设计，导致PSP迎日涂层的 $\alpha _ { s } / \varepsilon _ { 1 R }$ 比值偏高，辐射散热能力较弱，距日最近时迎日涂层温度高达1400 摄氏度。对于处于距日心5倍太阳半径区域的抵近探测器来说，其热平衡温度远超氧化铝陶瓷的熔点。此外，氧化铝陶瓷涂层的硬度和模量高，导致高温断裂韧性低、损伤容限低，容易产生裂纹、剥落；目前 PSP 迎日涂层无法满足我国抵近太阳探测器的要求，可以从降低迎日面 $a _ { s } / \varepsilon _ { 1 R }$ 比值、提高抗高温能力和掺杂提高氧化铝陶瓷涂层韧性三方面出发，探索适合抵近太阳探测器的迎日涂层。

2）抵近太阳探测器轨道与太阳的距离是整个热防护系统设计的根基，距日心10倍太阳半径和 5倍太阳半径差异巨大的辐射通量密度对热盾设计与冷却方式以及太阳能电池板的冷却方式影响巨大。对于我国抵近太阳探测器来说，除了寻找 $a _ { s } / \varepsilon _ { 1 R }$ 比值更低和更抗高温的迎日涂层优化设计，还应结合具体轨道设计，寻找进一步降低热盾和太阳能电池板等迎日面温度的新方法，包括提高热盾传递热量给辐射制冷器，增加太阳能电池板表面的太阳辐射反射率，进而减少其热控压力等，探求适合我国抵近太阳探测项目的新型热控设计。

3）设备总质量决定了能否用现有火箭发射太阳探测器到设计绕日轨道，也是项目可行性的关键。为保证满足热防护要求的前提下，PSP技术人员在减轻热防护系统质量方面做了巨大的努力。从160磅左右的超轻质热盾，到放弃总质量为 $1 1 5 \mathrm { k g }$ 热管冷却系统，选用55公斤的单向泵循环液冷系统等降低质量设计，降低了整个PSP的质量，大幅度提高了整个项目的可行性。我国目前大推力火箭能力方面还不如美国，需要在PSP热防护系统的基础上，有效借鉴近几年出现的新型材料和新型热控技术，进一步探索降低热防护系统质量的方法。

# 参考文献：

[1]林隽，汪敏，田晖等．太阳爆发的抵近探测[J].中国科学：物理学力学 天文学（LINJin,WANG Min,TIAN Hui,etal.In situ measurements of the solar eruption［J].SCIENTIA SINICA Physica,Mechanica & Astronomica）,2019,49(05):70-89.   
[2]LockwoodM,ErcolJ,Cho WL,etal.AnActive CoolingSystemfor the Solar ProbePowerSystem[C//40th Inteational Conference on Environmental Systems.2010.   
[3]CongdonE,MehokeD,BuchtaM,etal.DevelopmentofHigh-TemperatureOpticalCoating forThermal ManagementoSolar Probe Plus[C]//Aiaa/asme Joint Thermophysics &Heat Transfer Conference.2013.   
[4]路广明,刘宏伟,乌日开西·艾依提.等离子喷涂氧化铝复合涂层的研究进展［J].热加工工艺(LUGuangming,LIU Hongwei, Wurikaixi Aiyiti.research Progressof Alumina Composite Coatings Prepared by Plasma Spraying[J]．.Hot Working   
Technology),2018,47(6):5-8.   
[5]JiaSK，ZouY，XuJYetal.EffectofTiO2contentonpropertiesofAl2O3 thermalbariercoatingsbyplasmaspraying[J]. Transactions of Nonferrous Metals Society of China.2015，25(1)：175-183.   
[6]程诚，纪箴，贾成厂等.MgO和烧结温度对 Al203 陶瓷致密化过程的影响[J].粉末冶金技术(CHENGCheng,JI Zhen,JIACheng Cheng,et al. EfectofMgOaditionandsintering temperatures ondensificationprocessofAl2O3ceramics[J].PowderMetallurgy Technology),2015,33.(4):275-280.   
[7]李淑华，邵德春．稀土与激光表面重熔对喷涂层耐蚀性的影响[J]．材料科学与工艺(LIShuhua,SHAO Dechen.The Efect of RareEarths andlaserremeltingon thecorosionresistanceofcoatings[J]Materials ScienceandTechnology)，1994(2)：91-96. [8]HeL，TanY，WangXetal．Microstructure and wear properties of Al2O3-CeO2/Ni-base aloy composite coatings on   
aluminum alloys by plasma spray[J]．Applied Surface Science，2014，314:760-767.   
[9]SolarProbe ThermalProtection SystemRiskMitigation Study,preparedbyTheJohns Hopkins UniversityApliedPhysics Laboratory,Laurel,MD,November 30,2006.   
[10] HeislerE,AbelE,CongdonE,etal.Fullscale thermalsimulatordevelopmentforthesolarprobeplusthermalprotection system[C]// Aerospace Conference.IEEE,2017. [11]杨鑫 黄启忠 苏哲安 常新.C/C复合材料的高温抗氧化防护研究进展[J]．宇航材料工艺(YANG Xin;HUANGQizhong;SU Zhean;CHANG Xin.Reviewof Recent Progresson Oxidation Protection forC/C Composites at High Temperature[J]. Aerospace Materials& Technology),2014,44(1):1-15.   
[12]付前刚，李贺军，沈学涛，李克智.国内C/C 复合材料基体改性研究进展[J].中国材料进展(FUQiangang，LIHejun，SHEN Xuetao，LIKezhiDomesticResearchProcess ofMatrixModificationforCarbon/CarbonComposites[J].MaterialsChia),1 (30):6-12   
[13] https://hub.jhu.edu/2O18/o8/06/parker-solar-probe-heat-shield-explaied/.   
[14]王新营.高性能碳泡沫的制备与研究[D].东南大学博士毕业论文(Preparation and study on novel carbon foam[D].Ph.D.thesis, Southeast University)，2006.

# Research and enlightenment of heat protection system of Parker Solar Probe

HUANG Shan-jie, LIN Jun,JIN Zhen-Yu, SONG Teng-Fei,XU Fang-Yu (Yunnan Observatories，Chinese Academy of Science，Kunming 650216)

Abstract:The Parker Solar Probe (PSP), named after Eugene Newman Parker, the founder of the modern theory of solar wind and magnetic reconnection, will cross the sun's coronal layer to explore areas that the spacecraft has never detected. Parker Sun Detector directly probes the origin and dynamics of the corona and solar wind. It is expected to solve the mystery of high temperatures in the corona and the high speed of the solar wind.The Parker Solar Probe's thermal protection system has encountered far more diffculties and challenges than any spacecraft currently.This paper first introduces the significance of detecting the sun and the scientific goal of PSP,then briefly describes the thermal environment of PSP orbitals and points out the difficulties of thermal protection. The structure of PSP thermal protection system is analyzed,and then the design of thermal shield, surface coating,solar panel and cooling system of thermal protection system is described in detail. At last, the paper gives the enlightenment of PSP thermal protection system to the design of thermal protection system of near solar detector in China.

Key words: Parker Solar Probe; Thermal protection system; Heat shield