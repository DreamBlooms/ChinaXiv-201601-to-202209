# 串列式叶栅扩压器非定常流动研究

周莉，李妍，王占学(西北工业大学 动力与能源学院，西安 710072)

摘要：采用数值模拟方法，对串列式叶栅扩压器中的非定常流动进行了研究。结果表明，带串列式叶栅扩压器的离心压气机内部流动是以强非定常的三维黏性主流和缝隙流动为主要特征，串列式叶栅扩压器内部流动存在明显的非定常性，压力脉动的传播在前排叶栅通道内衰减很快。扩压器前排叶片通道内压力脉动的主频为叶轮叶片通过频率。后排叶片前缘附近压力脉动的主频变为0.5倍叶频。串列式叶栅扩压器进口的压力脉动主要受到叶轮的激励作用；串列叶栅间隙处，随主流输运而来的叶轮尾迹与缝隙流、前排叶片尾迹相互干扰与叠加，成为后排叶片前缘压力脉动新的激励。相比于近叶根、叶尖处，前排叶片前缘中间叶高处的压力脉动受到叶轮主流和分流叶片尾迹的激励作用更强烈。

关键词：串列式叶栅扩压器；非定常流动；压力脉动；主频中图分类号：V211.15 文献标识码：A

# Numerical Investigation of Unsteady Flow in Tandem Cascades Diffuser

ZHOULi LI Yan WANG Zhan-Xue (School of Power and Energy, Northwestern Polytechnical University, Xi'an 710o72,China)

Abstract: Numerical simulation was employed to investigate the unsteady flow field of tandem cascades difuser. Results show that inner flow of the centrifugal compressor with tandem cascades diffuser is featured with strongly unsteady，three-dimensional viscous main flow and gap flow.The inner flow in tandem cascades diffser is significantly unsteady.The propagation of the pressre fluctuation attnuates notably in the passage offront cascade. The dominant frequencyof fluctuation pressure in front cascade of diffuser is the blade passing frequency(BPF) of impeller, while it changes to a half BPF of impeler near the leading edge of rear cascade.Near the leading edge of the front cascade,the pressure fluctuation is excited bythe impeller; in the gapoftandem cascades,it is dominated by a new excitation which is created by the interaction and superposition of the gap flow,the wake of front cascade andtheimpeller wake transported in the mainstream.Near the leading edge offront cascade,compared with the root or the tip,the pressure fluctuation near the mid-span is more strongly excited by the wake of both main blades and splitter blades of impeller.

Key words: tandem cascades diffuser; unsteady flow; pressure fluctuation; dominant frequency

# 0引言

高负荷压气机是现代叶轮机械的发展方向，随着离心压气机向高负荷、高效率和宽工况范围方向的发展，其关键部件一一扩压器的设计既要兼顾气流折转角的增大，又要考虑不同工况下流动损失的有效控制。然而传统的单列叶栅扩压器在大冲角下的高损失以及大的气流转角下导致的气流严重分离和喘振等都使得传统扩压器已经不能满足发展的需求，寻找一种性能更加优异的扩压器成为必然[1]。

串列叶栅技术被认为是一种能够提高压气机负荷的有效技术手段。魏巍[2]分析串列静子的迎角、落后角、载荷分配后，发现前排叶片的落后角和后排叶片的气流迎角对静子来流的迎角变化并不敏感，几乎全部来流迎角变化所引起的负荷变化由前排叶片承担。Hergt和Sillerl3对跨声速压气机的串列设计进行了研究，提出了3个设计推荐值：前排叶片弦长要比后排叶片短 $30 \%$ 以达到最佳载荷平衡，并且串列叶栅的轴向重叠度只能在轴向弦长的 $0 \sim 5 \%$ 之间，叶片间的周向间距范围要在周向的 $1 5 \% { \sim } 3 0 \%$ 之间。Payyappalli 和 Shine[4]认为叶栅节距系数增大的同时，前排叶片的气动载荷相比于后排叶片来说越来越大。在离心压气机方面，Douglas[5的研究表明同传统单列叶片相比，串列式离心叶轮的应用可以提高压气机的压比和喘振裕度。齐翠霞等认为串列式叶栅扩压器跟单列叶栅叶片扩压器相比具有较宽的可运行工况和较高的效率，并且在串列式叶栅扩压器中当后排叶片压力面前缘接近前排叶片吸力面尾缘位置时，压气机整级损失较小。谢蓉7对离心压气机串列叶栅扩压器性能开展了研究，结果表明叶型的好坏对串列叶栅扩压器的性能影响较大。这些研究表明串列叶栅扩压器与传统单排叶栅扩压器相比，具有气流折转角大、可有效的阻止边界层过早分离和流动损失小的特点，越来越引起人们的兴趣。

此外，研究表明离心压气机内部流动具有显著的非定常性，其会对离心压气机的效率、运行工况范围、稳定性等的气动性能产生较大的影响[8-9]。在带有串列式叶栅扩压器的离心压气机内，由于串列式前后排叶片之间间隙相对较小，在前后排叶片之间间隙处，非定常效应不仅强烈而且复杂，其流动规律、干扰机理以及对机器整体性能及结构的影响均可能不同于单列动一静叶排为干扰源的非定常流动。目前，国内外研究人员针对串列叶栅的几何参数、气动参数做了大量研究，但是针对串列叶栅非定常性的研究却缺乏关注。

本文采用数值模拟方法，研究了设计流量工况下串列式叶栅扩压器通道中非定常流动特性，探索了串列式叶栅扩压器内部的非定常流动机理。

# 1数值方法

在进行串列式叶栅扩压器内部的非定常流动数值模拟时，采用NUMECA软件包，求解圆柱坐标系下的三维非定常雷诺时均Navier-Stokes方程。湍流模型为Spalart-Allmaras一方程模型，空间离散采用中心差分格式。采用双时间步时间推进方法进行非定常流场的求解。

为了模拟串列式叶栅扩压器真实进口条件，以带串列式叶栅扩压器的离心压气机级为研究对象，计算区域包括离心叶轮和串列式叶栅扩压器。根据区域缩放的原则，计算区域选择为1个叶轮通道和2个串列式叶栅扩压器通道。叶轮网格节点数为47.1万，串列式叶栅扩压器网格节点数约为119万。

在叶轮进口边界给定进口总压、总温，进气方向为轴向进气。在串列式叶栅扩压器出口边界给定静压。周期性边界条件施加在周向边界。固体壁面设置为无滑移以及绝热壁面边界条件。在定常计算中，动/静叶界面采用混合平面法，非定常计算中动静叶界面采用滑移网格法进行数据传递，以定常计算的收敛结果作为非定常计算的初场。把一个叶轮叶片通过两个串列式叶栅扩压器通道用的时间作为一个周期。在每个计算周期设定90个物理时间步，在每个物理时间步下进行50次虚拟时间下的迭代。

# 2计算结果及分析

为了研究串列式叶栅离心扩压器中的非定常流动特性，本文对设计流量工况下的扩压器进行了数值研究，对其流场与压力脉动进行了分析。

# 2.1非定常流动的流场分析

图 $1 \sim$ 图3分别给出了 $10 \%$ 、 $50 \%$ 、 $90 \%$ 叶高处熵增、绝对马赫数和绝对总压在某一时刻的分布云图。从图中可以看出， $50 \%$ 叶高处，串列式叶栅扩压器前排叶片从距离前缘约1/2处开始发生气流分离。接下来分离气流面积并没有扩大，在前排叶片尾缘附近受到了串列叶栅缝隙流的影响而被吹除了。后排叶片尾缘附近的旋涡区域非常小，这则说明气流的分离受到了较好的控制。值得注意的是，非定常流动流场尤其是在尾迹区域的流场参数呈现出了规律性的高低、高低错落有致的分布，这就是非定常计算反映出来的叶轮尾迹的输运。相比于 $50 \%$ 叶高截面， $10 \%$ 叶高处叶片周围的流线基本都与叶片贴合，虽然叶轮尾迹宽度最窄，但尾迹输运的现象衰退的最慢。 $90 \%$ 叶高处流场受到由轮盖附近气流由轴向转径向时发生的气流分离、端壁附面层以及叶顶间隙共同作用的叶轮出口流场的影响，混乱程度明显变大。从前排叶片前缘处气流就开始发生分离并产生了逆时针的旋涡；前排叶片尾缘处的分离气流受到该叶高截面强烈的叶栅缝隙流影响产生了顺时针的旋涡。

![](images/9154b476343f0eda16823152c8ac1285b3c749746e3c514f491aead0ea938b71.jpg)

![](images/f6fe19a98eb477765ec035d6f2cb9149afcec43ba040f975c9e0481e7eb26a5c.jpg)  
Fig.1Instantaneous entropy and streamline distribution at different spans Absolute Mach Number   
图2不同叶高下的绝对马赫数等值线分布图

![](images/bbe133048e03cdbc25916a546ddc4793dec887b9310debad1f1c64e894b93a06.jpg)  
图1不同叶高下的熵增和流线分布图  
Fig.2Instantaneous absolute Mach number contours at different spans   
图3不同叶高下的绝对总压等值线分布图

Fig.3Instantaneous absolute total pressure contours at different spans

图4给出了 $50 \%$ 叶高不同时刻的熵增分布图。由图可知，扩压器入口处的熵增总体较小，但是由于气流分离的影响，到了前排叶片吸力面的尾缘附近熵增明显变大，可见前排叶片通道的气流损失较大。受到离心叶轮尾迹的影响，不同时刻下，两排叶栅的前缘及尾缘附近的熵增都会呈现周期性变化。当尾迹扫过时，此处的熵增变大，吸力面的气流分离区也随之增大。由于受到串列叶栅缝隙流的影响，作用于前排叶片压力面的尾迹流很大一部分作用到了后排叶片前缘的吸力面。

![](images/c371299dcb732006c6e4aeb4c6312a004b8658610e851e322af43b857c1c0202.jpg)  
图4 $50 \%$ 叶高不同时刻下的熵增等值线分布图Fig.4Instantaneous entropy contours at $50 \%$ span

# 2.2非定常流动的压力脉动分析

图5给出了在串列叶栅前、后排叶片吸力面和压力面的前缘和尾缘附近的 $50 \%$ 叶高处布置的压力监测点(MonitorPoint)位置示意图，并且在对应位置的 $10 \%$ 、 $50 \%$ 和 $90 \%$ 叶高处分别布置了压力监测点。下文中“MP50.5”代表的是 $50 \%$ 叶高处压力面上的MP5监测点。

![](images/e6291725929b7683a080ad5226dd5b92fd38f4400731949c2689262a39eba987.jpg)  
图5监测点位置示意图Fig.5Sketch of monitor points

图6给出了各监控点静压的压力系数在3个周期内随时间步的变化曲线。由图可知，每个周期内，在串列式叶栅扩压器前排叶片前缘附近的压力系数经历了2次明显的周期性变化，这是由于在1个周期内有2个叶轮叶片尾迹通过，每当叶轮主流叶片或分流叶片经过串列式叶栅扩压器通道时，就会产生旋转叶片与静止叶片间的动静干扰。对比每幅图中不同监测点处的压力曲线图可以发现，压力脉动的传播在前排叶栅通道内迅速衰减，但在后排叶栅通道内，其幅值的变化并不显著。值得注意的是，压力脉动在后排叶片前缘附近的变化，相比较前排叶片而言，周期性的变化规律减弱，这也体现出了在串列叶栅缝隙的作用下，叶片尾迹流动和缝隙流动的相互作用，使得压力脉动复杂化。

![](images/17965cd9410dca58b77746e5f9b16a480eec6ca2ce0466ffc689c49c5763eddc.jpg)

图7给出的是 $50 \%$ 叶高处，压力面上不同监测点的压力脉动通过快速傅里叶变换得到的频谱特性图。带有分流叶片的离心叶轮相对于扩压器叶片的叶片通过频率为 $2 6 . 4 \mathrm { k H z }$ 。由图可知，在 $50 \%$ 叶高处，前排叶片前缘附近压力脉动的主频为叶轮的叶片通过频率，说明此处的压力脉动所受离心叶轮的主流和分流叶片的激励作用强度相当。前排叶片尾缘附近压力脉动主频的幅值比前排叶片前缘处的小了一个数量级，可见其能量传播在前排叶栅通道内衰减的程度很大。后排叶片前缘附近压力脉动的主频逐渐变为0.5倍叶片通过频率，相应幅值略大于前排叶片尾缘处的主频幅值。结合图4的熵增分布图及图6中的压力脉动分布图可知，在两排叶片的间隙处，随着主流输运而来的叶轮尾迹与缝隙流、前排叶片尾迹相互干扰与叠加，撞击到后排叶片的前缘，成为此处压力脉动新的激励，此后非定常流动的主导频率为0.5倍叶片通过频率。后排叶片尾缘附近压力脉动的主频同样为0.5倍叶频，对应幅值略大于后排叶片前缘处的最大幅值，说明在后排叶栅通道内的主流中，压力脉动的发展所受串列叶片缝隙以及主流区能量掺混的影响越来越显著。

![](images/7dddc58068d6d3e4ef948038cdcc5266362b87267ba6c33a905956ce6466c56a.jpg)  
图6 $50 \%$ 叶高处的各监测点压力系数波动图 Fig.6Pressure coefficient fluctuation at different monitor points of $50 \%$ span   
图7 $50 \%$ 叶高处压力面各点压力脉动的频谱特性图  
Fig.7Frequency spectrum characteristic at $50 \%$ span

图8给出了在前排叶片前缘、后排叶片前缘和尾缘附近不同叶高处压力脉动的频谱特性分布图。由图 8(a)可知，在前排叶片前缘附近， $10 \%$ 和 $50 \%$ 叶高处压力脉动的主频皆为叶轮叶片通过频率，次主频皆为0.5倍叶片通过频率； $90 \%$ 叶高处压力脉动的主频为0.5 倍叶频，次主频为叶频。并且 $10 \%$ 和 $90 \%$ 叶高处的叶片通过频率对应的能量谱密度幅值小于 $50 \%$ 叶高处，0.5倍叶频随着叶高位置的上升幅值增大。这说明相比于近叶根和近叶尖处，中间叶高处的压力脉动受到叶轮主流和分流叶片尾迹的激励作用更为强烈；但相比于中间叶高与近叶根处，近叶尖处的压力脉动受到主流叶片尾迹的激励作用更为强烈。结合图8(a)和图 8(b)可知，在前排叶片通道内，相比于近叶根和近叶尖，中间叶高处的压力脉动能量衰减程度更大。由图8(c)和图 8(d)可知，在后排叶片前缘附近， $50 \%$ 和 $10 \%$ 叶高处的压力脉动主频都发展为0.5倍叶频，并且 $10 \%$ 叶高处的主频幅值远大于 $50 \%$ 叶高，而 $90 \%$ 叶高处的压力脉动的主频变为叶轮叶频；在后排叶片尾缘附近，$10 \%$ 、 $50 \%$ 和 $90 \%$ 叶高处压力脉动的主频都发展为0.5倍叶频，并且其对应的幅值随着叶高位置的上升而略有下降。结合不同叶高的流场分布云图可知，叶高中部高能量流体向两端壁扩张掺混也使得不同叶高处的压力脉动相互影响。近叶根区域由于流场的损失小，压力脉动的能量衰减程度最小，在缝隙处对后排叶片前缘压力脉动的激励作用更强。

![](images/fd2b0f9a5e6f5f528b5a769167adc120998c3dfdaafaba3625428ef3f8b25c2c.jpg)  
图8不同叶高处各点压力脉动的频谱特性图 Fig. 8Frequency spectrum characteristic at different spans

# 3结论

本文对串列式叶栅离心扩压器中的非定常流动机理进行了研究，详细分析了设计流量下扩压器中的非定常流动特性。主要结论如下：

1)串列式叶栅扩压器内的流动以强非定常的三维黏性主流和缝隙流动为主要特征。压力脉动的传播在前排叶栅通道内迅速衰减，但在后排叶栅通道内，由于叶片尾迹流动和前后排叶片间缝隙流动的相互作用，使得压力脉动复杂化。

2)串列式叶栅扩压器前排叶片前缘附近的压力脉动同时受到离心叶轮的主流叶片和分流叶片的激励作用。串列叶栅间隙处，随着主流输运而来的叶轮主流和分流尾迹、串列叶栅缝隙流与前排叶片尾缘处的尾迹相互掺混、干扰与叠加，撞击到后排叶片的前缘，成为此处压力脉动新的激励，其产生的压力脉动的最大幅值和能量谱密度幅值比前排叶片尾缘处大。在近叶根区域，后排叶片前缘受到压力脉动的激励作用更强。

3)串列式叶栅扩压器内部前排叶片通道内压力脉动的主频为叶轮的叶片通过频率。后排叶片前缘附近压力脉动的主频变为0.5倍叶片通过频率。前排叶片前缘附近， $10 \%$ 和 $90 \%$ 叶高处的叶频对应的能量谱密度幅值小于 $50 \%$ 叶高处，相比于近叶根和近叶尖处，中间叶高处的压力脉动受到叶轮主流和分流叶片尾迹的激励作用更为强烈。在前排叶片通道内，相比于近叶根和近叶尖，中间叶高处的压力脉动能量衰减程度更大。

# 参考文献

[1] 彭泽琰，刘刚，桂幸民等．航空燃气轮机原理[M]．北 京：国防工业出版社,2008:3 PENG Zeyan,LIU Gang,GUI Xingmin,et al. Principles of Aviation Gas Turbine[M].Beijing: National Defense Industry Press,2008: 3   
[2]魏巍，刘波．小型涡轴发动机串列静子数值研究[J]．空 气动力学学报.2015,33(4):493--500 WEI Wei,LIU Bo.Numerical Investigations of a Tandem Stator Stage for a Small Turbo-shaft Engine[J].Acta Aerodynamica Sinica,2015,33(4): 493-500   
[3]Hergt A,Siller U.About transonic compressor tandem design - a principle study -[C]// ASME Turbo Expo. 2015.   
[4] Manas Madasseri Payyappalli, SR Shine. Numerical investigation on tandem compressor cascades[R]. ASME paper, GTINDIA2015-1311, 2015   
[5] Roberts D A, Kacker S C, Roberts D A, et al. Numerical Investigation of Tandem-Impeller Designs for a Gas Turbine Compressor[J]. Journal of Turbomachinery, 2001, 124(1):36-44   
[6] 齐翠霞，王志恒，席光．串列叶栅扩压器叶栅周向相对 位置对离心压气机级性能影响的数值研究[EB/OL]．中 国科技论文在线,2008 QI Cuixia, WANG Zhiheng，XI Guang. Numerical Investigation on the Effectsof Varying Cascade Circumferential Position of Tandem Cascade Diffuser on Centrifugal CompressorStage Performance[EB/OL]. Sciencepaper Online,2008   
[7]谢蓉，杨勇，海洋，等．离心压气机错排叶栅扩压器性 能研究[J]．燃气轮机技术,2010,23(2):48-52 XIE Rong，YANG Yong，HAI Yang. Research on Centrifugal Compressor Staggered Arrangement Cascade Diffusers[J]. Gas Turbine Technology,2010,23(2):48-52   
[8]Hergt A, Meyer R, Liesner K,et al.A New Approach for Compressor Endwall Contouring[C]// ASME 2011 Turbo Expo: Turbine Technical Conference and Exposition. American Society of Mechanical Engineers,2011:177-186   
[9]Abdelwahab A.Numerical Investigation of the Unsteady Flow Fields in Centrifugal Compressor Diffusers[C]/ ASME Turbo Expo 201O: Power for Land,Sea,and Air. 2010:2405-2418

# 第一作者联系方式：

姓名：周莉  
通信地址：陕西省西安市长安区东大镇西北工业大学新校区动力与能源学院  
手机号码：18292849616  
邮箱：zhouli@nwpu.edu.cn