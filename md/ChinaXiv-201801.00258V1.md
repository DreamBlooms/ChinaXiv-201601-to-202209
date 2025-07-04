# 高时空分辨的神经递质电化学传感检测技术发展与展望

![](images/b4dd9abec5ac3b73cc87065ace05bd6cfc10f2d000bbbf0205cd4c8b4493217a.jpg)

\*资助项目：国家自然科学基金项目（21422508、31470960)  
\*\*通讯作者  
修改稿收到日期：2017年12月2日

张月月1.2 左小磊1 樊春海1\*\*

1中国科学院上海应用物理研究所上海201800  
2中国科学院大学北京100049

摘要目前，实现对细胞神经递质释放过程的高时空分辨实时监测，仍存在诸多挑战。近些年来，通过发展不同的电化学检测技术实现了对细胞胞吐（exocytosis）释放以及细胞内部囊泡的定量化分析；一些研究使用这些技术，进行了细胞释放模式的探究。通过在电极表面修饰小分子或者调控电极尺寸，可实现高分辨率和高灵敏度的监测。文章重点介绍了神经递质电化学检测的机理、微米电极以及纳米电极检测技术的发展，对电化学传感与成像技术的联用进行了评述，并对电化学传感检测技术未来发展方向进行了展望。在此基础上，文章综合各种不同监测技术的优点，提出构建纳米电极与成像以及其他检测手段的联用技术，以大幅提高纳米电极在神经递质检测方面的能力。

关键词神经递质，高时空分辨率，囊泡释放，纳米电极，电化学 DOI 10.16418/j.issn.1000-3045.2017.12.003

胞吐（exocytosis）是神经细胞之间信息交流的基本方式，作为生物体内一项非常重要的生物进程，胞吐以及它的分子机制引起人们广泛的关注。细胞通过胞吐释放直径 50一$1 0 0 0 \mathrm { n m }$ 的囊泡到环境中，这些囊泡中的物质组成以及他们的释放动力学主要取决于细胞的种类和活性状态，这也就导致了细胞内部的囊泡在不同时间段、通过不同检测方式所得到的结果在性质以及数量上存在很大的差异和不均匀性[1-4]。囊泡膜是由磷脂层构成的复杂结构，其中包含一些跨膜蛋白和来自于细胞膜表面的亲水化合物，其非正常释放会影响相邻受体细胞的正常生理机能[5]。

磷脂与不同的蛋白、信号复合物发生作用，调节囊泡裂变、融合、释放位点上特异性酶的活性以及蛋白质的运输和补充[6-9]。 $a -$ 突触核蛋白（ $\mathfrak { a }$ -synuelein）的异常聚集和基因突变与家族性帕金森病（PD）有密切关系。有报道指出，$a -$ 突触核蛋白通过调控突触末端的囊泡储存池来控制囊泡运输动力学，从而控制在神经递质释放期间停靠在细胞膜表面的囊泡数量[10.I1]，而β-淀粉样蛋白也会对阿尔茨海默病（AD）的发病存在类似的影响。这些蛋白通常会处于神经细胞末端，在神经递质释放中所发挥的作用尚不明确。但有些研究表明，在神经细胞或者嗜铬细胞中，这些蛋白的表达量提高会导致囊泡融合孔扩大从而加速囊泡的释放，降低胞吐释放事件的数目[12]。tau蛋白在病理状态下会产生累积，引起突触前端功能障碍，进而导致肌动蛋白聚合，使得囊泡之间产生交联并抑制囊泡在细胞膜上面的停靠，导致细胞无法正常胞吐释放以及疾病发生[13-16]

综上所述，能够及时、准确、快速地对胞内囊泡及其释放情况进行检测，是近些年来神经科学领域面临的一个非常重大的问题。电化学技术由于其快速便捷的特点，可以实现对生物系统中快速胞吐释放过程的实时定量分析[17,18]，大幅度提高疾病早期检测的能力，其中微电极电化学能够在实现单细胞监测的基础上提升检测的灵敏度、特异性以及抗干扰能力。但是，由于胞吐囊泡通常比较小（直径一般为 $3 0 { \mathrm { - } } 1 0 0 \mathrm { n m }$ ）且聚集状态不固定，亟需一种更高分辨率的技术来优化检测效率与分辨率之间的关系。在这方面，纳米电化学技术的出现为纳米尺度囊泡的传感检测带来了新机遇，纳米电化学技术与生物传感技术的有机结合，可以在深入研究纳米尺度囊泡碰撞作用机制的基础上，针对生物传感领域面临的挑战性问题，达到单囊泡、单分子水平的分析，实现高灵敏度、高特异性以及高时空分辨率的检测。

# 1微电极监测机理

信息以极快的速度通过神经突触进行传输[19]，大多数突触的传递时间虽然只有几毫秒，但是这个速度对于大脑的整体运作至关重要。当动作电位沿轴突末梢传导时，它会使神经末梢去极化并打开突触前膜的 $\mathrm { C a } ^ { 2 + }$ 通道， $\mathrm { C a } ^ { 2 + }$ 内流后 $1 \mathrm { m s }$ 内触发神经递质释放。

突触前端的神经递质释放是膜介导的，突触前端内部充满囊泡，尺寸不等（ $3 0 { \mathrm { - } } 1 0 0 { \mathrm { n m } }$ ），每个囊泡中包含高浓度的神经递质。当 $\mathrm { C a } ^ { 2 + }$ 诱发囊泡膜与突触前端细胞膜的特异性区域（俗称活性区域）快速融合的同时，释放发生（图1）。活性区域通常位于突触后端包含神经递质受体较为密集方位的对面区域。囊泡在整个突触前端的膜运输循环过程包括：（1）突触前端循环囊泡形成，以及填充神经递质（NT）；（2）囊泡运输到接近突触前端细胞膜的位置，并在此聚集等待胞吐发生；（3）在囊泡膜上的蛋白以及细胞膜活性区域蛋白的共同作用下，囊泡停靠并被控制在释放活性区域；（4）囊泡处于待融合阶段；（5） $\mathrm { C a } ^ { 2 + }$ 引发融合孔打开，神经递质释放。胞吐过程中，囊泡存在不同的释放方式，包括：囊泡完全与细胞膜融合的全释放模式，融合孔闪烁开关导致的“kiss andstay”（部分融合且停留）模式，以及依赖于网格蛋白的(a）囊泡从突触前端运输至突触间隙产生释放的过程；（b）神经细胞突触间隙中胞吐释放的神经递质分子数统计结果

![](images/dd0c369e023e33bf9d50e9ec9bae2ba5d43d0c222e7256012345fda3104178fb.jpg)  
图1突触部位囊泡释放以及循环图[25.36]

"kiss and run” （部分融合即离开）模式[20-25]

神经递质释放过程包含了复杂的物理化学过程[26-28],亦有不同检测方法。本文针对不同的胞吐释放模式，以碳纤维纳米电极对细胞胞吐的实时监测为例进行介绍。理想状态下，外界对单细胞某个部位施加刺激，使细胞表面活性区域的囊泡发生释放，囊泡中的分子碰撞到位于细胞表面的电极界面，在一定氧化电压的作用下失去电子发生氧化。同时，电化学设备将这种失电子行为转化为电信号输出。在细胞内部的监测中，电极表面存在一些羧基官能团，由于静电吸引作用，这些羧基官能团容易与亲水性的囊泡发生碰撞，导致囊泡破裂同时释放出其内部的分子，而这些分子在电极表面发生氧化[29-31]

因此，碳纤维纳米电极在纳米囊泡监测方面的应用，不仅克服了电极与细胞内蛋白之间的非特异性吸附，同时也提高了检测的分辨率和灵敏度。神经细胞内部囊泡中包含各种不同类型的神经递质，包括多巴胺、羟色胺、肾上腺素、去肾上腺素等，嗜铬细胞中囊泡主要包含多巴胺，而巨噬细胞中则包含一些活性氧以及活性氮成分[32]，这些分子都很容易发生氧化。在监测过程中，只有超过监测对象的氧化电压才能将其氧化，并产生电化学信号。通过调整电极所加电压或者细胞类型来控制可检测的分子种类，通过在电极表面修饰特定分子增加电极与待测对象之间的相互作用力[33-38]，均可使检测具有更高的灵敏度、特异性以及更低的检测限。

影响胞吐释放的因素也是多种多样的，研究人员通常对细胞作一系列处理来控制细胞释放分子的数量或释放事件的多少。比如：利血平可以使囊泡释放分子数减小[39]；L-DOPA作为多巴胺的前体，可以增加释放的分子数；顺铂在不同浓度下对细胞释放的影响有显著差别，高浓度抑制，低浓度促进，这可能与细胞内的某种蛋白作用有关[40]；锌离子不会改变释放分子数，但是它会使融合孔减小，改变释放动力学的速度，并引起更高的释放比例[41]。单个囊泡的电化学信号非常微弱，在皮安（pA）级别，很容易导致信号湮没，因此在监测过程中合理选用处理细胞的方法对于细胞实时监测来说同样重要。

# 2基于高时空分辨率的囊泡检测方法

关于细胞的实时监测，现在最普遍的方法是成像，但是成像方法虽然比较直观，也存在诸多挑战[42-47]，例如：细胞胞吐释放神经递质的实时监测，成像技术在时间以及空间分辨率上还存在一定的局限性[48]。对于单细胞而言，特别是在神经科学中神经递质的释放研究中，微电极的应用已经相对成熟。微电极相对于宏观尺寸电极而言具有更小的尖端尺寸以及更高的灵敏度，非常适合单细胞研究，现在已经成功应用于检测蛋白[49]、小分子[50]以及一些离子[41]和病毒等[51-54]。Wightman 等最先开展通过电化学方式进行细胞胞吐的实时监测工作，通过制备直径为 $2 \mu \mathrm { m }$ 的碳纤维微米电极，监测嗜铬细胞表面若干个微米区域的胞吐释放情况[55-58]。后来，越来越多的研究者针对不同种类的细胞以及人工制备的囊泡进行检测并加以分析。近些年随着囊泡检测工作的不断进行，检测对象也在发生变化，从最初的单细胞到单囊泡以及单分子[59-63]。与此同时，检测方式也在发生变化，逐渐影响了检测的分辨率以及灵敏度[41,64-66]。

# 2.1微米电极

微米电极尺寸在微米级别，尖端足够覆盖整个细胞体，具有高的信噪比，可以测量非常小的电流强度并保证监测的效率。在细胞以及活体检测中所用的微米电极主要有金属电极和碳纤维电极两种，其中碳纤维微米电极是微电极中非常重要的一个组成部分，自从应用以来，微电极伏安法就被认为是研究大脑中神经递质传递的一项不可或缺的技术，一直在生物学领域发挥重要作用（图2）[49,50,52,53,7,68]。通过碳纤维微米电极，可以从单细胞水平对神经递质的释放进行监测[69-75]

通过微电极电化学检测单细胞释放事件是非常强有力的方法，它可以实时监测分子释放过程并且提供囊泡释放事件的动力学信息，实现在单细胞水平的定量分析。传统微米电极使用环氧树脂封闭玻璃管尖端，然后

# ChinaXiv合作期刊

![](images/5e760687dd02e8271d0bb887c587d5b23a3710ba15d35e88c679752fb74e86e5.jpg)  
图2微电极监测的相关应用

(a）微流控芯片监测细胞团簇受刺激后的释放[7]；（b）镀金的碳纤维微电极检测小鼠脑中的神经递质[68]；（c）微电极监测液滴中的电化学活性物质[52]；（d）微电极监测病毒颗粒[53]；（e）微电极监测细胞内部的低拷贝数蛋白[49]；（f）微电极监测单细胞中的葡萄糖[50]

用胶体石墨回填玻璃管，该方法存在4个缺点：（1）会导致玻璃/碳纤维的接触面都存在环氧树脂，严重影响了电极性能；（2）不可避免的封闭不完全甚至泄露，会导致低信噪比、低灵敏度、低电极寿命以及液体污染;（3）不能保证胶体石墨的填充成功率，电极制作成品率比较低；（4）环氧树脂可以溶解在有机溶剂中，因而不能在有机溶剂中监测或者进行特殊修饰。为了克服这些缺点，Strein 和Ewing[76]、Malinski 和 Taha[77用火焰刻蚀法制备电极。但是，电极尖端仍然存在环氧树脂，增加了刻蚀难度并且难以调控刻蚀进程，电极表面不够平滑。在此方法的基础上，黄卫华课题组[4报道了一种新的改进方式，其中没有环氧树脂对尖端的处理，通过火焰熔融将玻璃管和碳纤维融合在一起，形成了比较高效的封闭，这样制备的电极尖端比较平滑，具有很好的电化学特性，电化学检测中检测灵敏度高，主要应用于监测细胞胞吐释放神经递质以及活体研究。

细胞释放有很多种模式，要正确判断当前的模式种类，需要分别对细胞内部囊泡以及细胞胞吐释放的囊泡进行监测。对细胞内囊泡中分子的准确定量，最常用的方法是将细胞裂解后进行检测[73]。细胞裂解释放和超速离心分离出囊泡，然后通过微米电极进行电化学检测，检测结果可以得到若干个信号峰，而其中每个峰都代表一个囊泡的碰撞破裂后的氧化事件。很多研究都发现,胞吐过程中，囊泡仅仅释放一部分神经递质[78]，剩余未释放部分以另一种形式循环或者继续释放，而神经细胞中大多为“kiss and run”模式。

微电极在活体检测中的应用已经有几十年的历史，将碳纤维微米电极或者镀金的微电极通过显微操控技术置于小鼠大脑中进行实验，可以在整个时间范围内进行高灵敏检测。这种设计被广泛应用于神经生物学中，尤其是纹状体中多巴胺的检测。最初Adams研究发现活体电化学分析技术非常适用于实时监测大脑中的神经递质[71]。后来，很多研究人员也对大脑中多种神经递质（羟色胺、多巴胺等）进行检测并分析[8.79-85]

# 2.2纳米电极

化学突触之间信息的正常传递对于脑功能运行具有非常重要的作用。突触是由突触前端、突触后端以及之间的间隙（ $2 0 \mathrm { - } 5 0 \mathrm { n m }$ ）组成。纳米尺度的间隙使得实时监测细胞之间神经递质的突触释放成为巨大的挑战。在过去很多年里，人们很少关注到电极尺寸和电极表面的几何形状对电化学过程带来的影响，以及尺寸和检测信号之间的直接性关系。细胞大小通常在几微米到几十微米之间，每个细胞中包含上千个纳米级别的囊泡[2.5.8-88]，每个囊泡中储存着大量的信息传递分子。传统的微米电极可以反映整个细胞表面一部分区域的胞吐特性，但是并不适用于区分每一个单独释放位点的性质[75]，也不能探测纳米尺寸突触间隙之间神经递质释放的机理（图3a）[89]。纳米电极的发展为高分辨率的检测带来了机遇，很多报道[90-92]已经指出了小尺寸的纳米电极在神经科学以及生命科学中的应用潜力。

胞吐实时监测过程中，纳米电极与细胞之间的距离控制在 ${ 5 \mu \mathrm { m } }$ 以内，这样能够最小化扩散产生的影响。通过人工模拟细胞以及囊泡[93.94]发现，细胞膜与电极之间的距离会影响单囊泡释放的瞬时电流（图3b）[95]。假如囊泡尺寸比电极小且囊泡融合区域没有靠近电极表面边缘区域，则我们假设的定量氧化行为完全有效，但是现实监测中往往没有如此精确。监测过程中，神经递质通过流动和扩散到达膜外区域，它们从释放位点释放并呈半球几何形状稀释并碰撞氧化。在此过程中，大电极可以有效封阻分子在X轴方向上面的传递，只能在膜和电极之间移动，检测效率非常高[95-97]。但是，电极增加会大大降低电极的时间和空间分辨率，以至于难以区分单一囊泡和多个囊泡聚集体的情况。因此，选择一种与囊泡相匹配的电极，并调控好检测效率与时空分辨率之间的关系，在细胞监测中是重要且具有挑战性的问题。

利用碳纤维纳米电极进行实时监测可以得到囊泡中分子的定量化信息以及动力学参数（图3c）[9.,2]。一个正常的信号峰是由峰脚、上升阶段和下降阶段组成。峰脚是囊泡与细胞膜开始融合阶段，此时融合孔比较小，因此释放速度比较慢；上升阶段是融合孔张开，大规模释放神经递质并氧化的过程，初期因为囊泡中递质含量比较高，通常上升阶段比较陡峭；下降阶段是囊泡监测后期，分子浓度降低，氧化进程变慢，表现为比较平缓和更延展的曲线形式，通过对信号峰进行积分以及数学运算可以得到囊泡尺寸、包裹分子数以及分子浓度信息[89,98-100]。半峰宽为峰高一半时候的峰宽度，表明囊泡从释放初始阶段到释放完毕速率的大小，是释放动力学的体现，半峰宽的大小与监(a）不同的细胞胞吐释放模式猜想[89]；（b）模拟细胞和囊泡体系，探索电极尺寸与信号之间的关系[95]；（c）纳米电极监测神经细胞突触部位胞吐释放的神经递质以及动作电位，得到其释放的定量信息以及动力学参数[90]；（d）微米电极与纳米电极监测细胞覆盖位点对比[75]；（e)纳米电极在细胞外部监测以及穿透细胞进行内部监测 [4i]

![](images/7ff927f93867d634927b5506f2d0a272bef67f9a77b537a763e1aeed7f30f781.jpg)  
图3纳米电极在细胞监测中的应用

测囊泡大小及内部包裹神经递质的量直接相关。

纳米电极研究表明，细胞表面存在活性区域和非活性区域，而其中大部分表面都是非活性的[74,75]。同时在活性区域还存在特殊活性位点，同一个位点可能存在多个囊泡连续释放的情况，只有纳米电极恰好处于活性位点位置时才能监测到信号（图3d）。黄卫华课题组首次报道了通过纳米电化学方法，利用纳米电极在同一释放位点监测到多个囊泡释放出多巴胺的情况[75]，这主要归因于纳米电极的高分辨率，可以区分多个囊泡连续释放。后来他们又对神经细胞之间连接部位的神经递质释放进行监测并分析[92]，得到囊泡中分子含量以及释放动力学方面的信息。纳米电极尖端尺寸只有 $1 0 0 \mathrm { n m }$ 左右，既满足了与囊泡之间的匹配性质，穿透细胞膜的同时又不会对细胞造成伤害。因此，纳米电极在外部监测的同时，还可以实现对细胞内部囊泡的实时监测。Majdi等通过碳纤维纳米电极穿透细胞膜检测了单细胞内部囊泡中的神经递质含量[101]，并将之与外部监测对比，发现胞吐释放的量确实少于囊泡中实际量[102]（图3e），当然胞外扩散也占一定的比重。相对于细胞裂解的方法，现在可以直接在细胞环境中进行检测，这是一种更为准确和直接的对细胞内囊泡中分子定量的手段。金属电极[51,103,104]在纳米电极中也占了很大的比重，如施国跃等[105]用金纳米电极（尖端尺寸 $3 \mathrm { n m }$ ）对细胞的胞吐释放进行研究。金电极电子传输速率快，检测灵敏度高，但是也容易吸附细胞内部的复杂蛋白，造成污染，严重影响电极寿命。目前，碳纤维纳米电极在单细胞乃至单囊泡检测领域仍占有至关重要的地位。

追踪，却缺乏探索动力学参数以及定量分析所需要的时间分辨率，另外其他的一些细胞监测手段也同样存在优势和局限性[107,108]。考虑到这些方法之间的互补性，如果将两种或两种以上的技术联用，就能够更直观且高分辨率的对胞吐事件进行监测。

![](images/388b27e522dbbc83ed3422d803609ffa060630a4045ecc52a7d0aed0b2ab6708.jpg)  
图4细胞内部囊泡不同检测方法联用展示

(a）碳纤维微米电极通过细胞裂解法检测完整囊泡中的分子量[73];(b）全内反射荧光显微镜（TIRFM）与微流控芯片连用监测囊泡释放[64]；（c）基于等离子体的电化学阻抗显微镜成像[65]；（d）扫描电化学显微镜成像[66]

# 2.3 其他联用技术

纳米电极具有很高的空间分辨率以及与胞吐释放动力学相匹配的毫秒级别以下的时间分辨率，但是缺乏一定的直观性（图4a）[73]，无法准确定位细胞表面的释放位点；微流控具有很好的控制性能，但是分辨率通常比较低[67,106]（图2a）；全内反射荧光显微镜（TIRFM）具有一定的空间分辨率，借助荧光可以实现囊泡释放位点的

微流控通量高，通过设计通道宽度，检测限可以达到单细胞水平；而电化学检测方法灵活性强，两者与碳纤维微电极联用，可对细胞中裂解的囊泡进行快速检测。因为检测过程中囊泡会不断碰撞到电极表面，检测效率高[2]。将TIRFM与微流控芯片以及电化学技术相结合（图4b）[64]，可以通过记录荧光强度来观察囊泡分泌过程，通过对比产生的氧化电流峰的不同对整个释放事件定量，两者相关联能够获得具有高时空分辨率并且可视化的表征[64]

基于等离子体的电化学阻抗成像技术[65]，将等离子体成像与电化学阻抗结合在一起（图4c），能够在不需要标记的情况下对神经细胞在刺激状态下的动作电位成像。同时，简化了样品准备时间，并且排除在神经细胞上面标记荧光基团对相关功能带来的不良影响，可以与传统的膜片钳以及荧光显微镜相媲美。

扫描电化学显微镜（SECM），是一种扫描探针显微技术[6,109,11]，利用高分辨率的微电极作为测量工具（图4d），已经应用于细胞的新陈代谢、呼吸作用以及细胞膜对化学试剂的渗透作用等研究，并且能够作用于单个细胞。研究过程中盘状微电极放置在一个包含氧化还原物质的溶液中，在超过其氧化电压的条件下，能够得到典型的S型循环伏安曲线和稳态电流。电极位于非常靠近样品的位置，根据样品性质的不同分为负反馈和正反馈，得到微电流减小或增大的曲线。而反馈的程度取决于电极与细胞之间的距离，可以同时对细胞表面的形态以及释放的化学分子进行扫描。

综上所述，联用技术可以发挥多种不同检测手段的优势，克服单一技术的不足，也将是未来检测发展的一种主流趋势。

# 3总结与展望

近些年来，人们已经发展了多种检测方法，包括微流控、微米电极、纳米电极、荧光、高效液相色谱、TIRFM、SECM等。其中，电化学方法具有快速、便捷、检测效率高以及灵敏度高等特点，应用最为广泛。细胞内部囊泡尺寸非常小，随着技术的不断进步，单纯荧光的方法已经不足以满足研究的需求，纳米电极的出现为囊泡的高时空分辨率传感检测创造了条件。纳米电极尖端尺寸非常小，并且能够可控的进行调整，可以与囊泡达成很好的匹配性，在不损失分辨率的状态下尽量保持高的检测效率，实现真正意义上的单囊泡检测。同时，纳米电化学技术还可以提供较为详细的分子数、浓度以及尺寸等定量化信息，通过调整电极表面所加电压，来调控检测的分子种类。

基于高时空分辨率的实时监测以及可视化的需求，监测方式不再只是局限于单一的某种技术，迫切需要发展多种技术联用方法，在满足分辨率的同时又能直观观察到目标所在的具体方位。为了能够适应当前需求，未来继续发展高分辨率的成像技术，并且在纳米电极制备方面进行更精确的调整，实现检测过程可视化，检测结果定量化，并能将其一一对应。

# 参考文献

1 Borgonovo B, Cocucci E,Racchetti G, et al. Regulated exocytosis: a novel, widely expressed system. Nature Cell Biology, 2002, 4(12): 955-962.   
2 van der Vlist E J,Nolte H E,Stoorvogel W,et al. Fluorescent labeling of nano-sized vesicles released by cells and subsequent quantitative and qualitative analysis by high-resolution flow cytometry.Nature Protocals,2012,7(7): 1311-1326.   
3 Kavalali E T.The mechanisms and functions of spontaneous neurotransmitter release.Nature Review Neuroscience,2015, 16(1): 5-16.   
4Sezgin E,Levental I,Mayor S,et al.The mystery of membrane organization: composition,regulation and roles of lipid rafts. Nature Review Molecular Cell Biology,2017,18(6): 361-374.   
5Thery C, Ostrowski M, Segura E.Membrane vesicles as conveyors of immune responses.Nature Review Immunology, 2oo9,9(8): 581-593.   
6Grover A,Schmidt B F,Salter R D,et al. Genetically encoded pH sensor for tracking surface proteins through endocytosis. Angewandte Chemie International Edition,2012, 51(20): 4838- 4842.   
7Salem N, Faundez V, Horng JT, et al.A v-SNARE participates in synaptic vesicle formation mediated by the AP3 adaptor complex. Nature Neuroscience,1998,1(7): 551-556.   
8 Sprong H, Sluijs P V, Meer G V. How proteins move lipids and lipids move proteins. Nature Reviews Molecular Cell Biology, 2001,2(7): 504-513.   
9 Zhou Q,Lai Y, Bacaj T, et al. Architectureof the synaptotagmin — SNARE machinery for neuronal exocytosis. Nature, 2015, 525(7567): 62-67.   
10 Fusco G, Pape T, Stephens A D,et al. Structural basis of synaptic vesicle assembly promoted by $\propto$ -synuclein. Nature Communications,2017,7: 12563.   
11 Roetne R J, Jacobsen H. Alzheimer's disease: from pathology to therapeutic approaches. Angewandte Chemie International Edition, 2009, 48(17): 3030-3059.   
12 Selkoe D J. Showing transmitters the door: synucleins accelerate vesicle release.Nature Neuroscience,2017,20(5): 629-631.   
13 Boulanger C M,Loyer X, Rautou PE, et al. Extracelular vesicles in coronary artery disease. Nature Review Cardiology, 2017, 14(5): 259-272.   
14 Buzas EI, Gyorgy B,Nagy G,et al.Emerging role of extracelular vesicles in inflammatory diseases. Nature Review Rheumatology, 2014, 10(6): 356-364.   
15 Kolter T, Sandhoff K. Sphingolipids - Their metabolic pathways and the pathobiochemistry of neurodegenerative diseases. Angewandte Chemie International Edition, 2010,38(11):1532- 1568.   
16 Zhou LJ, McInnes J, Wierda K,et al. Tau association with synaptic vesicles causes presynaptic dysfunction. Nature Communications, 2017, 8: 15295.   
17 Najafinobar N, Mellander L J, Kurczy M E, et al. Cholesterol alters the dynamics of release in protein independent cell models for exocytosis. Scientific Reports,2016,6: 33702.   
18 MellanderL J,Kurczy ME,Najafinobar N,et al. Two modes of exocytosis inan artificial cell. Scientific Reports, 2014, 4: 3847.

19Rohrbough J,Broadie K.Lipid regulation of the synaptic vesicle cycle.Nature Review Neuroscience,2005, 6(2):139-150.

20 Bacia K. Intracellular transport mechanisms: Nobel Prize for Medicine 2013.Angewandte Chemie International Edition, 2013, 52(48): 12486-12488.   
21 Fernandez TF, Grover L M, Stephenson B A,et al. Vesicles in nature and the laboratory: elucidation of their biological properties and synthesis of increasingly complex synthetic vesicles. Angewandte Chemie International Edition,2017, 56(12): 3142- 3160.   
22 Flagmeier P, De S,Wirthensohn D C,et al. Ultrasensitive measurement of $\mathrm { C a } ^ { 2 + }$ influx into lipid vesicles induced by protein aggregates. Angewandte Chemie International Edition, 2017, 56(27): 7750-7754.   
23 McMahon H T, Boucrot E.Molecular mechanism and physiological functions of clathrin-mediated endocytosis.Nature Review Molecular Cell Biology,2011,12(8): 517-533.   
24 Rothman JE. The principle of membrane fusion in the cell (Nobel Lecture). Angewandte Chemie International Edition, 2014, 53(47): 12676-12694.   
25 Sudhof T C.The molecular machinery of neurotransmitter release (Nobel Lecture). Angewandte Chemie International Edition, 2014, 53(47): 12696-12717.   
26 Ahmed W W, Saif TA.Active transport of vesicles in neurons is modulated by mechanical tension. Scientific Reports,2014, 4: 4481.   
27 Gruenberg J. The endocytic pathway: a mosaic of domains.Nature Reviews Molecular Cell Biology,2001,2(10): 721-730.   
28 Thery C, Zitvogel L,Amigorena S. Exosomes: composition, biogenesis and function. Nature Review Immunology,2002, 2(8): 569-579.   
29 Bath B D,Michael D J,Trafton B J,et al. Subsecond adsorption and desorption of dopamine at carbon-fiber microelectrodes. Analytical Chemistry,2000,72(24): 5994-6002.   
30 Runnels PL, Joseph JD,Logman MJ,et al. Effect of pH and

surface functionalities on the cyclic voltammetric responses of carbon-fiber microelectrodes.Analytical Chemistry,1999,71(14): 2782-2789.

31 CahillP S,Walker QD,Finnegan JM,et al.Microelectrodes for the measurement of catecholamines in biological systems. Analytical Chemistry,1996,68(18):3180-3186.

32WangY,Amatore C.Nanoelectrodes for determinationof reactive oxygen and nitrogen species inside murine macrophages.PNAS, 2012,109(29):11534-11539.

33 Chen R S,Huang WH, Tong H,et al.Carbon fiber nanoelectrodes modified by single-walled carbon nanotubes. Analytical Chemistry, 2003,75(22): 6341-6345.

34 Huang W H, Cheng W, Zhang Z,et al. Transport, location,and quantal release monitoring of single cells on a microfluidic device. Analytical Chemistry,2004, 76(2): 483-488.

35WangJH,HuangWH,LiuYM,etal.Capillary electrophoresis immunoassay chemiluminescence detection of zeptomoles of bone morphogenic protein-2 in rat vascular smooth muscle cells. Analytical Chemistry,2004,76(18): 5393-5398.

36 Bath B D，Martin HB,Wightman R M,et al.Dopamine adsorption at surface modified carbon-fiber electrodes.Langmuir, 2001,17(22): 7032-7039.

37Hermans A,Seipel AT,Miller CE,et al.Carbon-fiber microelectrodes modified with 4-sulfobenzene have increased sensitivity and selectivity for catecholamines.Langmuir the Acs Journalof Surfaces & Colloids,2006,22(5):1964-1969.

38 Hashemi P,Walsh PL,Guillot T S,et al. Chronically implanted, nafion-coated Ag/AgCl reference electrodes for neurochemical applications.ACS Chemical Neuroscience,2011,2(11): 658-666.

39 Omiatek D M,DongY,Heien ML,et al.Only a fraction of quantal content is released during exocytosis as revealed by electrochemical cytometry of secretory vesicles.ACS chemical neuroscience,2010,1(3): 234-245.

40 Li X C,Dunevall J,Ewing AG.Using single-cell amperometry to reveal how cisplatin treatment modulates the release of catecholamine transmitters during exocytosis.Angewandte Chemie International Edition,2016,55(31): 9041-9044.

41 Ren L,Pour M D,Majdi S,et al. Zinc regulates chemicaltransmitter storage in nanometer vesicles and exocytosis dynamics as measured by amperometry.Angewandte Chemie International Edition,2017,56(18): 4970-4975.

42Spicer C D,Triemer T,Davis B G.Palladium-mediated cellsurface labeling. Journal of the American Chemical Society,2012, 134(2): 800-803.

43Tokunaga T,Namiki S,Yamada K,etal.Cell surface-anchored fluorescent aptamer sensor enables imaging of chemical transmitter dynamics. Journal of the American Chemical Society, 2012,134(23): 9561-9564.

44 Liu Y, Zhang X,Chen W T,et al. Fluorescence turn-on folding sensor to monitor proteome stress in live cells.Journal of the American Chemical Society,2015,137(35):11303-11311.

45 Qiu L P,Zhang T,Jiang JH,et al.Cell membraneanchored biosensors for real-time monitoring of the cellular microenvironment. Journal of the American Chemical Society, 2014,136(38):13090-13093.

46 Porterfield WB,JonesKA,McCutcheon D C,et al.A“Caged" luciferin for imaging cell-cell contacts. Journal of the American Chemical Society,2015,137(27): 8656-8659.

47Sasmal DK,YadavR,Lu HP.Single-molecule patch-clamp FRET anisotropy microscopy studies of NMDA receptor ion channel activation and deactivation under agonist ligand binding in living cells.Journal of the American Chemical Society,2016,138(28): 8789-8801.

48 Kruss S,Salem D P, Vukovic L,et al. High-resolution imaging of cellular dopamine efflux using a fluorescent nanosensor array. PNAS,2017,114(8): 1789-1794.

49 Liu J,Yin DY,Wang S S,et al.Probing low-copy-number proteins in a single living cell. Angewandte Chemie International Edition,

2016,55(42):13215-13218.

50 Pan RR,Xu M C,Jiang D C,et al.Nanokit for single-cell electrochemical analyses.PNAS,2016,113(41):11436-11440.

51Park JH, Thorgaard S N, Zhang B,et al. Single particle detection by area amplification:single wall carbon nanotube attachment to a nanoelectrode.Journal of the American Chemical Society,2013, 135(14): 5258-5261.

52 Dick JE,Renault C,Kim B K,et al. Simultaneous detection of single attoliter droplet collisions by electrochemical and electrogenerated chemiluminescent responses.Angewandte Chemie International Edition,2014,53(44):11859-11862.

53DickJE,Hilterbrand A T,Boika A,etal.Electrochemical detection of a single cytomegalovirus at an ultramicroelectrode and its antibody anchoring.PNAS,2015,112(17): 5303-5308.

54Lebegue E,Anderson C M,DickJE,etal.Electrochemical detection of single phospholipid vesicle collisions at a Pt ultramicroelectrode.Langmuir,2015,31(42):11734-11739.

55 TroyerKP,Wightman R M.Temporal separation of vesicle release from vesicle fusion during exocytosis. Journal of Biological Chemistry,2002,277(32):29101-29107.

56 Troyer K P,Wightman R M.Dopamine Transport into a Single Cell in a Picoliter Vial.Analytical Chemistry,2002,74(20):5370- 5375.

57 Hochstetler S E,Puopolo M,Gustincich S,et al.Real-time amperometric measurements of zeptomole quantities of dopamine released from neurons.Analytical Chemistry,20oo,72(3):489- 496.

58Xin Q,WightmanR M.Simultaneous detection of catecholamine exocytosis and $\mathrm { C a } ^ { 2 + }$ release from single bovine chromaffin cells using a dual microsensor. Analytical Chemistry,1998,70(9): 1677-1681.

59 Wang P,Ge ZL,Pei H,etal. Quartz crystal microbalance studies on surface-initiated DNA hybridization chain reaction.Acta Chimica Sinica,2012, 70(20):2127-2132.

60LiuB,Ouyang X,Chao J,etal.Self-assembly ofDNA origami using rolling circle amplification based DNA nanoribbons.Chinese Journal of Chemistry,2014,32(2): 137-141.

61 Justin G J. Single entity electrochemistry progresses to cell counting.Angewandte Chemie International Edition,2016,55(42): 12956-12958.

62 Sepunaru L,Sokolov S V,Holter J,et al. Electrochemical red blood cell counting:one at a time.Angewandte Chemie International Edition,2016, 55(33): 9768-9771.

63Laforge F O,Carpino J,Rotenberg SA,et al.Electrochemical attosyringe.PNAS,2007,104(29):11895-11900.

64Liu XQ,SavyA,Maurin S,etal.A dual functional electroactive and fluorescent probe for coupled measurements of vesicular exocytosis with high spatial and temporal resolution.Angewandte Chemie International Edition,2017, 56(9): 2366-2370.

65 Liu X W,Yang Y Z,Wang W,et al.Plasmonic-based electrochemical impedance imaging of electrical activities in single cells.Angewandte Chemie International Edition,2017, 56(30): 8855-8859.

66 Takahashi Y, Shevchuk A I,Novak P,et al. Topographical and electrochemical nanoscale imaging of living cells using voltageswitching mode scanning electrochemical microscopy.PNAS, 2012,109(29): 11540-11545.

67 Abe H, Ino K,Li C,et al. Electrochemical imaging of dopamine release from three-dimensional-cultured PC12 cells using large-scale integration-based amperometric sensors.Analytical Chemistry,2015,87(12): 6364-6370.

68Dong H, Zhang L M,Liu W,et al.Label-free electrochemical biosensor for monitoring of chloride ion in an animal model of Alzhemier's disease.ACS Chemical Neuroscience,2017,8(2): 339-346.

69 Herr NR,Belle A M,DanielKB,et al.Probing presynaptic regulation of extracellular dopamine with iontophoresis.ACS Chemical Neuroscience,2010,1(9): 627-638.

70 Kile B M,Walsh PL,McElligott ZA,et al.Optimizing the temporal resolution of fast-scan cyclic voltammetry. Chemical Neuroscience,2012,3(4):285-292.

71 Rice ME,Oke AF,Bradberry C W,et al.Simultaneous voltammetric and chemical monitoring of dopamine release in situ.Brain Research,1985,340(1):151-155

72Omiatek D M,Bressler AJ,Cans A S,et al.The real catecholamine content of secretoryvesicles in the CNS revealed by electrochemical cytometry. Scientific Reports,20l2,3(3): 1447.

73 Dunevall J,Fathali H, Najafinobar N,et al.Characterizing the catecholamine content of single mammalian vesicles by collisionadsorption events at an electrode.Journal of the American Chemical Society,2015,137(13):4344-4346.

74Huang WH,Pang D W,Tong H,et al.A method for the fabrication of low-noise carbon fiber nanoelectrodes. Analytical Chemistry, 2001,73(5):1048-1052.

75 Wu W Z,Huang W H,Wang W,et al. Monitoring dopamine release from single living vesicles with nanoelectrodes.Journal of the American Chemical Society,2005,127(25): 8914-8915.

76 Strein T G,Ewing A G.Characterization of submicron-sized carbon electrodes insulated with a phenol-allylphenol copolymer. Analytical Chemistry,1992,64(13):1368-1373.

77Malinski T,Taha Z.Nitric oxide release froma single cell measured in situ by a porphyrinic-based microsensor.Nature, 1992,358(6388): 676-678.

78Dernick G,Gong L W, TabaresL,et al.Patch amperometry:highresolution measurements of single-vesicle fusion and release. Nature Methods,2005,2(9): 699-708.

79HashemiP,DankoskiE C,Petrovic J,etal.Voltammetric detection of 5-hydroxytryptamine release in the rat brain.Analytical Chemistry,2009,81(22): 9462.

80 Hashemi P,Dankoski EC,Wood K M,et al.In vivo electrochemical evidence for simultaneous 5-HT and histamine release in the rat substantia nigra pars reticulata following medial forebrain bundle stimulation.Journal ofNeurochemistry,2011, 118(5): 749-759.

81 Zachek M K,Takmakov P,Moody B,et al.Simultaneous decoupled detection of dopamine and oxygen using pyrolyzed carbon microarrays and fast-scan cyclic voltammetry.Analytical Chemistry,2009,81(15): 6258-6265.

82 Zachek MK, Takmakov P, Park J,et al. Simultaneous monitoring of dopamine concentration at spatially different brain locations in vivo.Biosensors and Bioelectronics,2010,25(5):1179-1185.

83ParentKL,HillDF,CrownL M,et al.Platform to enable combined measurement of dopamine and neural activity. Analytical Chemistry,2017,89(5): 2790-2799.

84ZhangLM,LiuFL, Sun XM,etal.Engineering carbon nanotube fiber for real-time quantification of ascorbic acid levels in a live rat modelof Alzheimer's disease.Analytical Chemistry,2017,89(3): 1831-1837.

85Rodeberg N T,Sandberg S G,JohnsonJA,etal.Hitchhiker's guide to voltammetry:acute and chronic electrodes for in vivo fast-scan cyclic voltammetry.ACS Chemical Neuroscience,2017, 8(2): 221-234.

86ReySA,SmithCA,FowlerMW,etal.Ultrastructural and functional fate of recycled vesicles in hippocampal synapses. Nature Communications,2015,6: 8043.

87Giuliana F,Tillmann P,Stephens AD,et al.Structural basis of synaptic vesicle assembly promoted by $\propto$ -synuclein.Nature Communications,2016,7: 12563.

88 Hinckelmann M V, Virlogeux A, Niehage C, et al. Self-propelling vesicles define glycolysis as the minimal energy machinery for neuronal transport.Nature Communications,2016,7:13233.

89Staal R G,Mosharov EV,Sulzer D.Dopamine neurons release transmitter via a flickering fusion pore.Nature Neuroscience, 2004, 7(4): 341-346.

90 LiY T, Zhang S H, Wang L,et al.Nanoelectrode for amperometric monitoring of individual vesicular exocytosis inside single synapses.Angewandte Chemie International Edition,2014, 53(46): 12456-12460.

91 Liu JT,Hu L S,Liu YL,et al. Real-time monitoring of auxin vesicular exocytotic efflux from single plant protoplasts by amperometry at microelectrodes decorated with nanowires. Angewandte Chemie International Edition,2014,53(10):2643- 2647.

92 Li Y T, Zhang S H,Wang X Y,et al. Real-time monitoring of discrete synaptic release events and excitatory potentials within self-reconstructed neuromuscular junctions.Angewandte Chemie International Edition,2015,54(32): 9313-9318.

93 Cheng W, Compton R G. Investigation of single-drugencapsulating liposomes using the nano-impact method. Angewandte Chemie International Edition,2014,53(50):13928- 13930.

94 Najafinobar N,Lovric J,Majdi S,etal.Excited fluorophores enhance the opening of vesicles at electrode surfaces in vesicle electrochemical cytometry.Angewandte Chemie International Edition,2016, 55(48): 15081-15085.

95 Cans A S,Wittenberg N,Eves D,et al.Amperometric detection of exocytosis in an artificial synapse.Analytical Chemistry,2003, 75(16): 4168-4175.

96 Anderson B B,Chen G Y,Gutman D A,et al.Demonstration of two distributions of vesicle radius in the dopamine neuron of Planorbis corneus from electrochemical data.Journal of Neuroscience Methods,1999,88(2): 153-161.

97Anderson B B, Zerby S E,Ewing AG.Calculation of transmitter concentration in individual PC12 cell vesicles with electrochemical data and a distribution of vesicle size obtained by electron microscopy. Journal of Neuroscience Methods,1999,88(2):163-170.

98Wightman R M,Jankowski JA,Kennedy R T,et al. Temporally resolved catecholamine spikes correspond to sigle vesicle release from individual chromaffin cells.PNAS,1991, 88(23):10754-

10758.

99 Heinze J.Ultramicroelectrodes in electrochemistry.Angewandte Chemie International Edition, 1993,32(9):1268-1288.

100 Mosharov E V, Sulzer D.Analysis of exocytotic events recorded by amperometry. Nature Methods,2005,2(9): 651-658.

101 Majdi S,Berglund E C,Dunevall J,et al.Electrochemical measurements of optogenetically stimulated quantal amine release from single nerve cell varicosities in Drosophila larvae. Angewandte Chemie International Edition,2015,127(46):13609- 13612.

102Li X C,Majdi S,Dunevall J,et al.Quantitative measurement of transmitters in individual vesicles in the cytoplasm of single cells with nanotip electrodes.Angewandte Chemie International Edition,2015,54(41): 11978-11982.

103 Jena B K,Percival S J, Zhang B.Au disk nanoelectrode by electrochemical deposition in a nanopore.Analytical Chemistry, 2010,82(15): 6737-6743.

104 Li Y X,Bergman D, Zhang B.Preparation and electrochemical response of 1-3 nm Pt disk electrodes.Analytical Chemistry,2009, 81(13): 5496-5502.

105Liu Y Z,Li M N,Zhang F,et al. Development of Au disk nanoelectrode down to $3 \ \mathrm { n m }$ in radius for detection of dopamine release froma single cell.Analytical Chemistry,2015,87(11): 5531-5538.

106 Gholizadeh A, Shahrokhian S,Iraji zad A,et al.Fabrication of sensitive glutamate biosensor based on vertically aligned CNT nanoelectrode array and investigating the effectof CNTs density on the electrode performance.Analytical Chemistry,2012,84(14): 5932-5938.

107Lu N, Gao AR,Dai PF,et al. The application of silicon nanowire field-effect transistor-based biosensors in molecular diagnosis. Chinese Journal, 2015,61(4-5): 442-452.

108 Zhu D,Zuo XL,Fan C H.Fabrication of nanometer-sized gold flower microelectrodes for electrochemical biosensing applications.Scientia Sinica,2015,45(11):1214-1219.

23(1):196-200.

109 Bergner S,Palatzky P,Wegener J,et al. High-resolution imaging of nanostructured $\mathrm { S i } / \mathrm { S i O } _ { 2 }$ substrates and cell monolayers using scanning electrochemical microscopy.Electroanalysis,2011,

110 Koch JA,Baur MB,Woodall E L,et al.Alternating current scanning electrochemical microscopy with simultaneous fast-scan cyclic voltammetry.Analytical Chemistry,2012, 84(21): 9537-9543.

# Electrochemical Sensing of Neurotransmitters with High Temporal and Spatial Resolution

Zhang Yueyue1,2 Zuo Xiaolei' Fan Chunhai'

(1 Shanghai Institute of Applied Physics, Chinese Academy of Sciences, Shanghai 201800, China;

2University of Chinese Academy of Sciences,Beijing 1ooo49,China )

AbstractCurentlyaltimoirteeleaseofeurotrasmitersfomlivigcellsitightmpralandspatialroutiois challenging.Inrecntyearsuantitativeanalysisofneurotransmiteeleasingasbnachieedbydevelopingdiferentelectroical monitoringtechiqes,andcelleleasepatesavenivestigatedInaddition,oitoringithghresoutionandssitiyane achievedbymodifyingtheelectrodesurfaceorregulatingtheelectrodedimensions.Thecombiningofdiferentmonitoringtechniquescan furthermproveteotogapabiltispapresteecansofectrohialetectioofurotransmttelopt of microelectrodeandnanoelectrodeforeurotransmiterdetection,thecoupligofelectrochmicaltechologyadimagingtecologto realizethehightemporalandspatialresolutionTepaperalsoprovidessomeoutloksinthefuturedirectionBasedonthesereviewsand futureperspecties,takingteadvantagesofdierentmonitoringtchqus,tepaperproposstheouplingamongtenanolectrodeand imagingtechologysellsotrotogtchqesgateatlyevatigteapabilityofanoelectrodeineuote monitoring.

Keywords neurotransmiter,high temporal and spatial resolution,vesicle release,nanoelectrode,electrochemical张月月中科院上海应用物理所物理生物学研究室博士研究生，主要研究方向为纳米电极的制备、细胞间神经递质的实时监测。E-mail: acszyue@163.com

ZhangYueyueP.tudentativisionofPhysicalBiologyShanghai IstituteofAppledPhysics(INAP),Chnesecadeyofiece (CAS).Herresearchinterestscoverthepreparationofnanoelectrodeandteirapplications ineal-timemoitoringofneurotrasiters. E-mail: acszyue@163.com

樊春海中科院上海应用物理所研究员、博士生导师，物理生物学研究室和上海光源国家科学中心（筹）生物成像中心主任。主要研究方向为生物传感与成像、DNA纳米技术与DNA计算和生物光子学。E-mail:fchh@sinap.ac.cn

FanChunhaiProfesorandChiefoftheDivisionofhysicalBiologyandtheBioimagingCenteratShanghaiInstituteofApledPhysics (SINAP),Cdec(CA).ssosateeioCdterals&tefdtiad memberofseveralinteationaljouals.Hissearchfocusesonbosesorsandbiomaging,nanotechnologyDcomputigand biophotonics.E-mail: fchh@sinap.ac.cn