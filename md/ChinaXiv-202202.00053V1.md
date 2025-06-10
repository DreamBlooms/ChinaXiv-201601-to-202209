# 眼动操纵技术在决策研究中的应用前景：改变决策行为\*

林浇敏」李爱梅²周雅然²何军红’周 蕾¹（广东工业大学管理学院，广州510520）（暨南大学管理学院，广州510632）

摘要 眼动追踪技术因干扰性低、客观性强、获取数据丰富而准确等优点，被广泛应用于行为决策研究。通过操纵眼动过程，可使决策结果按照预期的方向改变，建立决策过程和结果的因果链，为决策的干预研究提供思路。基于外源性操纵、注视追随操纵这两类研究，介绍了行为决策领域眼动操纵的基本方法及原理、常见操纵指标、操纵效果，并分析和讨论了不同操纵类别的优缺点。在实验设计中考虑决策者策略及偏好的差异，结合计算建模等方法进一步丰富操纵指标和分析方法，并将该方法的优势拓展到其它领域是眼动操纵研究未来的重要方向。

关键词眼动操纵技术，外源性眼动操纵，注视追随操纵，决策偏好，因果链

# 1引言

行为决策研究关注人们如何在不同的备择选项中做出选择(Edwards,1954)，其研究范围涉及日常生活、管理和经济行为：是否接种疫苗？是否为了可持续发展而减少过度开发？选择什么类型的投资产品？20世纪50年代至今，行为决策研究蓬勃发展(Weber＆Johnson,2009)，在此期间，研究焦点从“做出何种选择"逐渐过渡为"如何进行选择”。相应地，研究方法也从基于决策结果(outcome-based)的范式逐渐发展至基于决策过程(process-based)的范式(Schulte-Mecklenbeck et al.,2017)。前者一般通过操纵刺激的属性并建立相应的数学模型，从而推测最终的选择结果；与基于结果的研究范式不同，基于过程的研究范式关注对决策过程的解析，从而实现对决策背后内在认知过程的直接推断(Schulte-Mecklenbeck et al,2011)。近年来，基于决策过程的研究深入开展，作为一种基于移动的过程测量技术(movement-based measures)，眼动追踪技术(eye-tracking technology)凭借干扰性低、客观性强、获取数据丰富而准确、适用范围广、成本低、便携等显著优势(Glockner＆ Herbold,2011; Orquin & Loose,2013; Raptis et al.,2017)，被广泛应用于此类研究(Ballco et al., 2019;

Huddleston et al., 2018; Liu et al., 2021; Newell & Le Pelley, 2018; Uggeldahl et al., 2016)。

眼动追踪技术的基石是眼脑假设(eye-mind hypothesis)，即眼睛正在获取的信息和大脑正在加工的信息相一致，此类技术以眼动指标反应视觉信息的时空编码，可对决策过程中注意力分配和认知加工等特征进行有效测量(Schulte-Mecklenbeck et al.,2017)。在决策的眼动研究中，常以注视时长(fixation duration)、注视点数量(fixation count)反映决策者对信息加工的难度和深度(Horstmann et al.,2009; Su et al.,2013)，检验决策的加工特征，如检验风险决策是否包含"加权求和"(Suetal.,2013)，或跨期决策是否包含“折扣计算"(张阳阳,2016)等补偿性的加工特征；以眼跳(saccade)分布反映决策者如何搜索和比较决策信息(Khaw et al.,2018)，检验实验者更符合基于维度(attribute-based)还是基于选项(alternative-based)的加工特征(Glockner & Herbold,2011; Russo & Dosher,1983; Su et al.,2013)；以眼动轨迹(scanpath)反映视觉认知过程的时间顺序属性，检验决策者整体动态的眼动模式(周蕾 等,2019;Noton &Stark,1971; Zhouet al.,2016)。进一步地，为了探索决策过程和行为的关系及其表现，可通过计算建模等方式，用眼动模式预测行为。例如，有研究者将注意变量引入漂移扩散模型(drift diffusion model,DDM)，建立了基于注意的漂移扩散模型(attentional drift diffusion model,aDDM)(Krajbich et al.,2010; Krajbich& Range,2011)。该模型的核心假设是，决策由随机的证据累积过程驱动，而注意可以通过向所注视的选项引入临时的漂移偏差影响该过程，即注意的偏差将导致决策偏差。通过眼动追踪研究，该模型被证明能准确预测注视过程，并可定性地解释注视模式和决策行为之间的关系。又如，Chuk 等人(2020)基于隐马尔可夫模型(hidden Markov models,HMM)，提出了切换隐马尔可夫模型(switching hidden Markovmodels,SHMM)，并将其与眼动数据结合，用于分析涉及认知状态变化任务中的眼动模式，对实验者认知行为的差异进行定量测量。因此，将眼动数据所揭示的注意偏好纳入计算建模，可以从认知计算(cognitive computation)的层面进一步解释过程如何对决策结果产生作用。

过去十年间，国内外已有综述总结了眼动技术为解析决策过程和检验决策理论做出的特殊贡献(黄龙 等,2020;魏子晗,李兴珊,2015;Orquin&Lo0se,2013)。近年来，随着眼动操纵(gaze manipulation)方法的成熟，眼动技术为进一步探索决策过程与结果的因果关系及改变决策行为提供了途径。其核心思想是通过外源性操纵(exogenous manipulation)或注视追随(gaze-contingent)操纵等方式操纵决策过程，使得决策结果按照预期的方向改变。眼动过程的实时性使其在操纵研究中具有显著的优势：一方面，可以直接依据对眼动过程特征的分析明确所需操纵的关键过程；另一方面，借助眼动追踪监控过程，可以确保操纵的准确性和有效性。此类研究逐渐兴起，为建立决策过程和行为结果的关联(link)提供了新的证据支持(Fisher,2021; Liu et al.,2021; Shimojo et al.,2003; Sui et al.,2020)，并且从信息加工视角,为决策的干预措施提供了思路。本文基于不同的行为决策领域，梳理了眼动操纵研究的基本原理、常见操纵指标、操纵效果，并分析和讨论了不同操纵类别的优缺点，揭示了眼动操纵研究在决策领域的重要理论和现实意义，最后从实验范式改进、技术发展和应用层面探讨了眼动操纵研究未来的重要方向。

在行为决策领域，眼动操纵的研究主要可分为两大类：(1)外源性操纵研究，通过借助外部提示线索、改变选项的物理特征等方法来操纵眼动，影响决策者的决策结果(Shimojoetal.,2003;Vriens etal.,2020)；(2)注视追随操纵研究，通过监控实验者在决策时自主的眼动过程，当其达到某个阈值时，中断选项呈现从而实现眼动操纵，改变实验者的决策结果(Fisher,2021;Liu et al.,2020; Newell&Le Pelley,2018)。操纵研究类别、具体方法、原理及主要的操纵指标和研究领域等总结见表一。

表一操纵研究方法总结  

<html><body><table><tr><td>操纵类别</td><td>具体方法</td><td>原理</td><td>主要操纵的 眼动指标</td><td>主要研究 领域</td><td>参考文献</td></tr><tr><td rowspan="4">外源性眼动 操纵</td><td>外部线索</td><td>通过运用外部线索 引导实验者注视目 标选项</td><td>注视点数量</td><td>消费决策</td><td>Vriens et al.,2020</td></tr><tr><td>物理特征</td><td>通过改变选项的物 理属性：如显著性 （亮度、不透明 度、颜色等）、标 签、尺寸等，引导 实验者注视目标选</td><td>注视点数量</td><td>消费决策</td><td>Peschel et al.,2019; Zuschke,2020</td></tr><tr><td>呈现时长</td><td>项 通过延长选项的呈 现时间引导实验者</td><td>注视时长</td><td>认知决策 消费决策</td><td>Shimojo et al.,2003; Nittono&Wada,2009 Armel et al., 2008</td></tr><tr><td></td><td>注视目标选项</td><td></td><td>跨期决策</td><td>Fisher,2021</td></tr><tr><td rowspan="4">注视追随 操纵</td><td>末次注视</td><td>当实验者的末次注</td><td></td><td>消费决策</td><td>Liu et al., 2020</td></tr><tr><td rowspan="3"></td><td>视位于目标选项 时，中断眼动过程</td><td>末次注视点</td><td>认知决策</td><td>Morii& Sakagami,2015</td></tr><tr><td></td><td></td><td>道德决策 跨期决策</td><td>Ghaffari&Fiedler,2018 Fisher,2021;</td></tr><tr><td>当实验者注视选项 (维度)达到一定时</td><td></td><td></td><td>Liu et al., 2021 Sui et al., 2020</td></tr><tr><td colspan="2">注视时长 程</td><td>长时，中断眼动过</td><td>注视时长</td><td>风险决策 认知决策</td><td>元立东 等,2021; Newell&Le Pelley,2018;</td></tr></table></body></html>

# 2外源性眼动操纵研究

外源性眼动操纵研究可通过设置外部线索，改变选项的物理特征(如显著性(saliency)、标签、尺寸(size)等)，或设置选项的呈现时间等方法，引导决策者更多地注视目标选项或特定维度，使决策结果按预期方向改变(Shimojo et al.,2003; Vriens et al.,2020)。该技术可操纵的眼动指标较丰富，包括注视点数量、注视时长等。

# 2.1基于外部线索

常见的外源性眼动操纵研究可利用外部线索引导决策者的注意指向，并改变决策偏好。具体而言，研究者可随机设定目标选项，通过外部线索指向目标选项引导实验者对它更多的关注，从而进行眼动操纵，最终导致实验者更多地选择目标选项。此类研究多以注视点数量等为操纵指标。例如，在一项食物选择的研究中，实验者在两种喜爱度相似的零食间做选择时，屏幕上首先呈现不同的外部提示线索：一个指向右侧或左侧的箭头(实验组)，或者同时呈现两个箭头分别指向左侧和右侧(控制组)，随即线索消失，屏幕的左右两侧分别呈现两种食物，实验者需要在两者中选出喜欢的一种。结果显示实验者对线索提示的目标选项的注视点更多，并更偏好该选项(Vriens et al.,2020)。

# 2.2基于选项的物理特征

鉴于刺激驱动的注意(stimulus-driven attention)可改变决策者的选择结果(Milosavljevic etal.,2012;Orquin&Loose,2013)，因此，除了运用外部提示线索，以自上而下(top-down)的视角进行眼动操纵，研究者也可通过直接改变选项的物理特征，以自下而上(bottom-up)的视角来进行外源性眼动操纵。这类研究的原理是通过改变目标选项的物理特征引导实验者对目标选项的注视来进行眼动操纵，最终使得他们更多地选择目标选项。常用的方法包括但不限于：(1)突出选项的显著性，如提高亮度、降低透明度(Milosavljevic et al.,2012;Zuschke,2020)、设置突出的颜色(Kunar et al.,2017)，(2)增加标签(Orquin et al.,2018; Peschelet al.,2019)，(3)放大选项的尺寸(Zuschke,2020)。此类研究多以注视点数量等为操纵指标。例如，Zuschke(2020)要求实验者在不同的巧克力中选出他们喜欢的类型，实验通过控制巧克力包装颜色的透明度来对实验者进行眼动操纵。结果显示，巧克力包装颜色的透明度越低，越能吸引实验者注视，并使其偏向选择包装透明度更低的巧克力。此外，在改变产品尺寸大小来操纵眼动的实验中，他将部分巧克力的尺寸放大了 $20 \%$ ，要求实验者选出喜欢的巧克力类型。结果显示，尺寸较大的巧克力更能吸引实验者的注视，使实验者更偏向选择它们。又如，在 Peschel 等人(2019)的研究中，实验者需要在不同的巧克力中选择喜欢的类型。巧克力的外包装上贴有大小不同的"有机"符号标签，实验通过控制标签的大小引导实验者的注视和选择。结果显示，印有越大标签的巧克力越能吸引实验者注视，并使实验者更偏好选择它们。而在他们控制标签的大小，对标签颜色的亮度进行调整的实验中发现，在标签尺寸较大的情况下，实验者注视标签亮度更大的巧克力的次数更多，并更偏好选择它们。综上所述，基于选项的物理特征进行眼动操纵的研究常见于消费决策领域，其结果揭示了如何通过改变选项的物理特征来引导个体的眼动过程，从而进一步影响其决策。这类研究可为广告设计、产品包装、货架摆放等提供有效思路。

# 2.3基于强制暴露

另一种较为常见的通过改变选项特征来进行眼动操纵的方法叫做强制暴露法(forced-exposure)，即延长目标选项的呈现时间来引导实验者的注视，以此来进行眼动操纵，并最终使实验者的选择偏向预定目标。此类研究多以注视时长为操纵指标。例如，Shimojo 等人(2003)在一项判断面孔吸引力的研究中，通过操纵目标面孔的暴露时间，即目标面孔呈现的时间(900毫秒)比非目标面孔(300毫秒)更长，发现实验者更倾向认为目标面孔更有吸引力。类似地，Nittono 和 Wada(2009)采用抽象的图形为实验材料，要求实验者在两张图片中选出更有吸引力的图片，实验操纵目标选项与非目标选项的呈现时长分别也是900毫秒和300毫秒，实验结果发现实验者选择目标选项的概率高于选项被随机选择的概率 $( 5 0 \% )$ 。当人们对选项没有消极情绪时，强制暴露法可以促进人们对目标选项的积极评价或喜爱，然而，当人们面临能引起消极情绪的选项时，强制暴露法的作用却相反。例如，Armel等人(2008)的研究要求实验者在喜爱或厌恶的食物中分别进行选择，结果显示，当运用强制暴露法操纵的目标选项是实验者喜爱的食物时，实验者更偏好选择目标选项；然而，当操纵的目标选项是实验者厌恶的食物时，目标选项被选择的概率则下降了 $7 \%$ 。除了消费决策研究，近来，跨期决策研究也使用强制暴露法，通过操纵选项不同维度的呈现时长来改变实验者的选择偏好：当实验者在近期获得一笔较少的钱("小而近”，SS选项)和远期获得一笔较多的钱("大而远”，LL 选项)中做选择时，屏幕中交替呈现选项的金钱维度和时间维度，维度呈现一次的时长分别为2秒、0.5秒，在交替呈现至少5秒后，实验者需要做出选择。当目标维度是金钱维度时，结果发现这种操纵可增加人们对"大而远"选项的选择比例(Fisher,2021)。可见，强制暴露法是一种较为有效的外源性眼动操纵方法，在认知决策、消费决策和跨期决策等多个领域都得到了有效应用。

综上，外源性眼动操纵方法多样，研究者可以利用线索指向、增强选项的物理特征、或延长选项呈现时长等方法操纵眼动并引导实验者的选择偏好。此类研究的操作方法简单、便捷，被广泛地运用于决策研究。从应用层面来看，通过操纵外源性刺激可以影响实验者在自然状态下的选择偏好这一结论为产品设计提供了思路。例如，根据操纵选项物理特征的研究结果，将食品包装颜色换成鲜艳的颜色、加大包装上的标签尺寸等可以增加消费者对商品的注视，提升商品销量。

然而外源性眼动操纵研究存在一些不足。首先，虽然运用该方法操纵眼动可以强化实验者对目标选项的偏好，但在其过程中容易出现需求效应(demand effect,Newell&Le Pelley,2018)，实验者可能会因为目标选项的呈现时间较长或物理特征更明显而猜到研究目的，即引导他们选择该目标选项。因此，外源性眼动操纵可能会使实验者有意识地根据实验需求选择目标选项，从而影响结果的可信度。其次，并不是操纵所有在理论上与决策过程密切相关的外源性刺激都能影响决策结果。如根据注视层叠效应(gaze cascade effect)和漂移扩散模型的假设，首次注视点(first fixation)会对选择结果产生影响，然而通过外源性眼动操纵实验并没有发现操纵该指标能改变决策结果(van der Laan et al.,2015)。可见，虽然外源性眼动操纵技术被广泛使用，但由于易受到需求效应等干扰，其可靠性和可信度及应用范围会受到一定程度影响。

# 3注视追随操纵研究

注视追随操纵研究采用不易为实验者所察觉的基于注视的操纵方式，可以降低需求效应对实验结果的影响，在一定程度上克服外源性眼动操纵研究的部分不足。此类研究的基本思路是事先随机设定目标选项，用眼动仪实时监控实验者自主的眼动模式，当他的眼动模式达到触发条件时，实验刺激消失并呈现选择界面，要求实验者做出选择，由此影响实验者的行为(Newell&Le Pelley,2018;Pärnamets etal.,2015)。该类研究常操纵的眼动指标包括末次注视点(last fixation)、注视时长等(Fisher, 2021; Liu et al.,2020; Liu et al.,2021)，其中,通过控制注视时长操纵眼动在实验中最为常见。目前，该技术被广泛地运用于消费决策、跨期决策、风险决策、道德决策与认知决策等领域，来探索各决策领域内注视与决策结果之间的因果关系。

# 3.1基于末次注视点

根据操纵的指标来区分，首先，注视追随操纵研究可操纵末次注视点来改变选择偏好。具体而言，研究者设定目标选项，追踪决策者自主的眼动过程；当决策者对两个选项的注视都达到一定时间后，再次注视目标选项时，中断其眼动过程来进行操纵，这样使得决策者末次注视点落在目标选项上；最终，实验者可能更倾向于选择目标选项。这种方法已在消费和道德决策中被有效运用。在消费决策领域，研究者将两种实验者喜爱程度相似的食物分别呈现在屏幕左右两侧，并追踪实验者的眼动过程，当眼动仪监测到实验者对两种食物的注视时长均至少达到 500 毫秒后，实验者再注视随机设置的目标食物达到 50毫秒时，选项停止呈现，实验者在此时选出更喜爱的食物。结果显示，实验者选择目标食物的比例大于 $50 \%$ (Liu et al.,2020)，说明操纵末次注视点可以影响决策者的选择偏好。在道德决策领域的研究中，研究者向实验者提出一些道德问题，选项呈现在屏幕的左右两侧。当眼动仪监测到实验者注视选项达到一定时间(目标选项750毫秒，非目标选项 250毫秒)后，实验者再次注视目标选项时，选项停止呈现，实验者需在此时选出更喜欢的选项。结果显示，实验者更偏向于选择末次注视到的选项(Ghaffari&Fiedler,2018)。然而，在认知决策领域，基于末次注视点操纵眼动并没有达到预期效果。例如，Morii 和 Sakagami(2015)以抽象图片为实验材料，将图片分别呈现在屏幕左右两侧，当眼动仪监测到实验者注视两个选项后，再次注视目标选项时，选项停止呈现，实验者需要在此时选出更有吸引力的图片。然而，实验结果表明实验者的选择并没有偏向预定的目标选项。

我们认为，基于末次注视点的眼动操纵研究效果在不同研究中的差异可能取决于决策任务特征。与认知决策相比，在消费决策和道德决策的实验中，实验者的选择结果会对他带来更大影响：在消费决策中，实验者被要求吃掉他们选择的食物；在道德决策中，实验者可能会考虑研究者对他的看法，受到社会称许性(social desirability)的影响。因此，他们在决策中更可能集中注意力，进行审慎的思考，当眼动操纵中断其思考过程时，末次注视到的选项可能会具有更强的近因效应(recency effect)(Atkinson & Shiffrin,1968;Cowan,1993),进而使操纵达到预期效果。

# 3.2基于注视时长

除了基于末次注视点，在注视追随操纵研究中，基于注视时长的眼动操纵方法也较为常见。这类研究的基本原理是，事先设定目标和非目标选项的注视时长(目标选项比非目标选项时长显著更长)，追踪决策者的自主眼动过程，当他对目标和非目标选项的注视时长都达到设定阈值时，停止呈现选项，提示决策者做出选择。该操纵方法的对象主要可以分为两类，即选项和维度的注视时长。在基于选项的操纵研究中，研究者随机选取目标选项，当实验者对目标与非目标选项的注视时长都达到阈值后触发决策提示。此类操纵方法在不同类别的决策研究中被证实有效，即通过操纵对选项的注视时长，可使目标选项被选择的比例上升。而在基于维度的操纵研究中，研究者随机选取选项的某一维度作为目标维度，在实验者注视目标与非目标维度都达到一定时间阈值后触发决策提示。这类研究结果表明通过操纵对维度的注视时长，可以使实验者更多地选择目标维度占优的选项。

在跨期决策的研究中，Fisher(2021)基于选项操纵注视时长，实验以随机选择的 SS 或LL 选项为目标选项，一旦实验者注视选项达到一定时长(目标选项1.2秒，非目标选项0.3秒)，该选项就会从屏幕上消失，当两个选项都消失后，实验者做出决策。结果显示当LL选项是目标选项时，相比其他情况，实验者对LL 选项的选择比例升高。与之类似，Liu 等人(2021)也基于选项操纵实验者注视时长。在实验者注视目标选项至少 2000 毫秒、每个兴趣区至少50毫秒后，选项消失，实验者做出决策。结果显示通过操纵对目标选项的注视时长能使实验者偏向选择目标选项。在基于维度的操纵研究中，当眼动仪监测到实验者注视目标维度达到 2000 毫秒，并注视每个兴趣区至少 50 毫秒后，选项就会从屏幕上消失，实验者做出决策。结果发现，通过操纵对目标维度的注视时长，使得目标维度占优的选项被选择的概率超过 $50 \%$ 。以上研究发现，操纵实验者对目标维度的注视时长，可以使得实验者偏向在该维度占优的选项。在风险决策领域，Sui 等人(2020)也分别基于选项和维度进行眼动操纵。在该研究中，实验者在两个期望值之差不超过10 的风险选项中做选择，当眼动仪监测到实验者注视目标选项达 1500 毫秒，注视每个兴趣区达 100 毫秒(研究一)，或注视目标维度达 1000 毫秒，注视每个兴趣区达 100 毫秒(研究二)时，选项消失，实验者做出选择。实验结果表明在风险决策领域，增加实验者对目标选项或维度的注视时长，均可以使其选择偏好随预期方向改变。

除此以外，基于选项的眼动操纵技术也被应用于基础的认知决策和更为复杂的道德决策研究。在认知决策领域，Tavares 等人(2017)要求实验者在两条倾斜角度不同的线条中选出一条与他们在实验前看到的线段的倾斜角度接近的线条，结果发现，操纵目标选项的注视时长将有效引导实验者选择它。类似地，Newell和Le Pelley(2018)及元立东等人(2021)在图片识别任务中也重复出了Tavares 等人(2017)的实验结果。此外，在道德决策这类较复杂的决策中，基于选项的眼动操纵方法仍能有效影响决策偏好。Pämamets 等人(2015)的实验要求实验者在诸如"谋杀有时是正当的"和"谋杀任何时候都不正当"的两难选项中选出他们认为在道德上正确的选项，目标选项由研究者随机确定。当实验者注视目标选项 750 毫秒、非目标选项250 毫秒后，选项停止呈现，实验者做出选择。结果显示实验者更偏向选择目标选项，该结果揭示了注视时长和道德决策之间的因果关系。可见，基于注视时长的眼动操纵在多个不同的决策领域中被证实有效，然而此类方法易出现超时试次，影响实验效率。

总的来说，因为注视追随操纵研究不易被实验者所觉察，一定程度上克服了外源性操纵带来的需求效应的影响。注视追随操纵研究可基于选项或维度进行眼动操纵，在基础的认知决策，和较复杂的风险决策、跨期决策、消费决策、道德决策等领域得到广泛运用。这一系列研究结果不仅对建立决策过程和结果的因果链具有重要的理论意义，在现实中，对改善个体日常生活中做出的各类决策也具有重要启示。例如，在日常的跨期决策中，增加长远选项及其占优维度的曝光或可有效降低个体在决策中的冲动性程度，避免短视行为。

然而，注视追随操纵研究存在一定不足。例如，在运用该方法时，由于选项信息的呈现受实验者实际注视的影响，所以在某些试次中，实验者眼动条件可能无法达到触发决策提示的条件：在选项的最长呈现时间内，对选项注视时长无法达到设定阈值，导致试次失效，进而影响实验效率。在本文所综述的文章中，无效试次数占总试次数的比例范围为$3 \% { \sim } 2 5 \%$ ，然而，几乎没有研究解释试次之间的这种眼动过程的变异。在上述研究中，Liu等人(2020)的研究超时试次占比最小，而该研究所采用的实验材料事先经过了偏好测试，在后续实验中，决策者在无显著偏好差异的选项中做选择。因此，我们认为在注视追随操纵研究中出现较多超时试次的原因之一可能是大部分研究没有考虑决策者的实际偏好及个体差异，采用了统一的刺激材料，使得决策者对选项先验的偏好差异影响了操纵的效果。其次，由于注视追随操纵研究在实验者注视的过程中干预眼动，使得实验者在非自然状态下做出选择，与人们日常做出决策的状态不相符，因此和外源性操纵研究相比，这类研究结果在应用推广上具有一定局限。

# 4总结与展望

行为决策领域早期的研究仅关注输入和输出变量之间的关系，忽略了“人们究竟如何做出决策"这一谜题。眼动追踪等过程技术的发展，打开了决策认知的"黑箱”，为解析决策过程和检验决策理论做出了特殊贡献。进一步地，眼动操纵技术通过外源性操纵或注视追随操纵等研究方法操纵眼动过程，系统化地改变实验者的决策行为偏好，建立了决策过程和结果的因果链。两类操纵研究根本目的一致，但它们具有不同的特征，因而适用于不同的研究范围，未来研究者应根据实际的研究设计选择合适的方法。

外源性眼动操纵通过改变选项的呈现方式或物理属性来操纵眼动，因此这类操纵可在决策过程的初始阶段就有目的性地将实验者的注视引向目标选项，从而影响决策的眼动过程及其结果。外源性操纵研究方法较为多样，可操纵的眼动指标也较多，但在实验设计中需改变选项的物理特征或呈现时长，易出现需求效应。此类操纵研究选项框架及设计简单、实验过程易推广，且实验结果对日常实践具有重要借鉴意义，因此，在消费行为学等领域的研究中，可以运用外源性眼动操纵技术探索何种营销手段能有效促进顾客购买行为，提

高广告设计的有效性。

注视追随操纵研究不改变选项的属性，而是通过直接干预决策的眼动过程影响决策结果，这类操纵更多地作用于决策的中间过程。此类研究无须改变选项的呈现方式或物理属性，实验者不易识别出目标选项，猜出研究目的。然而，该研究操纵方法较为单一，且由于选项的呈现是根据实验者实际注视而定，实验易出现超时试次，导致试次失效。注视追随操纵研究可基于过程进行决策模型的检验和比较，如：在跨期决策中，经典的折扣模型，如折扣效用模型(discounted-utility model,DU,Samuelson,1937)。假设人们有更多基于选项加工的眼动过程，而非折扣模型，如权衡模型(trade-off model,Scholten&Read,2010)则认为人们有更多基于维度加工的眼动过程。跨期决策的研究通过基于维度的眼动操纵有效改变了决策偏好，侧面支持了非折扣模型的假设。此外，通过操纵注视时长改变选择偏好的研究也为 aDDM这类注意力模型"选项的价值会因过多的注意而被高估"的假设提供了直接的实验证据。

眼动操纵研究具有重要的意义：在理论层面，通过操纵不同决策理论所假设的眼动过程，探索过程与结果之间的关联，可在过程层面进行决策模型的检验和比较，从而基于决策过程对理论模型的假设提供直接的实验证据。在现实层面，操纵眼动过程以改变决策结果，可以在不改变选项价值，不违背实验者自由选择意志的前提下，使得决策行为朝着人们预期的方向改变，以信息加工为视角为改善现实中决策的质量提供思路。

正如Lahey 和Oxley(2016)所言：未来使用眼动技术进行决策研究仍具有较大潜能。眼动操纵技术可为行为决策领域的研究带来更多的新发现，推动决策理论的发展和应用。我们认为，今后决策领域的眼动操纵研究需要着力于以下几个方面的探索：

第一，针对现有眼动操纵研究存在的一些局限，未来的研究或可从以下几个方面改进实验范式。首先，现有的操纵研究未考虑到实验者采用不同的决策策略对实验结果带来的影响。根据 Simon(1982)提出的有限理性(bounded rationality)假设，生物体需要根据决策环境的结构调整策略，以应对环境的挑战(Gigerenzer＆Gaissmaier,2011)。对于眼动操纵研究而言，在风险和跨期决策的研究中，基于维度和选项的操纵均能有效改变实验者的选择偏好，从侧面证实了实验者可能在决策过程中采用混合的加工策略(Sui etal.,2020)。在不同的实验参数条件下，实验者可能采用不同的决策策略，若采用单一的操纵方法而不对策略加以区分，则可能导致部分试次失效。其次，绝大部分眼动操纵研究暗含的假设是实验者对选项具有近似相等的偏好，因此在大多数研究中，实验者采用统一的、自行设定的刺激材料，这种做法忽略了选择偏好的个体差异。实际上，如果实验者对实验中所设定选项的喜好存在先验的差异，则可能对某个选择存在注意偏差，这样会使得自主决策的眼动过程难以达到操纵所要触发的条件，导致试次失效。针对上述问题，未来的研究应充分考虑决策中实验者所采用的决策策略和选择偏好的差异，例如，鉴于决策者所采用的不同策略可表征为不同的眼动模式(Horstmann et al.,2009; Zhou et al.,2016; Zhou et al.,2018)，研究者可在正式实验前通过测试了解实验者在不同参数条件下的决策策略和偏好，针对每个实验者设置特定的实验材料(Zhou,Liang,etal.,2019)，以消除个体差异和实验参数特异性对眼动操纵效果带来的影响。

第二，针对目前眼动操纵研究所操纵的眼动指标较为单一问题，研究者们需进一步发展和丰富眼动操纵的指标和分析方法。我们认为，结合计算建模和机器学习(machineleaming)技术，可为确立眼动操纵的关键指标提供途径。计算建模优于一般的分析方法，可以建立实验范式中每个试次隐藏的决策变量与实际决策偏好间的关系，故而可以在动态层面建立决策过程模型(Scheibehenne&Pachur,2015)。因此，在决策模型中增加眼动过程数据作为重要的预测变量，可提高模型的解释力(Zhou,Zhang,etal.,2019)，并以此建立综合结果和过程数据的决策模型。对眼动操纵研究而言，与计算建模技术相结合，可有效地确立对决策结果解释力最高的关键性眼动指标，从而提高眼动操纵研究的有效性。此外，机器学习也或可为眼动操纵研究提供新的思路。机器学习技术可对给定的大数据进行预测，因此基于机器学习算法建立决策模型具有广阔前景(Bhatia& He,2021)。随着用户的注视数据集不断增长，机器学习与眼动追踪研究的结合将不断得到改进(Krol&Krol,2017;Shojaeizadehet al.,2019)。已有研究结合机器学习和眼动追踪技术，用眼动指标预测行为，例如 Eivaz 和 Bednarik(2011)将基于眼动数据的分类方法用于预测实验者的问题解决。未来操纵研究可通过机器学习方法，从海量数据中高效去除冗余，精确地确立有效的眼动操纵指标。

第三，从应用层面来看，眼动操纵研究也可拓展到诸如人力资源管理领域的决策问题。受新冠肺炎疫情影响，许多行业都放弃了传统的工作模式，把目光转到了线上(Cleland et al,2020;Dannenberg et al.,2020)。受到许多客观因素的限制，在企业线上招聘过程中，求职者与面试官的交流效果往往不如线下面试(Jones＆Abdelfattah,2020)。其中，非言语信息(nonverbal information)或对线上面试结果带来较大影响(张伟,徐建平,2016)。若将眼动操纵引入到面试研究中，一方面，或可通过外源性眼动操纵技术探讨非言语因素(如：衣着、灯光等)对面试者评分的影响程度，进而为提升线上面试效果提供建议。另一方面，或可加入相关调节变量(如：时间压力、实验者情绪、认知负荷等)来探究此类因素对面试效果的影响。

一项消费决策的研究发现，在认知负荷(cognitive load)和需要快速决策的情况下，提高目标食物的亮度能促使实验者选择它(Milosavljevic et al.,2012)。据此，眼动操纵研究也可用于探讨在时间压力等因素的作用下，如何通过外源性线索提升面试效果。

# 参考文献

黄龙，徐富明，胡笑羽.(2020).眼动轨迹匹配法：一种研究决策过程的新方法．心理科学进展,28(9),1454- 1461.   
元立东,李雨桐,隋雪.(2021).注视反映及影响决策偏好的眼动研究.心理科学,44(4),786-792.   
魏子晗,李兴珊.(2015).决策过程的追踪：基于眼动的证据.心理科学进展,23(12),2029-2041.   
张伟，徐建平.(2016).应聘者非言语信息对面试官评分的影响：解释、测量和控制．心理科学进展,24(8), 1319-1328.   
张阳阳.(2016).跨期决策是否基于"计算"：来自过程检验的证据(博士学位论文).中国科学院大学,北京.   
周蕾,李爱梅,张磊,李纾,梁竹苑.(2019).风险决策和跨期决策的过程比较：以确定效应和即刻效应为例.心 理学报,51(3),337-352.   
Armel,K. C., Beaumel,A.,&Rangel,A. (2oo8). Biasing simple choices by manipulating relative visual atention Judgment and Decision Making,3(5),396-403.   
Atkinson, R. C.,& Shifrin, R. M. (1968). Human memory: A proposed system and its control processs.In K. W. Spence & J.T. Spence (Eds.),Psychology of learning and motivation: Advances in research and theory (Vol. 2, pp. 89-195). New York, NY: Academic Press.   
Ballco,P.,de-Magistris,T.,& Caputo,V.(2O19). Consumer preferences for nutritional claims: Anexploration of attention and choice based on an eye-tracking choice experiment. Food Research International, 116,37-48.   
Bhatia,B.S.,& He,L. (2021). Machine-generated theories of human decision-making.Science,372(6547),1150- 1151.   
Chuk,T., Chan,A.B.,Shimojo,S.,& Hsiao,J. H. (2O2O). Eye movement analysis with switching hidden Markov models.Behavior Research Methods,52(3),1026-1043.   
Cleland, J., Chu, J.,Lim,S.,Low,J.,Low-Beer,N.,& Kwek,T.K. (2020). COVID19: Designing and conducting an online mini-multiple interview (MMI) in a dynamic landscape. Medical Teacher, 42(7),776-780.   
Cowan,N. (1993). Activation,attention,and short-term memory. Memory & Cognition, 21(2),162-167.   
Dannenberg,P.,Fuchs,M., Riedler,T.,& Wiedemann, C. (2020).Digital transition by COVID-19 pandemic? The German food online retail. Tijdschrift Voor Economische En Sociale Geografie,111(3),543-560.   
Edwards,W. (1954). The theory of decision making. Psychological Bulletin, 51(4),380-417.   
Eivazi,S.,& Bednarik,R.(2011).Predicting problem-solving behavior and performance levels from visual attention data. In Y.Nakano,C. Conati & T.Bader (Eds.),Proceedings of 2nd Workshop on Eye Gaze in Intelligent Human Machine Interaction(pp. 9-16). California: ACM Press.

Fisher,G. (2O21).Intertemporal choices are causally influenced by fluctuations in visual attntion.Management Science, 67(8), 4961-4981.

Ghaffari, M.,& Fiedler, S. (2018). The power of atention: Using eye gaze to predict other-regarding and moral choices.Psychological Science,29(11),1878-1889.   
Gigerenzer, G.,& Gaissmaier, W. (2011). Heuristic decision making. Annual Review ofPsychology, 62,451-482.   
Glockner,A.,& Herbold, A. K. (2011). An eye-tracking study on information processing in risky decisions: Evidence for compensatory strategies based on automatic processs. Journal of Behavioral Decision Making, 24(1), 71-98.   
Horstmann,N.,Ahlgrimm,A.,& Glockner,A. (2o09). How distinct are intuition and deliberation? An eye-tracking analysis of instruction-induced decision modes. Judgment and Decision Making, 4(5),335-354.   
Huddleston,P. T.，Behe, B.K.，Driesener,C.,& Minahan, S.(2018). Inside-outside: Using eye-tracking to investigate search-choice processes in the retail environment. Journal of Retailing and Consumer Services, 43, 85-93.   
Jones,R.E.,& Abdelfatth,K.R.(202O). Virtual interviews in the era of COVID-19: A primer forapplicants. Journal of Surgical Education, 77(4), 733-734.   
Khaw,M. W.,Li, Z.，& Woodford, M. (2018). Temporal discounting and search habits: Evidence for a taskdependent relationship.Frontiers in Psychology,9(2102).   
Krajbich,I.,Armel, C.,&Rangel,A. (20lo). Visualfixations andthecomputationand comparison ofvalue insimple choice.Nature Neuroscience,13(10),1292-1298.   
Krajbich,I.,& Rangel,A. (2O11).Multialternativedrift-diffusion model predicts therelationship between visual fixations and choice invalue-based decisions.Proceedings of the National Academy of Sciences of the United States of America,108(33),13852-13857.   
Kr6l,M.,& Kr6l, M. (2017). A novel approach to studying strategic decisions with eye-tracking and machine learning. Judgment and Decision Making,12(6),596-609.   
Kunar,M.A., Watson,D.G.,Tsetsos,K.,& Chater,N. (2O17).The influence of atention on value integration. Attention,Perception, and Psychophysics,79(6),1615-1627.   
Lahey,J. N.,& Oxley,D. (2016). The power of eye tracking in economics experiments. American Economic Review, 106(5), 309-313.   
Liu, H.Z.,Lyu,X.K., Wei,Z.H.,Mo,W.L.,Luo,J.R.,&Su,X.Y. (2021).Exploiting the dynamics of eyegaze to bias intertemporal choice. Journal of Behavioral Decision Making, 34(3), 419-431.   
Liu,H.Z., Zhou,Y.B., Wei,Z.H.,&Jiang,C.M. (202O).The power of last fixation: Biasing simple choices by gaze-contingent manipulation. Acta Psychologica, 208,103106.   
Milosavljevic,M.,Navalpakkam, V.,Koch,C.,&Rangel,A. (2O12).Relative visual saliencydifferences induce sizable bias in consumer choice. Journal of Consumer Psychology,22(1), 67-74.   
Morii, M.,& Sakagami, T. (2015). The effect of gaze-contingent stimulus elimination on preference judgments. Frontiers in Psychology, 6(1351).   
Newell,B.R.,&Le Pelly,M.E. (2018).Perceptual but not complex moral judgmentscan be biased by exploiting the dynamics of eye-gaze. Journal of Experimental Psychology: General,147(3),409-417.   
Nitono,H.,& Wada,Y. (2o09). Gaze shifts do not affect preference judgments of graphic pattrns. Perceptual and Motor Skills,109(1),79-94.   
Noton,D.,& Stark,L. (1971). Scanpaths insaccadic eye movements while viewing and recognizing paterns. Vision Research,11(9),929-942.   
Orquin, J.L., Chrobot,N.,& Grunert, K. G. (2018). Guiding decision makers’ eye movements with (un)predictable object locations. Journal of Behavioral Decision Making,31(3),341-354.   
Orquin, J.L.,&Loose, S. M. (2013). Atention and choice: A review on eye movements in decision making. Acta Psychologica, 144(1),190-206.   
Parnamets,P.,Johansson,P.,Hall,L.,Balkenius,C.,Spivey,M.J.,&Richardson,D.C. (2015).Biasingmoral decisions by exploiting the dynamics of eye gaze. Proceedings of the National Academy of Sciences of the United States of America, 112(13),4170-4175.   
Peschel,A.O.,Orquin,J.L.,&Loose,S.M. (2o19). Increasingconsumers'atentioncaptureand food choice through bottom-up effects. Appetite, 132,1-7.   
Raptis,G.E., Katsini,C.,Belk,M.,Fidas,C.,Samaras,G.,& Avouris,N. (2o17). Using eye gaze data and visual activities to infer human cognitive styles: Method and feasibility studies. In M. Bielikova &E. Herder (Eds.), Proceedings of the 25th conference on User Modeling,Adaptation and Personalization(pp.164-173). New York, ACM Press.   
Russo,J.E,&Dosher,B.A.(1983).Strategies formultiatributebinarychoice.JournalofExperimental Psychology: Learning, Memory, and Cognition, 9(4),676-696.   
Samuelson,P.A. (1937). A note on measurement ofutility. The Review of Economic Studies, 4(2),155-161.   
Scheibehenne，B.，& Pachur，T.(2O15).Using Bayesian hierarchical parameter estimation toassess the generalizability of cognitive models of choice.Psychonomic Bulletin and Review,22(2),391-407.

Scholten,M.,&Read,D. (2010).The psychologyof intertemporal tradeoffs.Psychological Review,17(3),925- 944.

Schulte-Mecklenbeck,M.,Kuhberger,A., Gagl,B.,& Hutzler,F. (2O17). Inducing thought processes: Bringing process measures and cognitive processes closer together. Journal of Behavioral Decision Making, 30(5), 1001-1013.   
Schulte-Mecklenbeck,M., Kuhberger,A.,& Ranyard,R. (2o11).The roleof process data in the development and testing of process models of judgment and decision making. Judgment and Decision Making,6(8),733-739.   
Shimojo,S.,Simion,C.,Shimojo,E.,&Scheier,C. (2Oo3).Gaze bias bothreflects and influences preference.Nature Neuroscience, 6(12),1317-1322.   
Shojaeizadeh,M.,Djamasbi, S.,Paenroth,R. C.,& Trapp,A. C. (2019). Detecting task demand via an eye tracking machine learning system. Decision Support Systems, 116, 91-101.   
Simon,H. (1982) Models of bounded rationality: Behavioral economics and businessorganization. MITPress.   
Su, Y.,Rao,L.L., Sun, H.Y.,Du,X.L.,Li, X.S.,&Li,S. (2o13).Is making a risky choice based on a weighting and adding process? An eye-tracking investigation. Journal of Experimental Psychology: Learning Memory and Cognition,39(6),1765-1780.   
Sui,X.Y.,Liu,H. Z.,&Rao,L.L. (2O2O).The timing of gaze-contingentdecision prompts influences riskychoice. Cognition,195,104077.   
Tavares,G.,Perona,P.,& Rangel,A. (Ol7).The attentionaldrift diffusion model of simple perceptualdecisionmaking. Frontiers in Neuroscience, 11(468).   
Uggeldahl,K.,Jacobsen,C.,Lundhede,T.H.,&Olsen,S.B.(2O16).Choicecertainty indiscrete choiceexperiments: Will eye tracking provide useful measures? Journal of Choice Modelling, 20,35-48.   
van der Laan,L.N.,Hooge,I.T.C.,De Ridder,D.T.D., Viergever,.A,&Smeets,P.A.M. (2015).Do you like what you see? The role of first fixation and total fixation duration in consumer choice. Food Quality and Preference,39,46-55.   
Vriens,M., Vidden,C.,& Schomaker,J. (2O2O). What Isee is what I want: Top-down atention biasing choice behavior. Journal of Business Research,111,262-269.   
Weber,E. U.,& Johnson,E. J. (2009). Mindful judgment and decision making. Annual Review of Psychology, 60, 53-85.   
Zhou,L., Liang Z-Y.,Li S.,Zhang L. (2O19,August).Similarity in processesofrisky choice and intertemporal choice: Based on equivalence conversion. Paper presented at the meeting of Subjective Probability, Utility,

andDecisionMaking,Amsterdam,Netherlands.

Zhou L.,Zhang,L.,Su,Y.,&Liang,Z.Y.(2O19). Is zero void? Attentional mechanism of hidden-zero effct inrisky decision-making.https://doi.org/10.31234/osf.io/pmhsa   
Zhou,L., Zhang,Y. Y.,Li,S.,& Liang, Z. Y. (2018). New paradigms for the old question: Chalenging the expectation rule held by risky decision-making theories.Journal of Pacific Rim Psychology,12,e17.   
Zhou,L., Zhang, Y. Y., Wang, Z. J.,Rao,L. L., Wang, W.,Li, S.,Li, X. S.,& Liang, Z. Y. (2016). A scanpath analysis of the risky decision-making process. Journal of Behavioral Decision Making,29(2-3),169-182.   
Zuschke,N. (2O2O).The impact of task complexity and task motivation on in-store marketing efectivenes: An eye tracking analysis. Journal of Business Research, 116,337-350.

# The prospect of gaze manipulation technology in decision-making research

LINJiao-Min1,LI Ai-Mei²,ZHOU Ya-Ran²,HE Jun-Hongl, ZHOULeil ('School of Management,Guangdong University of Technology, Guangzhou 51o520,China) (School of Management,Jinan University,Guangzhou 51o632,China)

Abstract: The eye-tracking technique has been widely used in behavioural decision-making research owing to its advantages: 1) does not interfere with the decision-making process,2) collcts information objectively and 3） provides accurate and rich process data. To reveal the causality between eye movement and decision-making， gaze manipulation could be utilized to examine whether shifting visual attention can alter choice behaviour. Gaze manipulation is classified into two types: exogenous manipulation and gaze-contingent manipulation. This paper reviews studies on gaze manipulation in decision-making, introduces the basic methods and principles of gaze manipulation, and discusses the common manipulation indexes. Additionally, this paper compares the advantages and disadvantages of the two basic methods.Future research from different fields should benefit from fully considering individual preference and choice strategy differences in decision-making,and integrating gaze manipulation with computational modeling or other methods to enrich the manipulation indexes.

Key words: gaze manipulation technology, exogenous manipulation, gaze-contingent manipulation, choice preference, causal link