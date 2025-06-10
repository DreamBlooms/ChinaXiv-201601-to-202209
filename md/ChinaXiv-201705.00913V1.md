# 端壁错位对端壁泄漏流冷却的影响研究

杨星刘钊刘战胜丰镇平

(西安交通大学能源与动力工程学院叶轮机械研究所；陕西省叶轮机械及动力装备工程实验室，西安710049)

摘要本文采用数值方法针对燃气涡轮端壁因实际运行过程中部件热膨胀所造成的端壁错位进行了研究，详细分析了不同端壁错位形式下端壁上游槽缝泄漏流和槽缝/间隙泄漏流共同作用下的冷却分布规律。结果表明，端壁错位会改变端壁附近的流动结构，进而影响端壁表面泄漏流冷却的分布特性；在不同的端壁错位形式下，通道间隙泄漏流基本不会影响上游槽缝泄漏流的冷却分布；对上游槽缝泄漏流冷却有强化作用的端壁错位形式反而有可能会对端壁下游的间隙泄漏流冷却带来不利影响。

关键词燃气涡轮端壁；泄漏流；端壁错位；气膜冷却；数值分析中图分类号：TK472 文献标识码：A 文章编号:0253-231X(2017)04-0719-07

# Effects of Endwall Misalignment on Endwall Rurge Flow Film Cooling

YANG XingLIU ZhaoLIU Zhang-Sheng FENG Zhen-Ping (InstituteofTurbomachinerySchoolofEnergyandPowerEngeeng,Xi'anJiaotongUniversity;ShaanxiEngiering Laboratory of Turbomachinery and PowerEquipment，Xi'an 710o49,China)

Abstract In this paper,flm cooling performande from upstream slot purge flow with and without mid-passage gap leakage was numericallyimyestigated in detail. The effects of endwall misalignment due to expansion and contraction of turbime component during engine operations were studied. The results show that the endwall misalgnment significantly altered fow structures over the endwall surfaces and thus had obviousSeffects on cooling coverage over the endwall. At various misalignment modes,the gap leakage presented little efects on the purge fow cooling distributions from the upstream slot. The endwal misalignment, which improved the endwall purge flow cooling performance, could bring out a reduction in film cooling effectiveness from the mid-passage gap leakages.

Key wordsgas turbine endwall purge flow; endwall misalignment; film cooling; numerical simulation

# 0引言

燃气涡轮通常是由单支或双支叶片在涡轮盘上装配而成，因此涡轮相邻叶片端壁通道中存在装配间隙。与端壁上游槽缝泄漏流一样，冷却空气在通过端壁通道间隙泄漏进入主流的同时，也可对端壁的一定区域形成冷却。然而，由于通道间隙在叶栅通道中轴向跨度较大，致使其出口压力分布差异非常明显，因此，与槽缝泄漏流冷却相比，通道间隙泄漏流在端壁表面具有与之完全不同的冷却分布规律。此外，端壁表面温度分布非常不均匀，由于热应力的作用，端壁通道间隙会出现明显的高低错位现象。通道间隙错位除了改变端壁附近的流动结构外，还会对泄漏流的出流方式及其冷却规律带来非常明显的影响。

端壁上游泄漏流对端壁具有非常明显的冷却保护效果，因此许多学者针对泄漏流流量[1]、槽缝位置[2]以及射流角[3]等因素对端壁表面泄漏流冷却分布特性的影响开展了研究。然而，目前针对叶栅通道中相邻叶片端壁间隙泄漏流对端壁冷却作用的研究还比较少，并且不够深入。Pigush 和 Simon[4的研究结果表明，端壁表面的换热分布规律受通道间隙泄漏流流量的影响；Roy 等[5]则研究了有上游泄漏流和通道间隙泄漏流时端壁表面的冷却效果，指出在冷却设计中考虑间隙和泄漏流的存在对发动机性能具有重要的意义。此外，Cardwell等l6和Hada等[7]则在有上游槽缝泄漏流、离散气膜孔以及通道间隙泄漏流三者共同作用的端壁上通过实验研究了端壁错位对端壁气膜冷却的影响，结果表明，上游槽缝和通道间隙在某一特定的错位形式下端壁表面的气膜冷却效果得到了提升。

本文在端壁上游和通道间隙泄漏流冷却研究的基础上[8.9]，采用数值方法针对发动机运行过程由于部件热膨胀造成的端壁错位进行详细研究，通过比较端壁的不同错位形式对端壁泄漏流冷却的影响，以期为涡轮端壁的间隙设计和冷却设计提供工程指导。

# 1计算模型

本文研究对象为图1(a）所示的某高性能航空发动机第一级动叶，计算模型中，在动叶端壁上游$- 0 . 1 C _ { \mathrm { a x } }$ 处设置槽缝以模拟上游静叶与下游动叶端壁之间的间隙，槽缝射流角为 $4 5 ^ { \circ }$ ，横截面宽度为4$\mathrm { m m }$ ，长宽比为6.573；同时，在叶栅通道中设置长度为 $2 0 0 . 8 ~ \mathrm { m m }$ 的垂直射流槽缝以模拟相邻叶片端壁通道间隙，通道间隙与轴向夹角为 $- 4 0 ^ { \circ }$ ，间隙宽度为 $2 ~ \mathrm { m m }$ ，深度为 $1 8 ~ \mathrm { m m }$ 。图1(b)、(c)分别给出了端壁上游槽缝和通道间隙的详细几何结构。有关叶栅模型、端壁上游槽缝和通道间隙的详细几何参数见表1。 学书

![](images/9f019a4cdc001d2f7a53c44d8e59d72fdb997bf1d92e436d07878670a30848f2.jpg)  
图1计算模型 Fig.1 Computational model

根据工程经验，在发动机运行过程，以上游槽缝和通道间隙为分界，上游静叶端壁(CS)、下游动叶端壁压力面侧(PS）与吸力面侧(SS）三者之间存在3 种不同类型的错位形式：1)齐平形式 (Flush)，2)堤坝错位形式(Dam)和3)瀑布错位形式(Cascade).端壁齐平形式代表上游静叶端壁、下游动叶端壁压力面侧和吸力面侧间没有发生错位，如图2(a)所示。端壁堤坝错位形式是指上游静叶端壁和下游动叶端壁压力面侧齐平，但低于吸力面侧；在此情况下，端壁附近二次流从压力面侧向吸力面侧流动过程中会由低到高翻越端壁错位台阶，如图2(b)所示。端壁瀑布错位形式是指端壁吸力面侧低于端壁压力面侧或上游静叶端壁；这种情况下，端壁附近的流动会经历从高台阶到低台阶的“瀑布效应"(waterfallorcas-cade effect)，此时又分为如图 $2 ( \mathrm { c } ) \sim$ (e)所示的3种不同的端壁瀑布错位形式。图2(c)中，上游静叶端壁高于下游动叶端壁压力面侧和吸力面侧，而压力面侧与吸力面侧齐平(Cascade_CS)；图2(d)中，下游动叶端壁压力面侧高于吸力面侧和上游静叶端壁，而动叶端壁吸力面侧和上游静叶端壁齐平(Cascade_PS);

表1叶栅模型几何参数  
Table 1 Parameters of cascade geometry   

<html><body><table><tr><td rowspan="5">叶栅几何</td><td>弦长：C/mm</td><td>184.15</td></tr><tr><td>轴向弦长/弦长：Cax/C</td><td>0.704</td></tr><tr><td>节距/弦长：P/C</td><td>0.750</td></tr><tr><td>叶高/弦长：S/C</td><td>2.483</td></tr><tr><td>进口气流角:β1/() 出口气流角：β2/()</td><td>35</td></tr><tr><td rowspan="5">上游槽缝</td><td>位置：Xs/Cax</td><td>-72.5 -0.1</td></tr><tr><td>流向截面宽度：Ws/mm</td><td></td></tr><tr><td></td><td>4</td></tr><tr><td>流向长度/宽度:Ls/W</td><td>6.375</td></tr><tr><td>射流角:α/()</td><td>45</td></tr><tr><td rowspan="5">通道间隙</td><td>长度：Lg/mm</td><td>200.8</td></tr><tr><td>与轴向角度:0/()</td><td>-40</td></tr><tr><td>宽度：Wg/mm</td><td>2</td></tr><tr><td>垂直高度：Hg/mm</td><td>18</td></tr><tr><td>射流角：β/()</td><td>90</td></tr></table></body></html>

![](images/2e44401d5cfef0e9b96c94f589f75c6ca69fc82a42dffa45bbf4e6816bc97354.jpg)  
图2不同形式的端壁错位结构Fig.2 Various endwall misalignment modes

图2(e)中，上游静叶端壁和动叶端壁压力面侧齐平，但高于动叶端壁吸力面侧(Cascade_PSCS)。在本文的研究中，借鉴发动机实际运行特征，在所有的错位形式中，端壁错位高度设为叶片高度的 $1 . 2 \%$ 。为了便于区别叙述，下文中将端壁上游槽缝泄漏流和叶栅通道端壁间隙泄漏流分别简称为槽缝泄漏流和间隙泄漏流。

# 2数值方法

本文数值研究采用ANSYSCFX11.0软件，求解三维定常可压缩雷诺时均方程 (RANS)，对流项采用高精度离散格式，工质按理想空气处理。为了与实验[10]进口边界条件尽可能保持一致，首先进行单独的进口边界条件计算。进口边界条件计算模型采用与叶栅模型等高的矩形通道进行，矩形通道的长度为实验中测得的来流边界层虚拟起点与计算域进口之间的距离。将矩形通道出口获得的速度 $V$ 、湍动能 $k$ 和湍流耗散率 $\varepsilon$ 分布作为叶栅模型计算域的进口边界条件，同时给定主流进口静温，出口静压。算域左右侧上下游为平移周期性边界条件，压面和吸力面为固壁，上游槽缝和通道间隙进给定冷气的质量流量和静温，表2给出了相应的计算边界条件。质量流量比是指冷气的质量流量与叶栅进口主流的质量流量之比。在绝热冷却有效度的计算过程中，所有固壁为绝热无滑移壁面，而在换热系数的计算时，固壁面设为恒定壁温 $3 0 0 \mathrm { ~ K ~ }$ 。

表2计算边界条件  
Table 2 Boundary conditions   

<html><body><table><tr><td>参数</td><td>值</td></tr><tr><td>进口雷诺数Rein</td><td>2.2×106</td></tr><tr><td>出口雷诺数 Reex</td><td>6.0×106</td></tr><tr><td>槽缝流量比MFR</td><td>1.25%</td></tr><tr><td>间隙流量比MFRg</td><td>0%，0.3% htt</td></tr><tr><td>密度比DR</td><td>1.78</td></tr></table></body></html>

选用Standard $k - \varepsilon$ ,RNG $k - \varepsilon$ , Standard $k - \omega$ 和SST $k - \omega$ 等4种常用的湍流模型以及 SST $k$ #$\omega + \gamma - \theta$ 转换模型对该叶片表面的换热进行湍流模型的校核。图3给出了不同湍流模型在 $z / S { = } 0 . 3 7 1$ 叶展处对叶片表面换热分布的预测值与实验测量值[10]的对比结果。从图3中可以看出，带 $\gamma - \theta$ 转挨模型的SST $k - \omega$ 湍流模型对叶片表面的流动传热预测精度最好，能很好地预测叶片压力面和吸力面上的换热系数及其分布趋势，因此本文将采用带 $\gamma - \theta$ 转捩模型的 SST $k - \omega$ 湍流模型进行端壁泄漏流冷却的研究。

在仅存在上游端壁槽缝射流，槽缝泄漏流流量为 $M F R _ { \mathrm { S } } { = } 1 . 2 5 \%$ 时，选用了4套粗细不同的结构化六面体网格进行网格无关性验证。对端壁表面横向平均冷却有效度的计算结果如图4所示。从网格无关性验证结果来看，网格规模大约为 $4 . 2 \times 1 0 ^ { 6 }$ 时，数值计算结果已达到很好的网格无关性。因此，经过网格无关性验证，最终选用的网格壁面网格第一层高度为 $0 . 0 0 5 \mathrm { m m }$ ，壁面网格增长率为1.15，最大 $y +$ 小于1.0，满足湍流模型对壁面附近网格的要求。

![](images/34fcd00ae1267dd30c2445b8982a271b949baa6f352099294954a4db9fba64c0.jpg)  
图3湍流模型验证[11] Fig.3 Turbulence model validation[11]

![](images/11e07fe7742c3eedd1c27882122f82c28a6069407f2e903f1ac276c2f6ace506.jpg)  
图4网格无关性验证Fig.4 Grid independency test

# 3结果与讨论

# 3.1端壁错位对槽缝泄漏流冷却的影响

本文的主要目的是在考虑发动机实际运行过程下如何更好地匹配端壁间隙和设计端壁泄漏流冷却。基于作者之前的研究[8,9]，槽缝泄漏流对端壁的冷却效果要远好于间隙泄漏流，因此在存在通道间隙但无间隙泄漏流出流的情况下，首先比较了不同端壁错位情况下槽缝泄漏流在端壁表面的冷却分布特性。

图5给出了不同端壁错位形式下仅存在 $M F R _ { \mathrm { s } } =$ $1 . 2 5 \%$ 的槽缝泄漏流时端壁表面的冷却分布规律与极限流线分布情况。由端壁表面极限流线分布可知，由于受到端壁错位以及泄漏流和通道间隙的吹吸作用，端壁附近的流动结构发生了非常明显地改变，进而使得泄漏流在端壁表面的冷却分布特性也随之发生了变化。从泄漏流冷却在端壁上的分布来看，与齐平端壁（Flush）相比，在端壁上游进口区域，端壁的堤坝错位（Dam）更有利于槽缝泄漏流的横典(沿叶栅节距方向)扩散，而当上游静叶端壁升高形成瀑布错位（Cascade_CS 和 Cascade_PSCS时，槽缝泄漏流的横向扩散能力将得到会削弱但是当发生压力面侧升高的端壁瀑布错位cade_PS）时，槽缝在端壁吸力面侧出口的压力分布更加均匀，在瀑布效应的影响下，受到从压力面流向吸力面二次流的压制作用，槽缝泄漏流具有更好的附壁性，当地冷却效果更好。此外，在端壁堤坝错位形式下，端壁通道间隙对槽缝泄漏流起到了很好的输运作用。从图5(b）可以看到，泄漏流从通道间隙前缘位置入侵进入通道间隙，在压力较低的喉部区域从端壁吸力面侧流出，进而对端壁喉部及下游区域起到了很好的冷却保护作用，而从之前的研究工作可知[9]，端壁通道间隙对槽缝泄漏流产生如此明显的输运作用只有在槽缝泄漏流具有更大的质量流量时才会发生。

![](images/9bf24e7fd5cace2d90d58444effa6356b00b04fe5ebc581e1320e523de7ab2fc.jpg)

![](images/90c3c33b9b4c60a71b748b7aa88c1a214f786d8bea507c96b3797c3fd7ccd2e6.jpg)  
图5端壁错位对槽缝泄漏流冷却和极限流线分布的影响Fig.5 Effects of endwall misalignment on purge flow coolingandstreamlines on endwall

![](images/3fdece89a0bb5b9068f5a400f63fffbe276ae4ff5aac6ec60ad26f83c8d021ce.jpg)  
图6 端壁错位对槽缝泄漏流横向平均冷却有效度的影响Fig.6 Effects of endwall misalignment on laterally averagedpurge flow cooling effectiveness

为了定量分析端壁错位对泄漏流冷却的影响，图6给出了不同错位形式下槽缝泄漏流冷却有效度横向平均值沿轴向的分布情况。可以看到，由于二次流的限制作用，大部分槽缝泄漏流集中在端壁上游三角区，使得其冷却效果沿轴向下降得非常快。和之前的分析一致，在端壁发生错位时，堤坝错位和压力面侧升高的瀑布错位会强化槽缝泄漏流冷却，尤其是端壁上游区域 $( x / C _ { a x } < 0 . 2 )$ ，而其他错位形式则都会不同程度地削弱槽缝泄漏流对端壁的冷却效果。此外，从该图中还可以明显地看到，在端壁发生堤坝错位时，由于通道间隙对槽缝泄漏流具有明显的输运作用，槽缝泄漏流在端壁的喉部及下游区域可以形成二次冷却效果，使得横向平均冷却有效度大致在 $x / C _ { a x } { = } 0 . 8$ 处有明显的升高。

# 3.2端壁错位对泄漏流冷却的影响

从上一节的分析可以看到，在端壁通道间隙没有泄漏流出流时，主流会不同程度地入侵通道间隙，这种情况的发生在发动机实际条件下不但会带来气动损失，降低热力效率，还会给涡轮盘腔造成热烧蚀故障，因此在实际工程中，通道间隙中也会设计少量的冷却射流。根据工程经验，本文通道间隙泄漏流设为 $M F R _ { \mathrm { g } } { = } 0 . 3 \%$ 。本节将针对上游槽缝和通道间隙同时存在泄漏流时，研究槽缝泄漏流和间隙泄漏流共同作用时端壁错位对端壁表面泄漏流冷却效果的影响。 彩

图7是槽缝泄漏流和间隙泄漏流分别为MFRs=$1 . 2 5 \%$ 和 $M F R _ { \mathrm { g } } { = } 0 . 3 \%$ 时端壁表面的冷却分布和极限流线分布情况。从冷却的分布特性可以看到，在端壁没有发生错位时，间隙泄漏流会明显削弱端壁上游的槽缝泄漏流冷却效果，这与之前的研究结果[9]是一致的，而当端壁发生错位时，间隙泄漏流则对上游槽缝泄漏流冷却的影响非常有限。间隙泄漏流对端壁的冷却区域主要集中在喉部及下游的低压区域。在此区域，端壁表面压力较低，通道间隙将间隙泄漏流和其输运的槽缝泄漏流在此一并射出。然而，比较不同形式错位端壁表面的冷却分布来看，堤坝错位对端壁喉部及下游区域的间隙泄漏流冷却具有十分明显的抑制作用。从图7(b)可以看到,与其它错位形式不同的是，堤项错位使得间隙泄漏流不能很好地从端壁喉部及下游区域射出，由于端壁吸力面侧台阶的阻挡作用，大部分间隙泄漏流对通道间隙压力面侧的出口边缘区进行了冷却。仅就端壁喉部及下游区域来看，在Flush和Cascade_CS端壁下，该区域的冷却效果明显好于其它情况，并且该区域基本上全部得到了泄漏流的冷却保护。

![](images/77851a77aa25bde155090ea9e777d419a60054ffd60e6f121a472129ff92cf48.jpg)

![](images/d0918a63e105f28911f2c90dd531b2de11a5a9ee11985a044bda446047f0a147.jpg)  
图7不同错位形式下端壁表面泄漏流冷却和极限流线分布 Fig.7 Purge flow coolingdistributions and streamlines on endwall at various endwall misalignment modes

槽缝泄漏流和间隙泄漏流共同作用下端壁表面的横向平均冷却有效度沿轴向的分布规律如图8所示。与图6对比分析可知，端壁上游的冷却主要由上游槽缝泄漏流冷却主导，而间隙泄漏流主要影响端壁喉部及下游区域的冷却效果。可以看到，在有间隙泄漏流时，不同端壁错位形式下端壁上游的冷却规律没有发生变化，也基本没有受到间隙泄漏流的影响。从图8中可以明显看到，在端壁的不同错位形式下，上游端壁升高的瀑布错位（Cascade_CS）最有利于间隙泄漏流对端壁喉部及下游吸力面侧的冷却，而有利于上游槽缝泄漏流冷却的堤坝错位 (Dam)则对端壁喉部及下游区域的间隙泄漏流冷却非常不利。

由于通道间隙横跨了从前缘到尾缘的整个叶栅通道，通道间隙内的流场更为复杂，应该予以特别关注。图9和图10分别给出了通道间隙出口平面内的无量纲温度分布和出口处的无量纲速度分布。图中，端壁位置在 $z / S { = } 0$ 处，如虚线所示位置。从两图中均可以看到，在相同的泄漏流条件下，在不同的端壁错位结构中，通道间隙中均会发生主流入侵的情况。一般情况下，主流入侵主要发生在端壁的上游区域，而在 $x / C _ { \mathrm { a x } } > 0 . 6$ 的下游区域，间隙泄漏流则能很好地从通道间隙射出。从入侵的程度来看，在上游静叶端壁及端壁压力面侧错位升高的瀑布错位（Cascade_PSCS）情况下，高温主流在间隙中入侵得较深，倒灌入侵程度也最为严重。从图10中通道间隙出口速度分布来看到，端壁压力侧错位升高(Cascade_PS和Cascade_PSCS)的情况下，间隙出口速度沿间隙分布极其不均匀，这一方面容易造成高温主流的入侵，另一方面有间隙泄漏流出流时，间隙泄漏流的附壁性也会变得较差。此外，从图9中主流的低温区还可以看到，在不同端壁错位形式下，前缘马蹄涡压力面分支和通道涡的发展迁移规律也是不同的，进而使得其卷吸低温泄漏流的程度也不相同。

![](images/4710c53cb8bdf689d37c9cb5ddb3590bc36a506a7ef48963d3fc111888a70dc5.jpg)  
图8端壁泄漏流冷却横向平均值沿轴向分布 Fig.8 Laterally averaged purge flow cooling effectivei along axial direction

综上分析可知，在发动机实际条件下，通道间隙中发生高温燃气入侵一般是难以避免的，但通过适当的间隙设计和合理的端壁结构热管理，可以尽量地降低燃气在间隙中的入侵程度，从而避免高温燃气给通道间隙带来烧蚀故障。

![](images/587193743993870703bb0e2174c04edec91e9d33775cdb268fdd43fa8335a4ac.jpg)

![](images/949bd7446cf66592ac3160738d931c306610e89754bd15fac22d3d734041898e.jpg)  
图9通道间隙平面内的无量纲温度和流场分布 Fig.9 Non-dimensional temperature distributions and flow structures on mid-passage gap exit plane

![](images/fa0104089ee78b65aa9d54046cfa5a4ee55e055a832aa54cc1f268ad01248d0b.jpg)  
10通道间隙出口无量纲速度分布 Fig.10 Non-dimensional velocity distributions along mid-passage gap exit

# 4结论

本文采用数值方法深入研究了发动机运行过程中由于部件热膨胀造成的涡轮端壁错位对端壁泄漏流冷却的影响，在4种不同的端壁错位形式下，通过对比分析槽缝泄漏流和间隙泄漏流在端壁表面的冷却分布特性以及通道间隙中的流动与温度分布规律，可以得到：

1）端壁错位会明显改变端壁附近的流动结构，  
进而使得不同错位形式下，端壁表面的泄漏流冷却  
分布明显不同;2）在无间隙泄漏流时，端壁吸力面侧错位升高  
(Dam）或者压力面侧错位升高（Cascade_PS)都会强  
化槽缝泄漏流冷却效果，而其它错位形式则反之;3）由于间隙泄漏流主要在端壁喉部及下游低  
压区射出，因此在不同错位形式下间隙泄漏流射流

均基本上不会改变端壁上游槽缝泄漏流冷却的分布特性；

4)针对间隙泄漏流冷却而言，上游端壁错位升高（Cascade_CS）对其强化作用最为明显，然而对槽缝泄漏流冷却最为有利的吸力面侧错位升高 (Dam)则对间隙泄漏流冷却最为不利。

# 参考文献

[1]Burd SW,Satterness CJ,Simon TJ.Effects of Slot Bleed Injection over a Contoured End wall on Nozzle Guide Vane CoolingPerformance:PartII-ThermalMeasurements [R]. ASME Paper No.2000-GT-200,2000   
[2]Knost D G,Thole K A.Adiabatic Effectiveness Measurements of Endwall Film-Cooling for a First-Stage Vane [J]. ASME Journal of Turbomachinery,2005,127(2):297-305   
[3] Thrift AA,Thole KA,Hada S.Impact of the CombustorTurbine Interface Slot Orientation on the Durability of a Nozzle Guide Vane Endwall [R].ASME Paper No. GT2012-68096,2012   
[4] Piggush JD,Simon T W.Heat Transfer Measurements inaFirst Stage Nozzle Cascade Having Endwall Contouring,Leakage and Assembly Features [J].ASME Journal of Turbomachinery, 2006,129(4):782-790   
[5] Roy A, Jain S, Ekkad SV,Ng WF,Lohaus A S,Crawford M E.Heat Transfer Performance of a TransoniTurbine Blade Passage in Presence of Leakage Flow Through Upstream Slot and Mateface Gap with Endwall Contouring [R].ASME Paper No.GT2014-26476,2014   
[6]Cardwell N D,Sundaram N,Thole K A.Effects of MidPassage Gap,Endwall Misalignment,and Roughness on Endwall Film-Cooling [J].ASME Journal of Turbomachinery,2005,128(1):62-70   
[7]Hada S,Thole K A.Computational Study of a Midpassage Gap and Upstream Slot on Vane Endwall FilmCooling [J].ASME Journal of Turbomachinery，2010, 133(1):011024   
[8] Yang Xing,Liu Zhao,Liu Zhansheng,Feng Zhenping. Computational Study on Effects ofPurge Flow onEndwall Film Cooling and Blade Suction Side Phantom Cooling [C]//Proceedings of 3rd International Workshop on Heat Transfer Advances for Energy Conservation and Pollution Control, Taipei,IWHT2015-1165,2015   
[9]杨星,刘钊,刘战胜,丰镇平.端壁通道间隙对端壁泄漏流冷 却的影响[J].工程热物理学报，2017,38(1)：44-48 YANGXmg, LIU Zhao, LIU Zhansheng, FENG Zhenping. EHects of Mid-Passage Gap on Endwall Purge Flow Film Cooling[J].Journal of Engineering Thermophysics,2017,   
38(1):44-48   
10] Papa M,Goldstein RJ,Gori F.Numerical Heat Transfer Predictions and Mass/Heat Transfer Measurements in a Linear Turbine Cascade [J].Applied Thermal Engineering，2007,27(4):771-778

![](images/2b07eda2b21752260c920eac9180a9b27af3e1a237da434fe4358bb7e155ea26.jpg)