# ·基于用户动态信息加工的信息流广告回避机制与重定向策略

张皓」肖邦明²黄敏学(湖北工业大学经济与管理学院，武汉430068)2(华中农业大学经济管理学院，武汉 430070)(武汉大学经济与管理学院，武汉 430072)

# 摘要：

信息流广告飞速发展的同时用户广告回避愈发普遍，然而传统广告回避结论无法平移到该情境。本研究基于用户动态的信息加工视角，试图探讨(1)动态信息加工状态下(收敛式vs 发散式)产生广告屏蔽和广告跳过行为的内在机制；(2)采用归因引导重定向策略，挖掘用户屏蔽广告的"残留效应"所带来的信号价值;(3)采用广告凸显重定向策略，突破用户跳过广告的"学习效应"造成的负面影响。丰富现有理论的同时，为信息流广告的响应式优化提供理论和决策支持。

关键词：信息流广告，动态信息加工，广告回避，广告重定向分类号：B849:F713.55

# The in-feed native advertising avoidance mechanism and re-targeting strategy based on user dynamic information

# processing mode

Zhang Haol, Xiao Bangming², Huang Minxue³   
1(School of Economics and Management， Hubei University of Technology，Wuhan 430068, China)   
² (College of Economics and Management， Huazhong Agricultural University， Wuhan 430070，China) 3 (School of Economics and Management， Wuhan University， Wuhan 430072， China)

# Abstract:

As the in-feed native advertising is growing fast,ad avoidance from the users is becoming more prominent. However， traditional knowledge about ad avoidance is no longer adequate for this new context. This research，based on users’ dynamic information processing states, seeks to (1） explore the mechanisms of users' ad-skipping and ad-blocking behaviors under varied information processing modes (convergent vs. divergent)； (2) apply the re-targeting strategy of "guided attribution" to leverage the signal value brought by the "residual effect" from users’ ad blockings;(3) apply the re-targeting strategy of"prominence" to break the ad-skipping momentum caused by the "learning effect" from users’ continuous ad-skippings. While enriching extant theories, this research provides theoretical and managerial support for the responsive optimization of in-feed native advertising.

Key words:in-feed native advertising，dynamic information processing mode, advertising avoidance, advertising re-targeting

# 1问题提出

顺应移动端信息消费场景的信息流广告成为网络广告行业发展的新引擎。据统计，2021年信息流广告占比 $3 6 . 8 \%$ ，市场占比第二，预计2022年将超过4500亿成为市场占比最高的网络广告形式(iResearch,2021)。然而信息流广告表面繁荣的背后，也存在一些隐患：据报道，有 $67 \%$ 的用户在使用信息流媒体时，因感知到信息流广告对其阅读体验带来干扰有过广告屏蔽行为(eMarketer,2020)。Chung 和Kim(2021)对19\~29岁Facebook用户进行深度访谈发现，有将近 $70 \%$ 的受访者表示，常常会无视其中的信息流广告选择快速跳过。屏蔽和跳过等广告回避行为会降低广告主营销支出效率(Chen&Liu,2022;Dukes etal.,2022)，威胁平台发展(严磊 等,2020)，如果平台缺乏赞助则无法持续提供优质且免费的服务，长远来看也会降低用户的整体福祉(Niuetal.,2021)。与信息流广告在业界的发展如火如荼形成鲜明对照，学界目前对信息流广告研究尚处于肇始期，信息流广告回避研究涉足不多。不同于传统媒介中的广告回避，信息流媒体平台的用户如何以及缘何回避信息流广告？平台该如何应对信息流广告回避行为？是亟待业界和学界探讨和解决的重点和难点问题。

信息流广告回避与传统媒介中的广告回避存在巨大差异。首先，用户信息加工状态的稳定性vs.用户信息加工状态的动态性。传统媒介(电视、广播、邮件、报纸等)中广告的嵌入背景相对固定，因此用户处理广告时其信息加工的状态相对稳定(Baek&Morimoto,2012)。而信息流广告是嵌入在源源不断涌现的流媒体资讯之中，在此背景下，用户已不再是单一的信息加工状态，其状态会随着其信息浏览场景的转变而发生动态转移(Kanuri et al.,2018)。其次，广告的凸显性 vs.广告的原生性。传统媒介中的广告一般采用凸显的广告形式，相关研究都强调由广告的干扰性所引起的广告回避(Goldfarb&Tucker,2011)。而信息流广告采用原生的广告形式，看上去与平台内普通的非商业信息区别不大。此时，用户对干扰性的感知更多的是由用户所处的信息加工状态决定(Ferreira etal.,2017; Sahni &

Nair,2020)，例如，Ferreira 等(2017)发现，当用户处于目标明确(或不明确)的信息加工状态时，其所感受到的信息流广告干扰性可能更强(或更弱)。最后，广告回避响应的滞后性 vs.广告回避响应的实时性。传统媒介中的广告内容和位置是相对固定的，因此很难对用户的广告回避行为进行实时响应，即使能够做到也具有滞后性(Baek&Morimoto,2012)。而信息流广告中的内容因人而异、因时而异，信息流媒体平台可以根据用户反馈动态的响应，调整广告内容和投放时机(Kanuri etal.,2018)。如果用户回避广告之后仍留在平台之中，理论上平台就有改过自新的机会进行响应式的广告重定向(Chen&Liu,2022)。

综上所述，信息流广告平台中用户信息加工状态的动态性、广告内容的原生性、和平台反馈的响应性对信息流广告回避问题提出了新的机遇和挑战。因此，传统媒介中的广告回避研究结论无法平移到信息流广告中。信息流广告回避问题的探讨应结合信息流媒体平台的特征，考虑如何通过可观测的用户信息浏览行为推断其背后的信息加工状态，区别用户在不同的信息加工状态下产生不同广告回避行为的内在机理。并进一步探讨平台应如何响应用户不同的广告回避行为，以提升后续广告的效果。以此为逻辑起点，本研究将从用户动态信息加工状态视角，在识别广告屏蔽和广告跳过两种可以被平台识别的信息流广告回避行为的基础上，探讨用户采取不同广告回避行为的内在机制，以及后续平台的响应策略。

# 2 文献回顾与评述

# 2.1信息流广告相关研究

（1）信息流广告的内涵与特征

信息流广告(in-feed native advertising)最早由社交巨擘Facebook于2006 年推出，随着移动互联网的发展越来越受到广告主和各大平台的青睐。信息流广告是指与所嵌入的信息流媒体平台中的信息特征保持一致，广告的内容可以根据用户实时的反馈进行响应式的动态调整，并具备社交功能属性的互联网展示广告(黄敏学，张皓,2019)。作为一种新兴的广告形式，信息流广告颠覆了传统互联网展示广告的传播过程，在广告设计层面(信息)、广告投放(渠道)、广告传播层面(信宿)都发生了转变：首先，广告设计层面。传统的互联网展示广告嵌入在网页之中，广告与网页其他内容存在清晰界限，一般采取让其高度可见(highly visible)的凸显形式来提升用户的唤起水平(arousallevel)，从而实现引起用户关注的目的(Goldfarb&Tucker,2011)。而信息流广告则是以原生的形式嵌入到用户阅读的信息流资讯之间，看上去就像一条普通的资讯，用户按照顺序从上至下逐条处理信息，每一条信息都会出现在用户的视觉焦点之中(Campbell&Evans,2018)；其次，广告投放层面。传统互联网展示广告主要投放于单向发布式的PC端，通常是基于细分市场的投放，因此个性化程度低并且无法根据用户反馈实时响应(Kim etal.,2019)。而信息流广告主要投放于移动端的去中心化社交流媒体平台，投放内容因人而异并且可以根据用户反馈动态响应(Yang&Jiang,2021)；最后，在广告传播层面。媒介的不同导致企业和用户以及用户彼此之间的关系发生转变。传统互联网展示广告是单向一对多的广告传播，用户之间也少有交集相互区隔(Bell&Buchner,2018)。而移动端的社交媒体平台赋予了信息流广告社交功能，用户通过点赞、转发、评论等社交功能按钮参与广告互动，用户之间通过平台的社交功能连接了起来(Lee et al.,2018)。

# (2）信息流广告的研究现状

信息流广告研究领域的学者一般聚焦于用户与广告两个层面进行探讨：(1)从用户层面来看，当前信息流广告的研究一般从用户稳定的心理属性(如，性别、年龄、社交关系)和历史的行为属性(如，历史浏览记录)出发来探讨信息流广告内容的精准推送。例如，Magesh 和Vijayalakshmi(2019)研究发现根据不同用户性别和年龄属性的差异，信息流广告插入的序列位置需要动态调整才能实现更好的广告效果；Kim 等(2016)在对 Facebook 中的“好友广告”(friend advertising)策略的研究中发现，对于弱关系的公共信息浏览页面推荐高解释水平的广告效果更佳，而对于强关系的个人信息浏览页面推荐低解释水平的广告效果更佳； (2)从广告层面来看，相关研究一般从广告形式与内容的角度出发探讨如何提升信息流广告效果的问题。例如，Aribarg 和 Schwartz(2020)研究发现信息流广告品牌适度凸显更有利于实现广告说服、品牌识别和平台信任的权衡；Wojdynski和Evans (2016)认为信息流广告放在居中或者底部的位置，在广告下角标注“广告”或“赞助”字眼相较于其它方式更容易引起用户的注意,于此同时也会引起部分用户对于广告说服意图的感知。

从上述文献梳理来看，国内外学者从各自的研究视角围绕着不同的研究问题对信息流广告展开了丰富的研究。但值得注意的是，在信息流广告前因研究方面，当前研究更多关注的是用户相对静态的、稳定的、历史的属性出发，忽略了信息流媒体平台的动态性和响应性特征，没有考虑用户浏览信息过程中信息加工的动态变化带来的影响。在信息流广告后效研究方面，更多关注的是广告点击、分享、购买意愿等广告传播带来的正面效果，对于广告屏蔽、跳过这类负面的广告结果关注较少。

# 2.2信息加工状态相关研究

# （1）信息加工状态的内涵与类型划分

信息加工理论(information processing theory)指出，人的认知过程就是对信息加工的过程，信息加工的状态会影响个体信息处理的方式、速度、认知状态，最终影响个体的决策判断(Hong& Desai,2020; Thompson& Hamilton,2006)。信息加工模式的概念有两个层面的内涵，在行为层面上指个体在面临信息任务时的信息处理方式，在心理层面指个体在处理信息任务时所处的认知状态(Huang et al.,2009;Thompson&Hamilton,2006)。信息加工研究领域的学者们通常采用二分法基于不同的视角将个体的信息加工状态划分为两种类型。如，Dickinger 和 Stangl(2011)根据用户搜索网络信息是否具有明确目标，将网络信息搜索行为划分为目标导向型(goal-directed information search)和体验型(experiential information search)信息搜索两种类型；Rezaei等(2016)在研究冲动购物时根据用户行为动机将用户的信息浏览行为划分为功能型网页浏览(utilitarian web browsing)和享乐型网页浏览(hedonic web browsing)两类；Ruiz 和 Sicilia (2004)根据用户处理信息时所处的思维模式划分为认知型处理风格(cognitive processing style)和情感型处理风格(affective processing style)两类。尽管学者们对于个体信息浏览模式的划分众说纷纭，但是究其根源一般都是根据用户处理信息时的行为导向与认知状态两个属性进行的划分。

# （2）信息流广告中的信息加工状态

广告研究领域的大量研究探讨了信息加工状态对于传统广告认知与决策的重要影响(Hossain,2018; Siefert et al.,2008; Zhang et al.,2014)。如，Thompson 和Hamilton (2006)对于海报广告研究发现处于分析型加工(analytical processing)状态的消费者会更偏好比较型广告，而处于想象型加工(imagery processing)状态的消费者会更偏好非比较型广告。再如，Jung等 (2014)对于网络展示广告研究指出，处于目标明确(telic mode)信息加工状态的消费者对于低互动水平的网络广告态度更加积极，而目标不明确(paratelic mode)信息加工状态的消费者对于高互动水平的网络广告态度更加积极。

纵观当前研究，学者们大都是从静态的信息加工视角探讨处于不同信息加工状态下的消费者对于某一则广告的处理，这是因为传统广告的嵌入情境是相对固定的。信息流广告的嵌入情境有别于传统广告：(1)广告嵌入位置具有动态性。信息流广告采用和流媒体资讯相同的形式，呈现若干条资讯之后呈现一则信息流广告，信息流广告嵌入在哪些资讯之后因人而异、因时而异(Wangetal.,2019);(2)用户信息选择具有动态性。用户在信息流媒体平台对于信息的选择是自由的、自主的，用户在处理信息流广告之前有时会选择主题相似的资讯进行深度阅读，有时会选择主题差异化的资讯进行多样化的阅读。逆转理论(reversaltheory)指出，个体认知深受所处场景的影响具有复杂性和可变性(Semaan et al.,2019)，由于信息流广告所嵌入的情境在客观的嵌入位置和用户的主观信息选择上具有动态性，从而启动用户处理广告时的信息加工状态随之动态变化。网络搜索广告的呈现方式和信息流广告具有相似之处，都是嵌入在信息流之中依次不断出现。与之不同的是，搜索广告是用户主动搜索呈现的，搜索广告的嵌入的背景都是与搜索关键词相关的内容，而信息流广告是平台根据算法投放的，其嵌入的内容具有多样性且一般和广告内容无关，不断阅读不同信息内容的用户更容易被激发出不同的信息加工状态(Zhou & Xue,2019)。

# 2.3广告回避相关研究

（1）传统广告回避的类型与前因后果

广告回避一直被认为是广告商面临的最大障碍之一。正如 Speck 和 Elliot(1997)指出"用户任何形式的广告回避都会不同程度的减少广告内容的呈现，削弱广告效果”。广告回避包含着用户在认知(cognition)、情感(affect)、行为(behavior)三个层面的广告反馈(Cho&Cheon,2004)。认知层面的广告回避指用户对广告负面的认知导致其主动忽视或者无视广告，即我不相信该广告（“Idon’tbelieve it”)；情感层面的广告回避指用户对广告产生了负面的情绪和态度，即我不喜欢该广告（“Idon’tlikeit”）；行为层面的广告回避指用户做出例如快进、换台/翻页、关闭广告窗口、视线主动离开广告等行为，即我不看该广告(“Iwont do it”)。

回顾以往的研究，学者们对于各种传统媒介中的广告，如杂志、报纸、广播、电视、邮件、短信、网络旗帜广告等，广告回避的前因与后效进行了大量的研究(Baek & Morimoto, 2012; Bang et al.,2018; Michelon et al., 2020; Speck & Elliott,1997)。目前前因研究主要围绕广告本体、用户个体、媒介载体三个层面进行探讨(Cho & Cheon,2004; Seyedghorban et al.,2016; Teixeira et al.,2010)。 但是由于传统媒介自上而下的垂直沟通属性，学者们普遍认为传统媒介中的广告回避还是由广告层面的干扰性为主要缘由。有关广告回避后效的研究，以研究广告回避给广告商、平台、消费者带来的负面效果为主流(Teixeira etal.,2010；严磊 等,2020)。尽管如此，仍有部分学者以积极的视角探讨如何使广告在被回避的情况下仍然尽可能产生一些积极的广告效果。例如，Brasel和Gips(2008)通过眼动仪实验发现，当电视广告中的品牌信息处于屏幕中心区域，快进观看相较于正常速度观看反而更能获取用户的注意力。Bellman 等(2010)则探讨了广告回避产生的残留效应(residualeffect)，通过将广告完整展示与快进、广告静音、眼睛离开屏幕、转换频道、广告跳过这五种广告回避形式进行两两比较发现，虽然广告部分展示的效果远不及全部展示，但是仍然会对用户的广告认知、广告态度、广告回忆带来一定程度上的积极效果。

# （2）信息流广告回避机制

近期，广告回避的研究拓展到了信息流广告领域。当前信息流广告回避研究模型大多是对传统广告回避经典模型的延伸，聚焦于探讨信息流广告回避的前置因素，致力于减少用户的广告回避行为。如，Niu等(2021)从心里所有权理论视角出发，认为社交媒体中的信息流广告是由于侵犯了用户的注意和个人空间才导致广告回避；Chung 和Kim(2021)从社会影响理论视角出发，认为除了受到广告干扰性的影响之外，品牌口碑和品牌粉丝数量也是影响社交媒体中信息流广告回避的重要因素；Chinchanachokchai 和De Gregorio (2020)从消费者社会化的角度出发，认为社交媒体中的信息流广告回避主要受到用户对同伴和对社交媒体易感性的影响；Youn 和Kim(2019)从心理抵抗理论视角出发，感知信息流广告的侵犯性和对自由的威胁是导致广告回避的主要原因。尽管学者们对于信息流广告回避的前因持不同观点，但都越来越强调用户所处的情境特征带来的影响。这是由于在信息流媒体中的用户被赋予更多的自主权，并且呈现行为碎片化、决策场景化的特征(Martins etal.,2019)，因此用户的情境特征对于信息流广告效果的影响愈发重要(Yang&Jiang,2021)。本研究将用户所处的信息加工状态这一用户情境特征纳入考虑，探讨用户动态信息加工状态下的信息流广告回避。

# （3）信息流广告的屏蔽与跳过

信息流广告存在广告屏蔽(ad blocking)和广告跳过(ad skipping)两类可以被平台观测的广告回避行为(Chen & Liu,2022; Chung& Kim,2021; Dukes et al.,

2022)。信息流广告屏蔽指用户点击广告关闭按钮屏蔽该条广告，此类广告回避行为通常是显而易见且被服务器直接记录的，目前大部分信息流媒体平台会基于此类广告屏蔽数据对后续广告投放进行优化(Chen&Liu,2022;Niu et al.,2021)。信息流媒体平台存在两类“跳过”广告行为，一类是用户对信息流广告无明显态度，并未对该广告进行任何点击或屏蔽的行为操作只是将该广告划过，此类属于正常的信息选择行为不属于广告回避(Bellman etal.,2010)，另一类指用户不想看该条信息流广告通过快速划过的方式主动忽视，此类广告跳过行为属于广告回避行为，类似于视频广告场景下的广告“快进”(Dukes etal.,2022)。这两类“跳过"广告行为可以通过用户阅读广告时长的总体分布以及处理不同信息之间的时间戳来相对地进行判断，如果用户跳过广告的速度与其跳过普通信息资讯的平均速度相当则可判断为正常的信息选择行为，如果用户跳过广告的速度显著快于跳过普通信息资讯的平均速度则可判断为广告回避当中的广告跳过行为(Belanche etal., 2017; Dukes et al., 2022)。

当前广告回避领域研究并未将不同广告回避行为产生的内在机制分别进行探讨，然而在信息流媒体使用场景中，广告屏蔽和广告跳过有着本质区别：首先，广告屏蔽表明用户关注到了广告信息，而广告跳过表明用户无视了该条广告信息；其次，广告屏蔽行为相较于广告跳过需要用户付出很高的行为和认知努力(Chen&Liu,2022)，而广告跳过意味着用户仅识别出该条广告但并未处理该条广告信息就将此广告划过(Dukes etal.,2022)；最后，广告屏蔽表明用户对广告产生了“心理抗拒”(Niuetal.,2021)，而广告跳过相较于广告屏蔽而言则并未唤起用户太多的心理反应(Belanche etal.,2017)。因此，广告屏蔽和广告跳过二者存在巨大差异，需要分别探讨二者才能更好洞察信息流广告回避的黑箱。

# 2.4广告重定向相关研究

被大数据赋能的企业，在广告投放失效之后仍然可以根据用户的历史行为识别出用户更为精准的偏好，从而进行广告的重定向(Villas-Boas&Yao,2021)。有关广告重定向的研究在传统广告背景下进行了丰富的探讨，主要聚焦于两个方面：(1)探讨广告重定向对广告效果的影响。如，Villas-Boas 和Yao (2021)在搜索广告情境下，发现基于用户搜索行为的广告重定向对广告效果有积极的影响。再如，Sahni 和Nair (2020)研究发现，旗帜广告采用重定向策略之后， $14 . 6 \%$ 的消费者会在四周内回到网站中来；(2)探讨广告重定向的时效性对广告效果带来的影响。

如，Li等(2021)研究了短信、邮件广告情境的重定向，强调重定向时效性的重要性，认为广告重定向需要“趁热打铁”及时响应才能实现更好的效果。再如，Bleier 和Eisenbeiss (2015)指出，网页广告基于用户的浏览记录进行重定向会带来积极的广告效果，但是效果会随着时间不断衰减。通过文献梳理发现，以往的研究普遍关注的是基于用户浏览、搜索、添加购物者这类积极的行为信号进行的广告重定向，然而关于广告回避这类消极的行为信号该如何重定向还尚未有研究探讨。

本研究将探讨如何基于信息流广告回避这一消极的信号进行广告重定向。一方面，是由于信息流媒体平台可以捕捉用户的广告回避行为(Kanuri etal.,2018)，基于此洞察用户心理可以为广告重定向提供依据；另一方面，是由于信息流媒体平台可以实时响应用户反馈(Chen&Liu,2022)，因此为响应式的重定向提供了机会。

# 2.5 研究评述

前述文献为本研究的开展打下了良好的基础。然而，对于本研究所关注的信息流广告屏蔽和跳过问题而言，当前文献仍存在如下缺口正是本研究试图做出的贡献之处，具体如下：

首先，对信息流广告回避问题缺乏研究。当前信息流广告的研究停留于用户的积极反应，关注如广告点击、购买意愿、广告分享等积极的结果(Kimetal.,2017;Yang&Jiang,2021; Zhou&Xue,2019)。然而，对于广告回避这类消极的用户反应探讨较少(Chung&Kim,2021)。对于信息流广告回避问题的研究有助于全面理解信息流广告的效果，具有重要的理论研究意义和实践价值。

其次，用户动态信息加工对用户认知和偏好的影响并没有得到充分的关注。信息加工领域研究通常从静态的视角探讨了不同信息加工状态下的用户差异(Siefert et al.,2008; Thompson & Hamilton,2006; Zhang et al., 2014)，然而，在移动互联网时代，用户呈现行为决策碎片化、场景化、移动化的特征(黄敏学，张皓,2019)。因此，用户的信息加工状态随着信息处理场景的变化而动态变化，用户的认知和偏好也随之动态迁移。本研究从用户动态信息加工状态视角探讨信息流广告的研究问题，有助于深化对信息加工理论在移动互联网时代背景下的应用和理解。

最后，未探讨广告回避之后的广告重定向问题。当前研究对于广告回避大多聚焦于广告回避前置因素的探究(Ferreira et al.,2017; Michelon et al.,2020; Niu etal.,2021)，然而对于广告回避之后如何重定向缺乏明确指引。而信息流媒体平台为广告回避后进行响应式的重定向提供了实现的机会和场景。因此，本研究探讨信息流广告回避的前因到后果到后续的再定向，从更加完整的研究视角构建了信息流广告回避和应对的全模型。

# 3研究构想

本研究从用户动态的信息加工状态视角出发，力图深化对于用户信息流广告回避内在机制的理论理解。同时，也从信息流媒体平台管理实践出发，帮助平台实时响应用户的广告回避行为，优化后续广告的重定向策略。具体来说，本研究有以下三个目标： (1)回答用户在动态信息加工状态下为何以及如何回避信息流广告。即结合信息流广告特征，从用户动态信息加工状态的视角切入，探讨信息流广告屏蔽和跳过这两类回避行为是由什么因素导致的？产生的内在机制分别是什么？以及刻画信息流广告回避决策的动态过程； (2)探讨用户屏蔽信息流广告后平台的重定向策略。信息流广告屏蔽是最容易被平台观测到的信息流广告回避行为，用户屏蔽信息流广告之后会对后续广告效果产生什么影响？广告回避的相关研究中发现，用户广告屏蔽行为由于需要投入较高的认知和行为努力，因此会带来“残留效应(residual impact)”提升用户对广告的记忆和认知(Bellman et al.,2010)。基于此，本研究将探讨如何利用广告屏蔽后的残留效应进行屏蔽后的广告重定向；(3)探讨用户跳过信息流广告后平台的重定向策略。信息流广告跳过意味着广告展现效果微乎其微，平台也很难从用户此类“视而不见”的行为中获取指引后续广告投放的有效信号。信息流广告跳过会对后续广告带来怎样的影响？研究表明，用户在持续信息处理过程中受到“学习效应(learmingeffect)”的影响，后续跳过广告的可能性会更高(Belanche etal.,2017)。因此，当出现高频的信息流广告跳过行为时，平台应该采取何种措施打破这种行为趋势？研究表明，唤起用户的广告注意是打破广告跳过行为模式的关键(Brasel&Gips,2008;Siefert etal.,2008)。基于此，本研究将探讨后续广告如何采用“凸显策略”来中断信息流广告的跳过行为模式。本研究理论框架如图1所示。

![](images/349b5c7e1e6c7c03fe69329268220ea4077b7766c50f951547a737271d7c4897.jpg)  
图1本研究理论框架示意图

3.1研究一：基于用户动态信息加工状态的信息流广告回避机制研究（1）研究1a：信息流广告屏蔽和跳过机制探讨

如前文所述，当前信息流媒体平台主要存在两类信息流广告回避行为，分别是广告屏蔽(ad blocking)和广告跳过(ad skipping)。由于信息流媒体平台的信息是以一种至上而下的、连贯的、序列式的形式呈现，展示若干条资讯随后展示一条信息流广告(Wang etal.,2019)，在展示不同的信息流广告之前，用户对于流媒体资讯的内容选择和信息处理方式存在差异。广告领域有大量研究表明，广告的嵌入背景或者说在广告之前展示的信息会影响人们对于广告的认知决策(Kim&Meyers-Levy,2008; Zhang et al.,2014；范思 等,2018)，然而以往研究探讨的是静态信息处理情境下单一背景信息对某一则广告处理的影响，而关于信息流媒体平台这一动态的信息处理情境下系列信息资讯对于不同广告的影响效应还尚未有研究探讨。在信息流媒体平台，用户在面临不同广告时的认知状态会受到浏览情境的影响而发生动态迁移(Siefert et al.,2008; Zhang et al.,2014)，基于此，本研究从用户动态信息加工状态视角出发，探讨屏蔽和跳过两类不同信息流广告回避决策行为产生的内在机制。

根据用户在信息流媒体平台信息浏览的行为模式，可以将用户信息流的动态浏览分为收敛式(convergent)和发散式(divergent)两种类型，其中，收敛式指聚焦于某一领域的资讯信息进行深度浏览，所选择的系列信息其主题与内容具有高度的相似性(Bjorneborn,2008;Nejati& Balasubramanian,2016)，发散式指进行多样化信息的宽度浏览，浏览的系列信息分属不同主题或内容差异化较大(Bjormebom,2008;Huang etal.,2009)。由于用户的信息选择行为是自主并且自由的，因此随着用户信息浏览行为模式的变化其信息加工状态也随之动态转化(Hong&Desai,2020; Zhang et al., 2014)。

心理抵抗理论(psychological reactance theory)认为，当用户将媒介视为自己的空间，如果广告使得用户感知到自主感受到威胁时，用户通常会采取诸如屏蔽广告等抵抗性的行为措施来恢复其自主感(autonomy)(Bang et al.,2018;Youn& Kim,2019)。当用户处于收敛式信息加工状态时通常是目标导向的，目的是进行某领域的信息性强化，此时用户不希望信息搜索的任务被打断，对于自主感(autonomy)具有较高的需求(Oliveira-Castro & Foxall,2017; Youn& Kim,2019)。Niu 等(2021)研究也指出，当用户在媒体平台信息浏览目标较为明确时更容易感受到广告对于心理所有权(psychologicalownership)的干扰，这种干扰不仅是注意力层面的干扰(attention invasiveness)还会感受到领域空间层面的干扰(space invasiveness)，从而促使用户屏蔽广告。视觉认知领域研究发现，个体对于同一则广告的不同构成要素投入的注意水平是不均衡的，在不同信息加工状态下个体的注意选择存在明显差异(Monga& John,2008;Thompson&Hamilton,2006)。当用户处于收敛式这种理性的、分析式的信息加工状态时，更加关注更够帮助其理性判断的如产品类型、产品功能、价格等精确的、具体的、有物理参照的广告具象要素(concrete elements)信息(Dewi&Ang,2020;Hur et al.,2020)。据此可以推断，当用户处于收敛式信息加工状态时，更多的会由于广告的具象要素的侵入性让用户感知到自主感受到威胁，促使用户选择屏蔽该条广告以恢复自主感。

认知资源理论(cognitive resource theory)认为用户的认知资源是有限的，广告和其它信息属于竞争关系共同争夺用户的注意，如果广告没有带来一定的心理唤起(arousal)则会被用户忽视并快速跳过(Dukes et al.,2022; Romberg et al.,2020)。当用户处于发散式的信息加工状态时，目标是对刺激的渴望、寻求唤起、预防厌倦等(Bjorneborn,2008)。例如，Kwon 和 Jain (2009)在研究多渠道购买时，发现用户是为了寻求最优的唤起水平(optimalarousal level)才不断寻求多样化的信息。

学者们普遍认为发散式的信息处理不符合用户理性决策的观点，相反，会让人联想到享乐性动机和基于感觉的(feeling-based)、无目的(nonpurposeful)、低努力(low-effort)、快速的(fast)的行为决策过程，会激发人基于整体的抽象思考(Dickinger & Stangl,2011; Kwon & Jain,2009; Sharma et al.,2010)。此时，用户处理一则广告信息更容易关注到的是不需要投入太多认知努力的并且更能够带来注意唤起的抽象的、模糊的抽象要素(abstract elements)信息，如品牌、配图、颜色、布局等(Bang&Wojdynski,2016;Dewi&Ang,2020)。当用户处于发散式的信息加工状态时，只有那些能够带来高心理唤起(high arousal)的信息才能够在众多的信息中脱颖而出吸引住用户的注意(Bjormeborm,2008)，若广告的抽象要素特征未能引起用户的心理唤起，则会容易被用户忽视直接跳过。因此，本研究提出如下命题：

命题1：当用户处于收敛式的信息加工状态下，用户更容易受到信息流广告具象要素侵入性的影响威胁用户自主感从而导致信息流广告屏蔽。

命题2：当用户处于发散式的信息加工状态下，由于信息流广告的抽象要素难以带来用户较高的心理唤起从而导致用户跳过信息流广告。

# （2）研究1b：信息流广告回避的动态决策模型构建

上述对于信息流广告回避机制的探讨只能静态的阐释用户信息流广告屏蔽和跳过的机制，仍无法很好的刻画用户处于不同的信息加工状态下，如何产生一系列连贯的、前后相关联的广告决策行为。由于用户在信息流平台中的行为决策往往是连贯的、序列的，如果将这些用户决策行为割裂开单独研究则会忽略用户前后出现的决策行为之间的关联，由此带来的内生性会导致有偏的且不一致的模型估计。因此，需要构建整体的动态模型来拟合用户在信息流媒体平台中回避广告的动态过程。马尔科夫随机游走过程一直在拟合不同研究场景下的动态过程扮演着重要的角色(Liu et al.,2021; Zhuang et al.,2021)。近期，在消费行为决策领域，马尔科夫族的一系列衍生模型如隐马尔可夫模型(hidden markov model)(Liberali&Ferecatu,2022)和多状态风险模型(multi-state hazard model)(Yu,2021)被广泛应用于刻画消费者的动态决策过程。本研究对信息流平台用户动态的广告决策行为建模的理论基础源于该领域的经典文献(Le-Rademacher etal.,2018)，并根据信息流平台场景的实际情况以及之前研究内容中对用户广告回避行为机制因素的假设，对模型形式的设定(如时间的离散性和随机效应的分布等设定)以及核心参数(如状态转移矩阵和影响用户广告回避因素的假设)做出了相应的调整。最终，通过构建多状态转移脆弱性模型(multi-state frailtymodel)来刻画用户在信息流平台中回避广告的动态过程，它在经典的马尔科夫随机游走模型的基础上放宽了对时间同质性的假设(Zhuang etal.,2021)，因为考虑到用户在信息流场景中的广告决策具有累积效应，用户在一段信息浏览过程中看到的所有广告都有可能对后续广告的反馈带来累积的影响。另外，脆弱性模型也相较于传统的风险模型考虑到了用户异质性和其他不可观测的潜变量的影响(Tran etal.,2020)。

具体来讲，本研究构建的模型给出了以下设定：以用户开始进入信息浏览为初始状态(状态1)，以用户最终在某个时刻t结束浏览为最终状态(状态4)，模型主要关注的是用户从初始状态到最终状态之间可能做出的与广告回避有关的决策，即广告跳过(状态 2)和广告屏蔽(状态3)。需要注意的是，虽然广告的点击、分享、评论等也都可能出现在本研究界定的用户初始状态和结束状态之间，但这些并不是本研究主要关注的内容，为了保证研究的聚焦和模型的简化，模型仅列出用户在信息流平台中出现的广告回避行为状态，如图2所示。

![](images/d7d6344e3b89b33ad07097a669bc0e6171087cd09be8c153d4725d5748a4f704.jpg)  
图2用户信息流广告回避动态过程的多状态转移脆弱性模型

在图2中，当用户开始一段信息浏览时即进入了状态1，与此同时该用户从状态1转移到状态2,3,4的风险开始累积，即该用户可能在信息浏览过程中出现广告跳过(ai：从状态1转移到状态2)，广告屏蔽(az:从状态1转移到状态3)，或者浏览一段时间信息流内容后结束浏览，期间不出现任何广告跳过或屏蔽行为(a:从状态1转移到状态4)。而当用户转移到状态2后，该用户接下来转移到状态1,3,4 的风险开始累积，即该用户可能返回到信息浏览状态(bi：从状态2转移到状态1)，也可能进一步产生广告屏蔽行为(bz：从状态2转移到状态3)，或者结束浏览(b：从状态2转移到状态4)。当用户转移到状态3后也会出现与状态2下类似的状态转移风险。需要注意的是，状态4在模型中被设定为“吸收状态"(absorbing state)，即一旦用户进入状态4，用户就结束了整个信息浏览过程，模型刻画的整个动态过程也就结束，不会再出现从状态4向其他状态转移的情况。本研究通过符号a,b和c分别表示以信息浏览，广告跳过和广告屏蔽几个状态为起点的状态转移，同样的起点状态(或终点状态)具有样本内的相关性需要在动态模型中控制。

进一步的，模型定义随机变量 $T _ { m  n } \in \{ t _ { 1 } , t _ { 2 } , . . . t _ { q } \}$ 表示用户出现状态转移的时间， $t _ { q }$ 以毫秒为单位记录了用户在信息流平台浏览过程中的时间节点。用户在$t$ 时刻从状态 $\mathbf { \nabla } _ { m }$ 转移到状态 $n$ 的风险率(hazard rate)为以下条件概率：

$$
\lambda _ { i j , m  n } ( t ) = P ( \mathrm { T } = t | \mathrm { T } \geq t )
$$

其中, $\lambda _ { i j , m  n } ( t )$ 就是用户在状态动态转移过程中某一时间点下的状态转移风险率，可以进一步拆分为两个部分，一部分为基准风险率(模型的非参数部分)，另一部分为本研究在前文中假设的一系列因素驱动的风险率(模型的参数部分)，由此得到的半参数模型如下：

$$
\lambda _ { m  n } ( \pmb { X } _ { m  n } ( t ) , \pmb { V } ) = \lambda _ { 0 } ( t ) e x p \ : ( \pmb { \beta } _ { m  n } \pmb { X } _ { m  n } ( t ) )
$$

其中， $X _ { m  n }$ 是之前研究内容所提出的影响用户广告跳过和屏蔽等行为的一系列因素， $\pmb { \beta } _ { m  n }$ 是这些因素相应的系数。 $X _ { m  n } ( t ) = \{ X _ { m  n } ( s ) | 0 \leq s \leq t \}$ 表示的是截止到 $\mathbf { \chi } _ { t }$ 时刻，用户所处的信息加工状态(收敛式或发散式)。为了进一步控制用户不可观测的异质性(例如个体差异化的信息内容偏好和广告反馈偏好)所带来的影响，本研究在原有模型基础上增加了脆弱性参数(frailty term)得到一下模型：

$$
\lambda _ { m  n } ( { \pmb X } _ { m  n } ( t ) , v ) = \lambda _ { 0 m  n } ( t ) e x p \ ( \pmb { \beta } _ { m  n } { \pmb X } _ { m  n } ( t ) + v )
$$

其中，随机变量 $\nu$ 控制了样本中不可观测的个体异质性部分，一般假设 $\nu$ 服从均值为1，方差为 $\frac { 1 } { \theta }$ 的 gamma 分布(Aboulnasr et al.,2008)。该模型的参数估计可以采用惩罚极大似然估计方法，在R软件中使用 frailtypack 得到相应的参数估计结果。

综上，通过构建动态的模型，可以聚焦于用户在信息流平台中关于广告决策行为的动态过程，不再只是静止的讨论每一个单独的广告决策背后的机制，而是连续的、动态的洞察用户的广告决策行为，同时检验前文所提出的广告屏蔽和跳过机制在动态模型的视角下是否依然成立。

# 3.2 研究二：用户屏蔽信息流广告后的平台重定向策略

上述研究内容一探讨了信息流广告屏蔽行为的产生机制，在此基础上，作为信息流媒体平台更关心的问题是用户屏蔽广告之后该如何应对？当前大部分学者都关注到了广告屏蔽行为给用户、广告商、平台带来的负面影响(Baek&Morimoto,2012;Cho&Cheon,2004)。然而，用户广告屏蔽行为带来的影响都是负面的么？一些研究发现，广告回避之后仍会存在一定的残留效应，即对广告存在一定的认知记忆(Bellman et al.,2010; Brasel& Gips,2008)。例如，Bellman 等(2010)在研究中对比了四种不同类型的电视广告屏蔽行为，发现用户在广告屏蔽时需要付出的行为和认知努力越高，广告的残留效应就越高。简单暴露效应(mereexposure effect)指出，人们对于以往经验的偏好更胜于新的刺激，因此相较于全新的广告信息，消费者对熟悉的广告信息处理的更为流畅(Fangetal.,2007;Montoya et al.,2017)。由于偏好判断是快速决断的、未经过深思熟虑思考的，因此流畅性的提升会带来对于熟悉广告的偏好(Bell& Buchner,2018)。那么，平台应如何利用广告屏蔽带来的残留效应制定相关策略来趋利避害，提升后续广告的效果呢？

基于经典的错误归因模型(misatribution model)(Bornstein&D'agostino,1992)，广告屏蔽产生的残留效应是否能够带来积极的影响，取决于用户是否能从后续广告处理中感知到流畅性，并且不将这种流畅性归因于之前的广告展示(Bell&Buchner,2018)。当前主流的信息流媒体平台也在尝试不同的屏蔽归因引导策略。例如，百度在用户屏蔽广告时设置了比较抽象、模糊的归因(如，“不感兴趣”)，也设置了比较具体的归因(如，“屏蔽某品牌”)；今日头条在用户屏蔽广告时同样也设置了比较抽象、模糊的归因(如，“屏蔽某类广告”)，和比较具体的归因(如，“屏蔽某品牌”)。那么，在用户屏蔽广告时，不同的屏蔽归因策略是否会对后续广告的态度产生影响？以及如何影响呢？

研究表明，启动人抽象的思考会促使个体进入一个整体式的思维模式(Monga＆John,2008)，此时用户会将广告视为整体，更容易将广告屏蔽理由归结为广告整体的不喜欢。而启动人的具象思考会促使个体进入一个分析式的思维模式(Yoon,2013)，此时用户认为广告各要素之间是相互独立，更容易将广告屏蔽的理由归结为对某个要素的不喜欢。因此引导用户更为具体的屏蔽归因策略，可以促使用户将屏蔽理由归结于某个具体的要素，而不是广告整体。因此，当用户选取较为抽象的屏蔽原因时说明是对广告整体的不喜欢，此时屏蔽广告的残留效应会对后续广告会产生负面的影响。当用户选取较为具象的屏蔽原因“屏蔽某品牌”时，表明对广告中的品牌产生负面认知，与此同时广告其他要素譬如产品品类可能仍存在残留效应，那么用户后续对相同品类但是不同品牌产品的广告信息处理时会具有更高的流畅性，从而提升了广告的态度。综上所述，本研究提出如下命题：

命题3：用户具象(vs.抽象)的屏蔽归因会正向影响后续同品类(vs.不同品类)产品的广告态度。

如前研究一所述，当用户处于收敛式的信息加工状态时对于广告的具象要素更为关注(Dewi&Ang,2020)，当用户处于发散式的信息加工状态时对于广告的抽象要素更为关注(Kwon&Jain,2009)。若用户屏蔽广告之后继续浏览信息，当用户处于收敛式的信息加工状态时处理基于具象引导归因策略推送的广告，会对广告具象要素更为关注，从而会增强屏蔽广告的残留效应带来的积极影响。当用户处于发散式的信息加工状态时对于广告的具象要素关注较少，因此对广告的熟悉感会减少，从而会削弱屏蔽广告的残留效应带来的积极影响。综上所述，提出如下命题：

命题4：用户收敛式(vs.发散式)的信息加工状态会增强其具象的屏蔽归因对后续同品类产品的广告态度的积极影响。

在确定了广告屏蔽后的广告推送策略之后，后续广告平台该在什么时机推送才能带来更优的广告效果呢？研究表明，当广告被视为干扰，后续如果推送广告过于紧密，广告被视为干扰的可能性越高(Wang etal.,2019)。因此，当用户屏蔽广告之后，不宜立即推送广告，需要让用户阅读一段时间的非商业信息恢复其自主权。于此同时，后续广告推送时机也不宜过晚，因为广告重定向效果具有时效性(Li etal.,2021)，于此同时屏蔽广告的残留效应也会随之间不断衰减(Bellman etal.,2010)。本研究提出如下命题：

命题5：用户具象的屏蔽归因对后续同品类产品广告态度的积极影响会随着后续广告与原屏蔽广告的时间间隔呈倒U型关系。

# 3.3研究三：用户跳过信息流广告后的平台重定向策略

相较于上述研究内容中的广告屏蔽行为，广告跳过则可能是更为普遍，却未引起足够重视的另一种信息流广告回避行为。由于广告屏蔽已经实现了广告展现，由此产生的认知残留可为后续的广告投放提供更多的重定向依据。但广告跳过则是用户主动选择无视广告快速划过，如同视频广告中的广告“快进”行为，此时广告的展现微乎其微(Cho&Cheon,2004)，平台可能很难从用户此类“视而不见”的行为获取后续广告投放的有效信息。不仅如此，研究表明用户在持续的信息处理过程中受到学习效应(learning effect)的影响，如果之前有过广告跳过行为，后续选择跳过广告的可能性会更高、决策速度会更快(Belanche etal.,2017)。因此，当广告跳过频率越高时，后续广告的注意时间就可能越短，从而形成连续的、习惯性的广告跳过行为模式，从而对信息流平台的广告收益造成更大的损失(Dukeset al.,2022)。那么，当出现信息流广告跳过行为时，平台如何进行及时干预呢？

视觉营销(visual marketing)和知觉心理学(perceptual psychology)领域的研究表明，唤起用户的广告注意是打破广告跳过行为模式的关键(Brasel&Gips,2008;Siefert etal.,2008)。因此，当用户广告跳过频率较高时，信息流媒体平台就需要及时调整后续广告投放策略，通过唤起用户更高的注意来避免后续的广告跳过。然而，信息流广告原生性的广告特征使其在获得用户注意力上存在挑战。Aribarg和 Schwartz(2020)研究发现，信息流广告的原生性确实顺应了用户对于阅读体验性的需求，但同时也难以提升用户的唤起和注意水平，存在削弱广告效果的风险。诸多研究表明，信息流广告并不是越原生越好，需要适当的凸显引发用户的注意进而才能实现说服(Campbell&Evans,2018;Wojdynski& Evans,2020)。纵观以往研究，一般通过两种路径来提升信息流广告的凸显性：其一，是通过提升广告具象要素的凸显性，如Wojdynski等(2017)从赞助清晰度(sponsor clarity)、产品信息披露(disclosure)、没有欺骗(lackof deception)等维度来提升信息流广告赞助信息的透明度;其二，是通过提升广告抽象要素的凸显性，如Aribarg和Schwartz (2020)在研究中通过改变信息流广告品牌的显著性来实现信息流广告的适度凸显。

注意参与理论(attention engagement theory)认为，用户在不同信息加工状态下对广告各要素的注意选择(attention selection)和注意参与度(attention engagement)存在差异(Pieters&Wedel,2004)。当用户处于收敛式的信息加工状态时，会激发人基于细节的具象思考，因此会对信息进行仔细逐步分析，此时对广告具象层面的要素会更为关注(Dewi&Ang,2020)。因此，可以通过提升广告具象要素的凸显性来提升用户对于广告的注意。当用户出现广告跳过，此时若用户处于发散式信息加工状态时，对不需要深度认知加工的广告抽象要素更为关注(Dickinger&Stangl,2011)。因此，可以通过提升广告抽象要素的凸显性来提升用户对于广告的注意。综上所述，本研究提出如下命题：

命题6：当用户出现信息流广告跳过时，用户信息加工状态调节后续广告凸显策略对后续广告注意的影响。具体而言：当用户处于收敛式信息加工状态时，后续广告采用具象要素凸显策略会正向影响后续广告注意；当用户处于发散式信息加工状态时，后续广告采用抽象要素凸显策略会正向影响后续广告注意。

# 3.4 研究方案

本研究综合采用深度访谈、基于企业后台真实用户行为数据的建模分析、实验室实验和现场实验等多方法交叉验证的方式来解决相关问题。具体来讲：首先，基于文献研究，对消费者、广告行业从业者和信息流媒体平台广告部员工的元样本进行深度访谈，深度挖掘信息流广告投放机制、用户信息流广告屏蔽与跳过的原因、平台的应对措施与效果等问题，以完善本研究理论模型建构；然后，与代表性的信息流媒体平台建立合作关系，通过脱敏处理获取合作平台信息流广告展示数据。借鉴Netzer等(2008)在研究中提出的隐马尔科夫框架，可以通过信息流平台中用户可观测的信息浏览文本内容和广告反馈(如点击、停留时长等)来推测不可观测的用户动态的信息加工状态。采用多状态风险模型(multi-state hazardmodel)(Yu,2021)来构建用户动态信息加工状态与不同广告要素特征对不同广告回避行为的影响；接着，为了验证信息流广告的回避机制，第一步采用2(信息加工状态：收敛式 vs.分析式)组间实验设计，运用心理学研究领域中较先进的眼动追踪技术，记录被试对实验材料的眼动指标注视数(次)和注视时间。第二步构建虚拟的信息流媒体平台，设计2(信息加工状态：收敛式 vs.发散式) $\times 2 ($ 广告要素的侵入性：具象要素 vs.抽象要素)的组间设计，采用各类真实的新闻资讯辅以及纸质材料的情境刺激操纵被试进入不同的信息加工状态，通过记录虚拟信息流媒体平台中被试对不同的信息流广告实验材料的反应，获取被试在不同实验刺激下的广告回避、点击、注意等数据。这种实验设计更能够观察到现实信息流平台中被试的真实反应，降低了外部因素对实验结果的干扰；最后，通过现场实验，基于双重差分(difference in difference)的方法测算重定向策略实施所带来的净影响从而对信息流广告屏蔽后的重定向策略进行效果评估。

# 4理论构建与创新

信息流广告迅速发展，广告回避问题也日益凸显。虽然近来有少量研究对信息流广告回避进行了探讨(Chung&Kim,2021; Niu etal.,2021)，但都是依赖于对传统广告回避研究经典模型的延伸，未考虑信息流广告的特性。与传统广告媒介不同，信息流媒体平台更加强调用户导向，其用户也因此被赋予了更多的决策选择，被赋能的用户回避广告在所难免。信息流媒体平台的动态性、原生性和响应性(黄敏学，张皓,2019)，也使得传统广告回避的研究结论无法平移到该情境。不同于传统媒介中的广告其嵌入情境是相对固定的，信息流媒体平台的广告嵌入情境则是动态变化的(Kanuri etal.,2018)，用户的信息加工状态也会随着信息浏览的不同而发生迁移(Bjormeborm,2008；范思 等,2018)。本研究突破以往信息流广告研究仅关注用户静态属性的局限，从用户动态的信息加工视角出发，在识别信息流广告屏蔽和跳过两类广告回避行为的基础之上，探讨用户在不同信息加工状态下(收敛式vs.发散式)产生不同广告回避行为的内在机制以及回避后的重定向策略。

首先，本研究拟建立了基于用户动态信息加工状态的信息流广告回避机制。信息流广告屏蔽与跳过是信息流媒体平台常见并且可观测的信息流广告回避行为，然而既有信息流广告回避研究并未对二者形成的前置因素和内在机制分别进行探讨，忽视了信息流广告屏蔽和跳过存在本质差异(Chen&Liu,2022;Chung&Kim,2021;Dukes etal.,2022)。并且，当前为数不多探讨信息流广告回避问题的研究也更多是对经典广告回避模型的延伸，对于信息流广告的特性考虑较少，忽视了用户在信息流媒体平台信息浏览动态性特征带来的影响(Campbell& Evans,2018;Leeetal.,2018)。因此，本研究在识别用户屏蔽和跳过两类不同信息流广告回避行为的基础之上，根据用户在信息流媒体平台信息浏览的行为模式将用户信息加工状态划分为收敛式和发散式两种类型，探讨用户不同信息加工状态下产生不同广告回避行为的内在机制。心理抵抗理论(psychological reactance theory)认为，用户会将媒介视为自己的空间，当广告使得用户感知到自主感受到威胁时，用户会选择屏蔽广告以恢复其自主感(Bang et al.,2018;Youn&Kim,2019)。当用户处于收敛式信息加工状态时对于自主感有较高的要求并且此时广告的具象要素更容易引起用户注意，本研究推断此时用户可能更多的是由于受到信息流广告具象要素干扰性的影响从而产生广告屏蔽行为。认知资源理论(cognitive resourcetheory)认为用户的认知资源是有限的，广告和其它信息属于竞争关系共同争夺用户的注意，如果广告没有带来一定的心理唤起则会被用户忽视选择快速跳过(Dixet al.,2010;Dewi&Ang,2020)。当用户处于发散式信息加工状态时需要较高的唤起水平才能吸引其注意力，此时广告的抽象要素更容易引起用户的关注，本研究推断此时用户更多是由于广告的抽象要素无法给用户带来高唤起从而导致用户跳过信息流广告。对于信息流广告屏蔽和跳过静态机制的探讨仍无法很好的刻画用户处于不同的信息加工状态下，如何产生一系列连贯的、前后相关联的广告决策行为。本研究通过构建多状态转移脆弱性模型(multi-state frailty model)来刻画用户在信息流平台中回避广告的动态过程，不再只是静止的讨论每一个单独的广告决策背后的机制，而是连续的、动态的洞察用户的广告决策行为，同时检验信息流广告屏蔽和跳过机制在动态模型的视角下是否依然成立。

其次，本研究拟提出用户屏蔽信息流广告后平台的重定向策略。信息流广告屏蔽是一种直观的，可被平台直接记录的广告回避行为。以往关于信息流广告屏蔽的研究主要从广告屏蔽所带来的负面影响出发，重点探讨了如何减少或避免广告屏蔽行为(Chen&Liu,2022;Niu et al.,2021)。然而，信息流广告作为人们处理主要认知任务过程中的干扰，广告屏蔽在所难免。那么如何基于已经出现的用户广告屏蔽行为洞察用户内在需求，从而将其转化为有价值的信号，帮助信息流媒体平台进行后续的广告推送是当前平台非常关注的问题。本研究致力于挖掘用户回避行为的信号价值，探讨用户屏蔽信息流广告之后的广告重定向策略。广告回避的相关研究中发现，用户广告屏蔽行为由于需要投入较高的认知和行为努力，因此可能会产生“残留效应”提升用户对广告的记忆和认知(Bellman etal.,2010;Brasel&Gips,2008)。而广告屏蔽产生的残留效应是否能够带来积极的影响，取决于用户是否能从后续广告处理中感知到流畅性，并且不将这种流畅性归因于之前的广告展示(Bell&Buchner,2018)。当前信息流媒体平台在用户屏蔽广告时都会设置屏蔽原因选择按钮，具象的屏蔽归因更容易启动用户进行分析式思考，促使用户将广告屏蔽理由归结为某个具体要素，而抽象的屏蔽归因更容易启动用户进入整体式思考，促使用户将屏蔽理由归结为对广告整体的不喜欢。因此，本研究推断用户具象(vs.抽象)的屏蔽归因会正向影响后续同品类(vs.不同品类)产品的广告态度。进一步的，本研究还探讨了用户信息加工状态和后续广告插入时机的调节作用。本研究推断用户收敛式的信息加工状态相较于发散式信息加工状态更能增强其具象的屏蔽归因对后续同品类产品的广告态度的积极影响，并且用户屏蔽广告后后续广告推送的时间不宜过早也不宜过迟，总体来讲用户具象的屏蔽归因对后续同品类产品广告态度的积极影响会随着后续广告与之前被屏蔽广告的时间间隔呈倒U型关系。

最后，本研究拟提出用户跳过信息流广告后平台的重定向策略。相较于广告屏蔽这类需要付出更高认知和情绪努力的广告回避行为，广告跳过对于用户来说操作更加便捷，广告展现更少，并且一旦形成行为趋势，后续广告展现效果会大打折扣，其危害不容小觑(Dukes etal.,2022)。然而，一方面广告研究领域鲜少将广告跳过与其他广告回避行为区别开来，更加细粒度的探讨广告跳过行为(Belanche etal.,2017),另一方面也尚未有研究探讨当出现高频的广告跳过行为时，该如何进行广告重定向来打破这种行为趋势(Dukes etal.,2022)。研究表明，用户在持续信息处理过程中受到“学习效应”的影响，后续跳过广告的可能性会更高(Belancheetal.,2017)，而唤起用户的广告注意是打破广告跳过行为模式的关键(Brasel&Gips,2008;Siefert etal.,2017)。注意参与理论认为，用户在不同信息加工状态下对广告各要素的注意选择和注意参与度存在差异(Pieters etal.,2007),当用户处于收敛式的信息加工状态时，会激发人基于细节的具象思考，此时对广告具象层面的要素会更为关注，据此推断后续广告采用具象要素凸显策略会正向影响后续广告注意，而当用户处于发散式信息加工状态时，对不需要深度认知加工的广告抽象要素更为关注，据此推断后续广告采用抽象要素凸显策略会正向影响后续广告注意。

相较于以往研究，本研究的理论贡献如下：首先，本研究拓展了信息流广告回避领域研究。纵观信息流广告当前研究，聚焦于探讨如何提升信息流广告精准营销的效果(Kanuri et al.,2018;Wojdynski et al.,2017)。然而信息流媒体平台不仅大量存在屏蔽广告此类显而易见且并被服务器直接记录的信息流广告回避行为，还存在快速划过广告的广告跳过行为。相较于广告屏蔽行为，广告跳过行为则很难直接被观察到，需要通过用户阅读广告时长的总体分布来相对地判断其是否跳过了某条广告。当前不论是业界还是学界都尚未将这两种截然不同的信息流广告回避行为区别看待，没有对二者形成的前置因素和内在机制分别进行探讨，忽视了信息流广告屏蔽和跳过存在本质差异。对于信息流广告回避研究的不足会越发放大信息流广告研究和管理实践的鸿沟。本研究聚焦于探讨信息流广告回避问题，更加细粒度的探讨了广告屏蔽和广告跳过两类不同的信息流广告回避行为，从动态信息加工状态的视角深入探讨了不同广告回避行为的内在机制，为打开信息流广告回避黑箱提供了可能。

其次，本研究丰富了信息加工理论的研究视角。当前应用信息加工理论的研究大多是从相对静态的视角出发，探讨不同信息加工状态下个体的差异(Wojdynskietal.,2017;Youn&Kim,2019)。然而在移动互联网的时代，用户的行为决策呈现碎片化、场景化、移动化的特征，用户的信息加工状态也随着情境的变化而发生动态转变(黄敏学，张皓,2019)。当前研究对于用户信息加工状态进行了丰富的探讨，本研究在信息加工理论的基础之上根据用户在信息流媒体平台的信息浏览行为模式将用户的信息加工状态区分为收敛式与发散式两种方式，并厘清不同信息加工状态下用户差异。本研究通过刻画出用户在信息流媒体平台信息浏览行为的动态变化，尝试探索出用户动态的信息加工状态与信息流广告回避之间的影响关系，丰富了信息加工理论的研究视角，有助于深化对信息加工理论在移动互联网时代背景下的应用和理解。

最后，本研究推进了广告回避后的广告重定向研究。以往关于广告回避的研究对于广告回避的前置因素进行了丰富的探讨，致力于减少回避(Youn&Kim,2019)。然而，广告回避在所难免，当前研究停留在发现问题而不是解决问题的阶段，针对信息流广告回避后重定向问题的理论研究尚未开展。信息流媒体平台的响应性为探究广告回避后的重定向提供了场景。本研究力图构建具有信息流媒体特性的、相对完整的信息流广告回避研究模型，试图凸显用户信息流广告回避行为的信号价值，作为指导后续广告重定向的依据，以突破信息流广告回避对后续广告效果带来的负面影响，推进了广告回避研究的领域范围。

本研究构建的理论模型预期的研究结果也具有重要的实践价值。首先，对于广告商而言，有利于提升广告投放的效率和效果，减少营销支出的浪费。信息流广告作为网络广告主流的广告承载形式，对于广告商的重要性不言而喻。通过加强对用户广告回避心理过程的洞察，使得广告主能够创造和提供更多符合用户需求的广告内容，避免无效的广告投入和浪费；其次，对于信息流媒体平台而言，有利于提升平台声誉，促进平台持续健康的发展。从用户动态信息加工视角更加细粒度、实时、精准的刻画平台内用户的需求，深入了解用户进行广告回避的内在机理，把握后续平台的应对策略，一方面有助于平台提升用户的体验感，降低用户的流失率，建立与用户稳固的关系，另一方面有助于增强广告商对于平台的信任和支持，长远来看有利于平台的持续健康发展；最后，对用户而言，有利于用户持续享受免费且优质的信息服务，提升用户的整体福祉。深刻洞察信息流广告回避的原因并且有针对性的进行后续广告的推送，一方面能够提供给用户与其信息浏览状态相匹配而不是带来干扰的有益广告信息，另一方面也能让用户享受到平台提供的优质信息服务，从而有效提升了用户的整体福利。

# 参考文献：

[1]艾瑞咨询(iResearch).(2021).2021年中国网络广告年度洞察报告-产业篇.2021-9-14 取自   
https://www.iresearch.com.cn/Detail/report?id=3844&isfree=0   
[2]范思，鲁耀斌，胡莹莹.(2018).社交媒体环境下一致性与社交性对信息流广告规避的影响研究．管理 学报,15(5),759-766.   
[3]黄敏学，张皓.(2019).信息流广告的前沿实践及其理论阐释．经济管理,41(04),193-208.   
[4]严磊，梅姝娥，仲伟俊.(2020).消费者广告屏蔽行为对媒体平台竞争与社会福利的影响研究．管理工 程学报,34(01),17-24.   
[5]Aboulnasr,K., Narasimhan, O.,Blair,E.,& Chandy,R. (2oo8). Competitive response to radical product innovations.Journal ofMarketing,72(3),94-110.   
[6]Aribarg,A.,& Schwartz,E.M. (2O20). Native advertising in online news: Trade-offs among clicks, brand recognition,and website trustworthiness.Journal of Marketing Research,57(1),20-34.   
[7]Baek,T.H.,& Morimoto, M. (2012). Stay away from me. Journal of Advertising, 41(1), 59-76.   
[8]Bang,H., Kim,J.,& Choi,D. (2018).Exploring the efects of ad-task relevance and ad salience on ad avoidance: The moderating role of internet use motivation. Computers in Human Behavior, 89(7),70-78. [9]Belanche,D.,Flavian, C.,& Pérez-Rueda,A.(2O17). Understanding interactive online advertising: Congruence and product involvement in highly and lowly arousing, skippable video ads.Journal of Interactive Marketing,37(1),75-88.   
[10] Bell,R.,& Buchner,A. (2O18).Positive effcts of disruptive advertising on consumer preferences.Journal ofInteractive Marketing,41(1),1-13.   
[11]Bellman, S., Schweda, A.,& Varan,D. (2010). The residual impact of avoided television advertising. Journal ofAdvertising,39(1),67-82.   
[12]Bjorneborn,L. (2Oo8).Serendipity dimensions and users'information behaviour in the physical library interface.Information Research,13(4),13-14.   
[13] Bleier,A.,& Eisenbeiss,M. (20l5).Personalized online advertising effectiveness: The interplay of what, when,and where.Marketing Science,34(5),669-688.   
[14] Bornstein,R.F.,& D'agostino,P.R. (1992). Stimulus recognition and the mere exposure efect. Journal of Personality and Social Psychology, 63(4), 545-552.   
[15]Brasel,S.A.,& Gips,J. (2oo8).Breaking through fast-forwarding: Brand information and visual attention. Journal of Marketing, 72(6),31-48. [16] Campbell, C.,& Evans, N. J. (2018). The role of a companion banner and sponsorship transparency in recognizing and evaluating article-style native advertising. Journal ofInteractive Marketing, 43(2),17-32. [17] Chen,Y., & Liu, Q. (2022).Signaling through advertising when an ad can be blocked. Marketing Science, 41(1), 166-187.   
[18] Chinchanachokchai, S.,& De Gregorio,F. (2O2O). A consumer socialization approach to understanding advertising avoidance on social media. Journal of Business Research, 110(1),474-483.   
[19] Cho,C.H.,& Cheon, H. J. (2004). Whydo people avoid advertising on the internet? Journal ofAdvertising, 33(4),89-97.   
[20] Chung, Y. J.,& Kim,E. (2021).Predicting consumer avoidance of native advertising on social networking sites: A survey of facebook users.Journal of Promotion Management, 27(1),1-26.   
[21] Dewi,I.J.,& Ang,S.H. (2020). Assessing the imagination scale's nomological validity: Effect ofhedonic versus utilitarian product types and abstract versus concrete advertising execution. Gadjah Mada International Journal of Business,22(2),118-136.   
[22] Dickinger,A.,& Stangl,B. (2011). Online information search: Differences between goal-directed and experiential search.Information Technology & Tourism,13(3),239-257.   
[23] Dukes,A.,Liu, Q.,& Shuai, J. (2022). Skippable ads: Interactive advertising on digital media platforms. Marketing Science, 41(3),528-547.   
[24] eMarketer. (2020). Attitude toward social media advertising according to adults in Australia.   
Retrieved July 20,2020, from   
https://www.emarketer.com/chart/240480/atitudes-toward-social-media-advertising-according-adults-australia-bygender-jan-2020-of-respondents-each-group.   
[25] Fang,X., Singh,S.,& Ahluwalia,R. (2o07).An examinationof diffrent explanations for the mere exposure effect. Journal of Consumer Research, 34(1),97-103.   
[26] Ferreira, C., Michaelidou, N.,Moraes, C.,& McGrath,M. (2017). Social media advertising: Factors influencing consumer ad avoidance. Journal of Customer Behaviour, 16(2),183-201.   
[27] Goldfarb,A.,& Tucker,C.(2011). Rejoinder—implications of “online display advertising: Targeting and obtrusiveness". Marketing Science, 30(3),413-415.   
[28] Hong, J.,& Desai,K. K. (202O). Variety-seeking behaviorand information processing in choosing avacation destination.Journal of Travel Research, 59(5),850-863.   
[29] Hossain, M.T.(2018). How cognitive style influences the mental accounting system: Role of analytic versus holistic thinking. Journal of Consumer Research,45(3), 615-632.   
[30] Huang,P.,Lurie,N. H.,& Mitra,S. (2O09). Searching for experience on the web: An empirical examination of consumer behavior for search and experience goods. Journal of Marketing,73(2),55-69.   
[31] Hur,S.,Lee,J.E.,& Stoel,L.(2O2o).Fair trade advertising: Influences of information type and emotional appeal congruency. Journal of Marketing Communications,26(2),186-206.   
[32] Jung, J. M., Chu, H., Min, K. S.,& Martin,D. (2014). Does telic/paratelic user mode mater on the effectiveness ofinteractive internet advertising? Areversal theory perspective.Journal of Business Research, 67(6), 1303-1309.   
[33] Kanuri, V.K., Chen, Y.,& Sridhar,S. (2018).Scheduling content on social media: Theory,evidence,and application. Journal of Marketing, 82(6), 89-108.   
[34] Kim,D.H.,Sung, Y.H.,Lee,S.Y.,Choi,D.,& Sung,Y. (2016).Are you on timeline or news feed? The roles offacebook pages and construal level in increasing ad effectiveness. Computers in Human Behavior, 57(4), 312-320.   
[35] Kim,J.,Lee,J.,& Chung,Y.J.(2017).Product type and spokespersons in native advertising-therole of [36] Kim,K.& Meyers-Levy,J.(20o8).Context efects in diverse-categorybrand environments: Theinfluence of target product positioning and consumers' processng mind-set.Journal ofConsumer Research,34(6),882-896. [37] Kim, S., Youn,S.,& Yoon,D. (2019). Consumers'responses to native vs. banner advertising: Moderation of persuasion knowledge on interaction effects of ad type and placement type. International Journal of Advertising, 38(2),207-236.   
[38] Kwon, K.-N.,& Jain,D.(2oo9). Multichannel shopping through nontraditional retail formats:   
Variety-seeking behavior with hedonic and utilitarian motivations. Journal of Marketing Channels,16(2), 149-168.   
[39] Le-Rademacher,J. G.,Peterson,R.A.,Therneau,T.M.,Sanford,B.L.,Stone,R.M.,& Mandrekar,S.J. (2018). Application of multi-state models in cancer clinical trials. Clinical Trials,15(5), 489-498.   
[40] Lee,D.,Hosanagar,K.,& Nair,H. S. (2O18).Advertising content and consumer engagement onsocial media: Evidence from facebook. Management Science, 64(11), 5105-5131.   
[41]Li, J.,Luo, X.,Lu, X., & Moriguchi,T.(2O21). The double-edged effcts of e-commerce cartretargeting: Does retargeting too early backfire? Journal of Marketing, 85(4),123-140.   
[42]Liberali, G., & Ferecatu,A. (2022). Morphing for consumer dynamics: Bandits meet hidden markov models. Marketing Science,41(4),235-441.   
[43] Liu,Z.,del Rosario,M.,& Ding,Z.(2O21). A markovian model-driven deep learning framework for massive mimo csi feedback. IEEE Transactions on Wireless Communications,21(2),1214-1228.   
[44] Monga, A.B.,& John,D.R. (2008). When does negative brand publicity hurt? The moderating influence of analytic versus holistic thinking. Journal of Consumer Psychology,18(4),320-332.   
[45] Montoya,R.M., Horton,R.S.,Vevea,J.L., Citkowicz,M.,&Lauber,E.A. (2017). Are-examinationof the mere exposure effect: The influence ofrepeated exposure on recognition,familiarity,and liking.Psychological Bulletin, 143(5),459-489.   
[46] Nejati, J.,& Balasubramanian,A.(2016).An in-depth study of mobile browser performance. Paper presented at the Proceedings ofthe 25th International Conference on World Wide Web.1305-1315.   
[47] Netzer,O.,Latin,J.M.,& Srinivasan,V. (2o08).A hidden markov model ofcustomer relationship dynamics. Marketing Science, 27(2),185-204.   
[48]Niu, X.,Wang,X,&Liu,Z. (221).Whenifeeivaded,iwillavoidit:Theefectofadvertising invasiveness on consumers'avoidance of social media advertising.Journal of Retailing and Consumer Services, 58(1),102320.   
[49] Oliveira-Castro,J.M.,& Foxal, G.R.(2017). Consumer maximization of utilitarian and informational reinforcement: Comparing two utility measures with reference to social class. The Behavior Analyst, 40(2), 457-474.   
[50]Pieters,R.,& Wedel,M.(0o4).Attention capture and transfer inadvertising: Brand,pictorial,and text-size effects. Journal of Marketing, 68(2),36-50.   
[51] Rezaei,S.,Ali,F.,Amin,M.,& Jayashre,S. (2016). Online impulse buying of tourism products: The role of web site personality,utilitarian and hedonic web browsing. Journal of Hospitality and Tourism Technology, 7(1), 60-83.   
[52] Romberg,A.R.,Tulsiani,S.,Kreslake,J.M.,MilerLo,E.J.,Simard,B.,Rask,A.,Arismendez,S.V., Vallone,D.M.,& Hair,E.C.(2020). Efects ofmultiple exposures and ad-skipping behavior on recallof health messages on youtubetm.International Journal ofEnvironmental Research andPublic Health,17(22),8427-8435. [53] Ruiz,S.,& Sicilia,M.A. (20o4).The impact ofcognitive and/or affective processing styles on consumer response to advertising appeals. Journal of Business Research,57(6), 657-664. [54] Sahni,N.S.,& Nair, H. S.(2O20).Sponsorship disclosure and consumer deception: Experimental evidence from native advertising in mobile search. Marketing Science, 39(1),5-32.   
[55] Semaan,R.W.,Gould,S., Chao,M. C.-h.,& Grein,A.F.(2019).“We don't allsee it the same way": The biasing effects of country-of-origin and preference reversals on product evaluation. European Journal of Marketing. 53(5), 989-1014.   
[56] Seyedghorban,Z.,Tahernejad,H.,& Matanda,M.J. (2016). Reinquiry into advertising avoidance on the internet: A conceptual replication and extension. Journal of Advertising, 45(1),120-129.   
[57] Sharma, P., Sivakumaran,B.,& Marshal,R. (2Ol0). Impulse buying and variety seeking: A trait-correlates perspective.Journal of Business Research, 63(3),276-283.   
[58] Siefert, C., Gallent,J,Jacobs,D,Levine,B., Stipp,H.,& Marci, C. (20o). Biometric and eye-tracking insights into the eficiency of information processing of television advertising during fast-forward viewing. International Journal of Advertising,27(3),425-446.   
[59] Speck,P.S.,& Ellot, M.T. (1997).Predictors of advertising avoidance in print and broadcast media. Journal ofAdvertising,26(3),61-76.   
[60] Teixeira,T.S., Wedel, M.,& Pieters,R. (2010). Moment-to-moment optimal branding in tvcommercials: Preventing avoidance by pulsing. Marketing Science,29(5),783-804.   
[61] Thompson, D.V.,& Hamilton,R. W. (2oo6).The effects of information processing mode on consumers' responses to comparative advertising. Journal of Consumer Research,32(4), 530-540.   
[62] Vilas-Boas,J.M.,& Yao,Y. (2021).Adynamic model of optimal retargeting. Marketing Science, 40(3), 428-458.   
[63] Wang,P., Xiong, G.,& Yang, J. (2019).Serial position effects on native advertising effectiveness: Differential results across publisher and advertiser metrics.Journal of Marketing, 83(2),82-97.   
[64] Wojdynski,B.W.,Bang,H.,Keib,K.,Jefferson,B.N.,Choi,D.,&Malson,J.L. (2o17).Buildingabter native advertising disclosure.Journal of Interactive Advertising, 17(2),150-161.   
[65] Wojdynski,B.W.,& Evans,N.J. (20l6). Going native: Effects of disclosure position and language on the recognition and evaluation of online native advertising. Journal of Advertising, 45(2),157-168.   
[66] Wojdynski,B.W.,& Evans,N.J. (2O2O).The covert advertising recognition and effects (care) model: Processes of persuasion in native advertising and other masked formats. International Journal of Advertising, 39(1), 4-31.   
[67] Yang,D,Lu,Y.,Zhu, W,& Su, C.(20l5).Going gree: Howdifferentadvertising appeals impact green consumption behavior.Journal of Business Research, 68(12),2663-2675.   
[68] Yang,J.,&Jiang,M. (2O21).Demystifying congruence efects in instagram in-feed native ads: The role of media-based and self-based congruence.Journal of Research in Interactive Marketing,15(4), 685-708. [69] Yoon,S.(2Ol3). Do negative consumption experiences hurt manufacturers or retailers? The influence of reasoning style on consumer blame atributions and purchase intention. Psychology& Marketing,30(7),55-565 [70] Youn, S., & Kim, S. (2019). Newsfeed native advertising on facebook: Young milennials' knowledge, pet peeves,reactance and ad avoidance. International Journal of Advertising, 38(5), 651-683.   
[71] Yu,J. (2021).A model of brand architecture choice: A houseof brands vs.a branded house.Marketing Science,40(1),147-167.   
[72] Zhang,L.,Peng,T. Q., Zhang,Y.P., Wang, X.H.,& Zhu,J.J. (2014). Content or context: Which matters more in information processing on microblogging sites. Computers in Human Behavior, 31(2),242-249. [73] Zhou,L.,& Xue,F.(2O19). In-feed native advertising on news websites: Effects ofadvertising format, website reputation,and product involvement.Journal of Internet Commerce,18(3),270-290.   
[74] Zhuang, G., Xia,J.,Sun, W.,Feng,J. e.,& Ma,Q. (2021). Asynchronous admissibility and fault detection

for delayed implicit markovian switching systems under hidden markovian model mechanism. International Journal ofRobust and Nonlinear Control,31(15),7261-7279.

（通讯作者：肖邦明 E-mail:bangmingshaw@163.com）

作者贡献说明：  
张皓：论文命题提出与设计；肖邦明：模型建构与论文修改；黄敏学：模型建构