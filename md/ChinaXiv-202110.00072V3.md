# “有声有色”的触觉体验：来自多感觉通道整合的线索\*

万必成马 舒　杨 振 李宏汀(浙江理工大学心理学系，杭州310018)

摘 要虚拟现实技术通过提供视觉、听觉和触觉等信息为用户创造身临其境的感知体验，其中触觉反馈面临诸多技术瓶颈使得虚拟现实中的自然交互受限。基于多感官错觉的伪触觉技术可以借助其他通道的信息强化和丰富触觉感受，是目前虚拟现实环境中优化触觉体验的有效途径。本文聚焦于触觉中最重要的维度之一一—粗糙度，试图为解决虚拟现实中触觉反馈的受限问题提供新思路。探讨了粗糙度感知中，视、听、触多感觉通道整合的关系，分析了视觉线索(表面纹理密度、表面光影、控制显示比)和听觉线索(音调/频率、响度)如何影响触觉粗糙度感知，总结了当下调控这些因素来改变粗糙度感知的方法。最后，探讨了使用伪触觉反馈技术时，虚拟现实环境中视、听、触觉信息在呈现效果、感知整合等方面与真实世界相比可能存在的差异，提出可借鉴的改善触觉体验的适用方法和未来待研究的方向。

关键词 粗糙度知觉，多感觉通道整合，视觉线索，听觉线索分类号

# 1引言

近年来，虚拟现实(Virtual Reality,VR)技术发展迅速，它通过头戴式显示器(Head MountedDisplayed,HMDs)等设备为用户提供视觉、听觉和触觉信息，展现虚拟现实环境(Virtual RealityEnvironment, VRE)(Lin etal.,2017)，创造身临其境的用户体验(Gunther et al.,2019)。然而，相较于市场上各种虚拟现实的视觉和听觉显示技术及产品的成功商业化，触觉信息呈现仍然面临着巨大的挑战 (Kang&Lee,2018)。现有的触觉反馈设备可分为接地式、手持式和可穿戴式三类，这些设备主要有以下一些问题：设备不够轻巧便携或不易操作；设备提供触觉感受的逼真度和人类触觉感知还相差甚远；现有设备无法同时提供多种不同的触觉感受；硬件设备开发、制造价格高，难度大(Bosman,2018; Culbertson etal.,2018; Ujitoko et al.,2019a; Ujitokoet al.,2019b;Wang etal.,2019)。因此，相较于目前虚拟现实环境中丰富的视听信息呈现，良好的触觉反馈仍然有所缺乏(Bosman,2018)。

利用多感官错觉(Intersensory Ilusion)来弥补虚拟现实环境中缺乏的触觉反馈，可能是缓解上述问题的途径之一(Bosman,2018)。多感官错觉是一种通过一个通道的刺激来影响或引发另一个通道感知的跨通道错觉现象(Bizley et al.,2012)。近年来在虚拟现实环境中广泛引起人们关注的伪触觉反馈技术(Pesudo-Haptic Feedback Techniques)(Aoyama et al.,2016; Bi et al.,2018; Kawabe,2019; Samad etal.,2019)或许源自于多感官错觉这一理论基础。伪触觉反馈技术由 Lecuyer 等人(2000)提出，其是一种不依赖于触觉反馈，而通过跨感觉通道(Crossmodal)信息来呈现触觉感知的技术(Kang& Lee,2018; Ujitoko et al.,2019b)。在电脑界面或虚拟现实环境中，可以通过伪触觉反馈技术灵活改变虚拟物体的视觉显示，从而模拟物体的重量(Bietal.,2018; Hirao et al.,2020; Samad et al.,2019)、硬度(Kawabe,2019; Liet al.,2016; Matsmoto etal., 2016)和粗糙度(Ota et al.,2020; Sato et al.,2020; Ujitoko et al.,2019a)等触觉感知。基于多感官错觉的伪触觉反馈技术允许用户更自由的交互，并且规避了如设备使用疲劳，硬件时间和空间分辨率低等问题(Hirao et al., 2020)。该技术不仅能有效帮助用户感知虚拟现实环境(Hashimoto et al.,2018; Ramirez etal.,2018)，还可以提升现阶段虚拟技术的沉浸感(Kang& Lee,2018; Samad etal.,2019)。总的来说，基于多感官错觉的伪触觉反馈技术可能是当今感知错觉在界面显示技术(Kawabe,2019)、虚拟信息显示技术中最成功的应用之一。

应用伪触觉反馈技术来营造良好的触觉感受，依赖于操纵非触觉信息创造触觉的多感官错觉。视觉、听觉和触觉是人类识别和感知环境的主要通道，但在虚拟现实环境中，则更依赖于视觉和听觉与虚拟对象进行交互(Ramirez etal.,2018)。一方面，由于当下技术发展的限制，触觉信息呈现存在诸多局限性，而视觉和听觉信息更容易在虚拟现实环境中呈现；另一方面，许多研究已经证明，人类可以有效利用视觉信息来感知材料的硬度，刚度和粗糙度等触觉特性(吴淼,2019; Bi et al.,2018; Paulun et al.,2017; Schmidt et al.,2017)。听觉和触觉在感知层面上非常相似(Bosman,2018)，因为触摸物体产生的振动和声音信息都是波信号，它们共享频率和振幅等物理特性，这使得它们在强度、频率/速度和粗糙度/纹理等属性上产生映射(Hoggan&Brewster,2007)。综上所述，在虚拟现实环境下，通过操纵视觉和听觉信息来诱发触觉感知是非常有潜力的。然而，前人研究并未明确视觉和听觉中影响触觉感知的因素是什么，因此有必要探讨和明确视听线索中影响触觉感知的因素，并通过操纵相关的视听觉因素在虚拟现实环境中营造更加真实和丰富的触觉体验。

而在触觉的多个不同感受维度上，本文聚焦于粗糙度这一维度，主要有以下原因：首先，从感知层面上来说，在触觉感知研究领域中，有大量研究聚焦于对纹理粗糙度感知的探究(Klatzky & Lederman,2010)。表面粗糙度的感知是纹理触觉定义中的一个重要维度，在一定条件下，粗糙度甚至可以作为触觉感知的量度(Okamoto et al.,2013; Ujitoko et al.,2019a; Wangetal.,2019)。其次，食品、家具、织物、汽车等表面的粗糙质感会直接影响消费者对于产品的偏好(Aktar etal.,2017)，因此，用户对产品表面纹理的感知对商业成功至关重要。最后，聚焦于触觉的粗糙度这一维度，也有助于更细致的探讨视听线索如何影响粗糙度感知，明确可以操纵的视听因素。综上所述，本文关注虚拟现实环境中缺乏良好触觉反馈这一问题，讨论视觉、听觉同触觉在粗糙度信息整合中的关系，并详细探讨、分类视觉和听觉中影响粗糙感知的因素。

# 2视觉、听觉和触觉的粗糙度信息整合

或许人们普遍认为，触觉在材料表面粗糙度的感知中占据了绝对优势，但是相关研究表明，除了触觉以外，视觉和听觉信息也在粗糙度感知中发挥了作用。正如Weisenberger &Poling(2004)所说：“人们对于物体表面纹理粗糙度的感知是一个对视觉、听觉和触觉信息进行整合的过程。”既然如此，人类在粗糙度的感知中多大程度的利用了视觉和听觉信息呢？

Ernst& Banks(2002)指出，在视觉和触觉信息整合的过程中，噪音更少，信息更为可靠的通道将占有较高的权重。Ledrman(1981)表明，视觉通道能频繁的获取、使用材料表面纹理的信息，因此在粗糙度感知方面，视觉信息具有很高的可靠性。Jones&O'Neil(1985)发现，视觉单通道条件下的粗糙度匹配准确性不逊于触觉单通道的准确性，甚至更好。这些结果均说明，视觉信息可能因为其较高的可靠性而在粗糙度的信息整合中占据不小权重。此外，模态适当性假设表明，当对事物特定维度的感知更适合通过某一通道完成时，这一通道会在感知判断中占据最大权重(Weisenberger& Poling,2004)。Lederman 等人(1986)指出，在人类感受材料的粗糙度时，会依据任务类型的不同而依赖不同的感觉通道：当被试的任务是判断表面纹理的空间密度时，会更依赖于视觉线索；而当被试的任务是判断表面的粗糙程度时，则更依赖于触觉线索。该研究结果似乎说明视觉通道不那么适合粗糙度感知的任务，但 Lederman等人(2003)解释：该研究结果说明被试虽然可以理解“空间密度”和“粗糙度”的差异，但在日常生活中感知材料表面的粗糙度时，他们则会将材料表面纹理的“空间密度”这一视觉信息作为粗糙度的感知线索，这表明视觉通道也适合粗糙度感知任务。

上述研究虽然说明了视觉通道在粗糙度感知层面具有较高的可靠性，具备执行粗糙度感知任务的能力，但并未清晰指出视觉在多通道的粗糙度知觉中占有多少权重。Lederman &Abbott(1981)的研究则量化分析了视觉在多通道粗糙度知觉评估中的权重。在他的实验中，被试需要在视觉，触觉单通道和视触双通道条件下对材料的粗糙度进行匹配，因此可以得到三种条件下的粗糙度估计值。此时使用下式，就可以计算出视觉和触觉信息在双通道知觉任务中所占的权重。

注：式中Mean(Modality standard)指的是在一个标准刺激的通道下，做出的与标准刺激匹配的粗糙度的均值。实验中触觉的标准刺激是60 目的砂纸，视觉的标准刺激是150目的砂纸，双通道的标准刺激是60目的砂纸作为触觉体验，而150目的砂纸作为视觉体验。例如，Mean(T standard)即为被试使用60 目的砂纸作为标准刺激时，从40，50，60，80，100，120,150，180，220 目砂纸中所选择来匹配标准刺激的砂纸粗糙度的均值。值得注意的是，双通道条件下的粗糙度知觉总在两个单通道的匹配值之间，因此在笔者看来 Mean(V standard)Mean(T standard)即为双通道条件下粗糙度评估值的区间，而式中分子部分则表示的是双通道条件下粗糙度评估值向单通道偏移的部分，即单通道的影响力。  
通过上述方法，Lederman&Abbott(1981)计算出在视触双通道粗糙度感知中，视觉信息的平均比例为 $4 9 . 3 \%$ ，触觉信息的平均比例为 $5 0 . 7 \%$ 。这一结果同前人推测视觉通道在粗糙度感知任务中有重要影响的结论相吻合，说明被试在视触双通道的粗糙度信息整合过程中，倾向于对表面纹理相关的视觉和触觉信息进行同等的加权。

这一范式也被用来研究听觉和触觉多通道粗糙度信息整合的权重问题。虽然在早期，人们认为听觉信息容易被环境中的噪声所掩蔽，因此在听触双通道粗糙度信息整合中几乎不起显著的作用(Lederman,1979)。 但 Lederman 等人(1999)和 AItinsoy(2008)两位学者的研究表明，一旦声音的响度提高，被试就可以有效的将听觉信息纳入粗糙度感知中，并且利用上述范式，计算出听觉信息在听触双通道粗糙度感知中的占比：Lederman 等人(1999)的实验结果是听觉占 $3 8 \%$ （触觉占 $6 2 \%$ ，Altinsoy(2008)的实验结果是听觉占 $4 0 \%$ 触觉占 $6 0 \%$ L。

总的来说，视觉和听觉信息在多通道的粗糙度信息整合过程中都占有不小的权重，其中视觉信息甚至有可以匹及触觉信息的重要作用，而听觉信息在有效被人类获得时也有着不可忽视的作用。正如上文中提到的，视觉信息能占据如此权重的原因可能是因为视觉和触觉一样，都可以频繁地获得和使用关于纹理的信息，因此对于粗糙度感知任务来说，这两个通道的信息都具有可靠性(Ledrman,1981)。相比之下，听觉信息因为其容易被环境噪声掩蔽的特点，不如触觉通道的信息可靠。但并不能说听觉信息在多通道的粗糙度信息整合中就毫无作用。前人的研究已经证实，略微增加听觉线索的响度就可以大大提高听觉信息在多通道粗糙度知觉中的权重(AItinsoy, 2008; Lederman et al.,1999)。视觉和听觉信息对于粗糙度的感知都颇为重要，而人类究竟利用了视觉和听觉信息中哪些线索来感知材料的粗糙程度呢？在缺乏良好触觉反馈的虚拟现实环境中，探讨这一问题有助于更好的利用和调控视听通道中影响粗糙度感知的线索，通过呈现视听通道的信息，改善人类对于材料表面粗糙度的感知。

# 3视觉线索和粗糙度知觉

早期的一些研究表明，被试可以仅凭视觉线索有效分辨不同粗糙程度的表面(Jones &O'Neil,1985; Lederman&Abbott,1981)。至今为止，学者们已对视觉中影响粗糙度感知的因素做了进一步的研究。本章把这些因素分为静态线索(表面纹理密度、表面光影)和动态线索，将在下文中详细介绍。

# 3.1静态线索

# 3.1.1表面纹理密度

现实生活中的表面纹理大多是非线性和随机特征的，为了减少分析的困难，增加对条件的控制，大多早期对粗糙度感知的心理物理学研究都集中于两类被简化的粗糙度刺激：凸起圆点表面(如砂纸等)和挖槽表面(如留声机的蚀刻板等)(AItinsoy,2008)。对于凸起圆点表面而言，圆点的间距和半径是影响粗糙度感知的主要因素(吴淼,2019)。研究者通常改变圆点间距使得材料表面呈现出不同的纹理密度。随着圆点间距减小，即表面密度增加，被试也越发感知材料表面粗糙度上升。以砂纸为实验材料的粗糙度感知研究也可以说明圆点颗粒半径和颗粒间距对粗糙度感知的影响：随着砂纸颗粒半径增大，颗粒间距减小，被试在视觉单通道、触觉单通道、视触双通道条件下都觉得砂纸变得更为粗糙(Jones &O'Neil,1985; Lederman &

Abbott,1981)。挖槽表面这类材料上光栅的周期和振幅是影响粗糙度感知的因素(Wall &Harwin,2001)。随着光栅周期增大，视觉、触觉和视触双通道条件下的粗糙度感知差别阈限都随之升高；随着光栅振幅增加，上述三个条件的粗糙度感知差别阈限则随之降低(Poling etal., 2003)。

总的来说，不论是凸起圆点表面的圆点直径、圆点间距，还是挖槽表面光栅周期的变化，在视觉上都表现为纹理密度的改变。当圆点直径增大，间距减小，或是光栅周期减小，对被试来说都表现为视觉上材料表面纹理密度的增加，被试对材料粗糙度的感知也随之升高。视觉信息在视触双通道的粗糙度感知中举足轻重(Etzi etal.,2018;Jones&O'Neil,1985;Lederman& Abbott,1981)，因此前人研究结果的得出，对于触觉反馈设备的设计创新将大有裨益。

# 3.1.2表面光影

在视觉层面，物体表面的纹理结构是日常生活中最容易关注到的纹理线索，但将物体置于外界坏境中时，环境中的光线，物体表面对光线的镜面反射又为其带来了新的粗糙度感知线索(Honson et al.,2020)。Ho 等人(2006)指出，当物体表面入射光的角度不断减小时，物体表面将产生更多的阴影，这会使得物体显得更加粗糙。照明方向的变化会产生新的纹理线索(Ho etal.,2007)：阴影在表面的比例；非阴影部分的平均亮度；非阴影部分亮度的标准差;纹理对比(用亮度的第95个百分位数和第5个百分位数除以中值亮度的差值来计算，是表征不同光照条件下材料特性的统计量)。尽管这些线索有时不能准确表明材料的粗糙程度，但人们仍然会利用这些“伪视觉线索”来判断表面粗糙度(Ho etal.,2007)。除此之外，人们也常利用物体表面的光泽度来判断其粗糙程度。因为当物体表面越光滑时，平行光线射入表面，反射光线趋近平行，趋近镜面反射，光泽度高；而当物体表面越粗糙(凹凸不平)，平行光线射入表面，反射光线射向各个方向，趋近于漫反射，光泽度低。目前研究主要聚焦于金属材料的粗糙度判断，实验发现，金属表面光泽度越低，人们觉得其越粗糙(Todd&Norman,2018)。Adams 等人(2016)通过控制物体的镜面反射性探究了物体光泽度和表面粗糙度的关系，实验表明，即使在视觉上被试很容易识别出光泽度的增加，但当标准刺激和一个实际更粗糙但是视觉上更有光泽度的刺激物做比较时，被试则难以凭借视觉和触觉信息分辨哪个更粗糙。至于其他材料，光泽度也会影响被试对材料表面粗糙度的判断，甚至因为光泽度的相似，将粗糙度完全不同的材料混淆(Vardar etal.,2019)。表面光影这一视觉的粗糙度线索，从环境光照以及材料的反光特性这两个角度，丰富了虚拟现实环境中静态物体粗糙度的表现形式。虚拟现实环境中光源设置灵活，定向光源、点光源等光照下，物体表面粗糙度将有不同表现。而如何将环境光源和物体光泽度渲染结合起来更好的展现材料粗糙度，还需在未来继续探究。此外，在虚拟现实环境中增加材料表面光泽度以减小其粗糙程度时，还应注意保留材料原本的特性。

# 3.2动态线索

表面纹理结构和表面光影都属于静态的视觉线索，而在虚拟现实环境中，还可以给物体添加动态视觉线索以改变人类对其粗糙度的感知。操纵控制显示比(Control Display Rate,CDR)就是最常用的方式之一。CDR 是人机交互(Computer Human Interaction,CHI)领域中一个著名的无单位参数(Lecuyer etal.,2000)，它将定点设备的移动映射到显示器上指针的移动。当 CDR比为1.0 时，指针的移动速度与控制装置完全相同。当CDR 比大于1.0时，与控制装置相比，指针以更快的速度移动更远。当CDR比小于1.0时，指针移动较慢，覆盖的距离小于控制设备(Hashimoto et al.,2018)。Lecuyer 等人(2000)的实验就通过设置 CDR 值在屏幕中创建了一块灰色区域，当被试通过移动光标控制屏幕中虚拟方块移动到至灰色区域时，物块会表现出明显的运动速度减缓，被试则会显著感受到这块灰色区域的摩擦阻力更大。Hannig&Deml(2008)的实验也控制了CDR 探究在虚拟现实环境中视觉动效和粗糙度感知的关系。在虚拟现实环境中，人手运动和显示器中虚拟手的运动比率通常是相等的(即 $C D R = 1 1$ ，而在这个实验中，触摸作为比较刺激的虚拟物块时会触发相应的CDR变化，表现为虚拟手运动的更快或更慢；触摸标准刺激时，虚拟手运动速度不变 $( C D R = 1 )$ 。研究结果表明，CDR 的变化显著影响了被试对虚拟物体表面粗糙度的判断，在虚拟现实环境中， $C D R > 1$ (虚拟手减速)代表粗糙的表面，CDR<1(虚拟手加速)则代表光滑的表面。Sato 等人(2020)通过设置 CDR 操纵虚拟手触摸物体时的运动速度，在混合现实环境中进行了类似的实验。研究结果表明当手部运动更快时，被试对物体会有更光滑的感知，而手部运动速度慢时则会感觉物体更为粗糙。

除了通过设置CDR 值来控制指针(光标或是虚拟手)运动的速度，还有一些学者赋予指针以特殊的运动方式来表现虚拟物体的粗糙度。在Ujitoko 等人(2019a)的一项研究中，当被试用手写笔在设备表面滑动时，他们会看到指针略微卡顿，似乎被黏住了一样，表现的比真实笔尖移动滞后，而这样的一种方式也显著让被试感受到了虚拟界面的粗糙质感。此外，Ujitokc等人(2019b)还使得指针颤动给被试带来虚拟表面的粗糙感。在他的实验中，被试通过电子笔在屏幕上写字，当光标在书写同时表现出振动，被试会认为虚拟表面更加粗糙。且随着视觉上这种振动的增大，被试对虚拟表面粗糙度的感知也增强。Ota 等人(2020)还将这种振动的方式扩展到了手指与虚拟表面的交互：被试用手指触摸实验材料，观察到界面上指针不断振动，同时评估材料的粗糙度。结果表明视觉线索的振动可以显著改变被试对真实纹理表面的粗糙度感知。

总的来说，不论是设置CDR 值以控制指针的相对运动速度，还是赋予指针特殊的运动规律来表现虚拟物体的粗糙度，都是将自然界中一个物体和另一个粗糙物体交互时发生的运动规律在虚拟现实环境中表现出来的方法。在自然界中，粗糙的地面往往会有更大的摩擦阻力，如果没有额外的动力，在这样的地面上运动物体的速度显然会越来越慢。前人研究中指针的低速和粘连的运动规律便是利用了这一点(Lecuyer et al.,2000; Hannig& Deml,2008;Ujitoko etal.,2019a)，而 Ujitoko 等人(2019a)和 Ota 等人(2020)的研究将指针在视觉上的振动和粗糙度感知联系了起来，这令人眼前一亮。虽然这也是自然物理规律的一部分，但他们超出了对视觉线索运动速度的控制，而是改变了视觉线索的运动规律。应用这种将真实的物理规律巧妙的嵌入虚拟世界的方法，或许能给予虚拟现实环境的探索者更真实和丰富的感官体验。

# 4听觉线索和粗糙度知觉

Lederman(1979)一项关于听觉和触觉线索对表面粗糙度感知的研究发现，听触双通道条件下的粗糙度函数评估曲线几乎与触觉单通道的结果重合，并且和听觉单通道的结果差异显著，这说明一旦被试能够获得触觉线索，他们会依赖于触觉线索来感知材料表面，而几乎不使用听觉线索来判断表面的粗糙度。Suzuki等人(2006)的研究也得到了相似的结果。

然而听觉线索对于粗糙度的感知并非没有影响，正如 Klatzky& Lederman(2010)所指出，伴随着触觉的听觉线索对知觉起到了重要的贡献。大量前人研究表明，只要能够有效获得听觉线索(即听觉线索不被环境噪声掩蔽)，人类对于粗糙度的感知就会受到听觉线索的影响(Etzi et al.,2018; Guest et al.,2002; Kim et al.,2007; Lederman,1979; Jousmaki& Hari,1998)。而在听觉线索中，响度和音调/频率是影响粗糙度知觉多通道信息整合的主要因素。例如Altinsoy(2008)的研究发现了听觉线索响度对于粗糙度感知的影响。他将实验的声音响度提高了10分贝，用绝对估计法探究被试在三种通道(听觉、触觉、听觉 $^ +$ 触觉)条件下的粗糙度知觉。比起上文中 Lederman(1979)研究结果中触觉单通道和听触双通道粗糙度评估函数曲线几乎完全重合的情况，AItinsoy(2008)得到了触觉单通道和听触双通道差异显著的结果，这说明增加声音的响度，可以增加听觉在听触整合的粗糙度判断中的权重。 Peeva 等人(2004)的一项相关性研究表明，被试将不同的纹理和声音进行匹配时，更容易将响度更大的声音和更粗糙的表面匹配在一起，同时他还发现，音调和粗糙度也有着强相关性。AItinsoy(2004)的实验也证实了音调和粗糙度的关联：被试能够准确的将相同频率的振动和声音线索匹配起来。由此不难得出，听觉线索中的响度和频率的变化是引发粗糙度知觉变化的重要因素。下文将对这两个因素分别做详细讨论。

# 4.1响度

较小的摩擦声容易被环境噪声所掩蔽，因此人类难以有效利用声音线索来判断物体的表面纹理等属性(Lederman etal.,1999)。Lederman(1979)研究了在三种通道(听觉单通道，触觉单通道，听触双通道)条件下被试对于铝板表面的粗糙度感知，其中听觉线索在实验人员录制好后向被试播放。当被试使用更大的力度摩擦铝板时，会知觉到更大的粗糙度。显然在触觉单通道条件下，更大的摩擦力会带来更大的粗糙感(Lederman&Taylor,1972)，而在听觉单通道条件下，则是因为大力度摩擦提高了录制声音的响度，才使得粗糙度的评估值显著上升。Lederman 等人(1999)在用刚性探针探究粗糙度知觉的研究中也得到了类似的结果。他认为这是由于摩擦主体从手变成刚性探针以后，声音的响度变大了，才使得被试感觉材料表面变得更加粗糙。

除了直接增加全频声音的响度可以使得被试感觉材料变得更加粗糙，声音中特定频率成分的调制也能对粗糙度感知产生影响。Jousmaki& Hari(1998)将被试双手摩擦声音的响度进行调制(2kHz以上的高频成分或是全频率响度调制)，在被试进行实验摩擦双手时播放这种调制后的声音。全频率段和高频段的响度增加，被试都产生了双手变得更加粗糙和干燥的错觉体验，而响度减小，被试则知觉手部变得光滑和湿润，这种错觉被称为纸皮错觉。Guest 等人(2002)同样将响度调制锁定在了声音的 2kHz 以上的高频段部分进行了相关探究，他检测了被试通过触觉线索和调制过的声音线索做粗糙度匹配任务的反应时间和错误率，结果表明被试更倾向于将响度更大的声音和更粗糙的表面匹配起来。Zampini 等人(2003)在一项关于产品体验的研究中也对声音高频成分的调制进行了探索，这项研究调查了电动牙刷粗糙度和愉悦度感知是否会受到它所发出声音的影响。结果表明，不论是整体响度或是高频音响度增加，被试都认为牙刷更加粗糙并带来不适感。此外，Suzuki 等人(2006)和 Kim 等人(2007)还对声音的中低频成分进行响度调制的实验(前者是对 25Hz至6.3kHz，后者是对300 至 600Hz频段的调制)，结果同样表明声音的响度调制对粗糙度知觉造成了影响。

虽然听觉线索的响度提高确实会带来更粗糙的知觉体验，声音中特定的频率成分也与粗糙度知觉有关，特别是高频成分的响度调制已被众多学者证实会影响粗糙度的评估，但是对于频率成分与粗糙度知觉的研究较少，频段响度和粗糙度知觉的关系尚未有明确定论，因此仍需要对这些频率成分和粗糙度知觉的关系做进一步的探究。

# 4.2音调/频率

除了响度这一特性以外，音调也被发现和粗糙度知觉有强相关性(Peeva etal.,2004)。Eitan& Rothschild(2011)探究了A4，A5，A6(分别对应 220Hz，440Hz，880Hz)三阶音调和粗糙度的关系。实验中被试仅获得听觉线索，并评估听觉线索的粗糙程度。结果表明，更高的音调意味着更粗糙的知觉体验，更低的音调则会使人感觉到更光滑。音调主要是由声波频率决定的听觉特性，声波的频率不同，人类听到的音调高低也不同。前人们对音调和粗糙度关系的研究相对较少，有些学者直接调制声音的频率来探究这一特性和粗糙度的关系。Altinsoy(2008)用调制频率的声音做了粗糙度评估实验，发现了趋势相反的结果。AItinsoy(2008)将手指滑动挖槽板材的槽与脊摩擦产生的振动频率定义为手部运动速度和板材物理属性的函数：

$$
\operatorname { f } = \mathrm { v } \mathrm { ~ r ~ / ~ L ~ }
$$

注：式中f是振动的频率， $\mathsf { v }$ 是手部运动速度，r是板材总脊数，L是板材的长度。通过计算机模拟出各种不同频率(56至112Hz)的声波作为听觉刺激，探究频率和粗糙度知觉的关系。实验发现即使触觉材料不变，当声音的频率变高时，被试知觉到的粗糙度显著降低，反之则显著增高。

Egmond 等人(2009)的研究则给频率和粗糙度知觉的关系提供了另一种可能：实验比较了 $1 0 mathsf { H z }$ ，50Hz，70Hz，200Hz，350Hz五种声音对应的粗糙度知觉，发现五种音频对应的粗糙度知觉和调制频率呈近似倒U型的曲线，并且在70Hz时粗糙度评估值达到峰值。这个现象说明频率和粗糙度知觉是非线性的关系(据此推测音调也是如此)：当选择频率与粗糙度感受函数的不同单调区间，将会得到相反的关系变化趋势。而单调区间具体如何分区，由于Egmond 等人(2009)在 70Hz与 200Hz之间没有采集频率样本，实验条件中 70Hz之后是否粗糙度知觉仍然会随着频率升高而增大不得而知。且由于粗糙度知觉并非受到频率单个因素的影响，不同实验条件下，如响度不同的声音，是否会出现频率和粗糙度知觉峰值的变化，也

仍然需要进一步的实证探索。

此外，对音调或是频率进行调制还存在一些应该注意的问题。首先，频率是描述听觉信号波周期运动频繁度的物理量，它和触觉振动存在的强大映射关系是科研工作中对其调制的原因所在(Bosman,2018)，但目前对于频率调制的声音多为计算机合成音(AItinsoy,2008;Bosman,2018;Egmond,2009)，缺乏自然声源的生态性。其次，在不同的频率下，人对不同声强的敏感性存在差异。前人对于等响曲线的研究很好的说明了声强和频率这两个物理量都是心理量响度的影响因素，因此，在解释粗糙度知觉中听觉影响因素时，应该注意更好地区分这几个概念。最后，白噪声和听觉适应会提高触觉对粗糙度感知的差别阈限，降低触觉对粗糙度和振动的感受性(Crommett et al.,2017; Suzuki et al., 2008)，因此在分析听触觉双通道条件的实验结果时，应考虑到环境噪声的影响。

# 5总结和展望

本文以粗糙度知觉为切入点，关注在虚拟触觉设备存在诸多局限性的当下，如何通过视、听感觉通道信息来辅助提升虚拟现实中的触觉体验。首先从感知觉信息加工的角度分析粗糙度知觉的形成，论证得出在粗糙度知觉的多感觉通道整合中视觉和听觉信息的重要性。继而进一步探讨和分类了视觉和听觉中会影响粗糙度感知的因素，并总结了当下对这些因素的操纵方法，以期在缺乏良好触觉反馈的虚拟现实环境中，利用视觉和听觉信息，改善人们对于材料表面粗糙度的感知。在探索和实践中，仍有一些问题值得进一步讨论。

首先，在虚拟现实环境中呈现多感觉通道信息的前提是单通道信息的呈现。因此，有必要分别探明视觉、听觉和触觉通道信息在虚拟现实环境和现实环境的呈现存在什么差异。

视觉信息作为目前虚拟现实环境中最主要的信息来源，其与现实环境最大的差异主要源于虚拟视觉的渲染质量的高低。虚拟现实环境中的视觉渲染主要包括阴影柔和度(阴影边缘的锐度)、表面平滑度、纹理质量、几何形状、光照和颜色等因素(Kapralos etal.,2017)。兼顾上述渲染效果，虽然可以为用户带来最好的虚拟视觉体验，但是会增加渲染成本，增加虚拟设备的运载负荷。而劣质的视觉渲染则会影响用户对虚拟现实环境的感知(Malpica et al,2020)。更为高效且节约成本的方法应是先确定任务场景，再于虚拟现实环境中找到满足用户对其认知需求的最小渲染参数。

在听觉层面，虚拟现实环境中音频的实时性是弱于现实环境的。人类与环境交互(在此专门指触觉交互)发出声音，交互方式、力度和速度的变化都会引发声音的改变。例如，敲击和摩擦的声音显然不同，力度影响音频响度，速度影响音频频率(Lederman，1979)。在现实环境中，依据交互属性的不同，人类可以即时获得不同的听觉信息。但在虚拟现实环境中，想要依照人类的交互变化即时呈现不同的听觉信息是有困难的，极易出现交互属性和听觉信息不匹配的现象。这种不匹配不仅破坏人类在虚拟现实环境中的沉浸感，也有可能影响人类对于交互材料的感知。然而交互属性和听觉信息的完全匹配成本过高，且依赖定位识别技术的高度发展。因此，将不匹配的差值控制在人类的感知阈值之下或许是个好的解决办法。在未来的科研探究中，探明交互属性同听觉信息跨模态匹配的差别阈限，亦能为今后物理技术的发展提供人因学的依据。

目前，虚拟现实环境中的触觉设备只能提供较为单一且精度低的触觉感受。现在的技术只能同时为用户提供一至两种维度的触觉感受，而现实环境中人类则可以同时获得粗糙度、温度、硬度等多维度触觉体验。虽然前人已经广泛测量了单一触觉维度的绝对和差别阈限，但当多维度的触觉信息同时呈现时，绝对和差别阈限将会产生的变化还有待探究(Wang et al.2019)。此外，即使在某一限定的触觉维度内，物理设备的反馈精度也远不及人类触觉感受器的精度。因此，在未来触觉设备研发过程中，不仅要攻克多维度触觉信息呈现的技术难题，还要使得触觉设备提供信息的精确度更接近人类触觉感知的精确度(Culbertson et al.,2018;Wang et al., 2019)。

其次，在虚拟现实环境中，单通道的感觉信息呈现存在不同程度的偏差，一方面，发展先进的技术可以渲染和呈现更逼真的感觉信息；另一方面，可否利用知觉加工规律，有侧重地、适时地提供和当下感知场景或任务更适配的感觉刺激信息呢？例如：人类在空间分辨任务中更依赖视觉信息，在时间分辨任务中更依赖听觉信息，在精细操作的交互任务中更依赖触觉信息。因此，站在应用实用性的角度来说，在不同的任务需求里提供足够的、适用的信息，使被试的操作绩效达标且获得较好的用户体验才是关键。正如 Malpica 等人(2020)在虚拟现实环境中材料辨别实验的结果：即使弱化视觉渲染效果，被试依然能凭借听觉线索有效感知和辨别不同质地的实验材料。因此，若虚拟现实环境中的触觉设备不足以提供可辨别的粗糙质感，将听觉信息或视觉信息辅助触觉信息来提供更好的粗糙质感也是值得探究的方向。

第三，还应该考虑：虚拟现实环境中单通道的视、听、触觉信息和现实环境中存在的差异，很可能导致不同通道间信息的不匹配。那么将如何整合原本存在差异、并且彼此间不尽匹配的多通道感觉信息呢？这一过程势必进一步加剧虚拟和现实感知觉信息加工的不同，带来新的问题。Ernst& Banks(2002)认为在多通道信息整合的过程中，信息更为可靠的通道将占据更多的权重。而本文在上述讨论中已经确定，虚拟现实环境下各个感觉通道的信息均和现实中原本感觉通道的信息存在差异：纹理质量的弱化，听觉信息和交互行为的不匹配，触觉感受的单一。这些差异使得各通道信息都不那么“可靠”，那人类在虚拟现实环境中会更依赖哪个通道呢？虚拟现实环境中的多通道信息整合的权重分配，究竟和现实环境中的这一过程有多大差别？对于这类问题的探究，不仅有助于理解虚拟信息和现实环境在感知上的差异，还将有助于定向优化人类在虚拟现实环境中失真的那部分感觉信息。

最后，总览前人所做的工作，这些研究大多从视觉、听觉、触觉单通道，或是双通道的角度探究了相关感觉信息对人类感知粗糙度的可用性。然而，在视听触三个通道如何协同工作，如何为整体感知做出不同贡献等问题上，几乎还没有这方面的研究(Collins& Kapralos,2019)。但正如我们所强调的，人类对于粗糙度的感知是一个多通道信息整合的过程，并且为人类呈现多通道的信息有诸多益处。在现实环境中，多通道输入为人类提供的冗余信息有助其降低认知负荷(Marucci et al.,2021)，提高任务绩效(Hecht et al.,2008)；在虚拟现实环境中，相较于单通道信息，多通道的信息反馈不仅使被试绩效最好，还能提供给被试更强烈的存在感和沉浸感(Bosman，2018; Cooper et al.,2018; Marucci et al.,2021)。因此，在虚拟现实环境中的材料感知任务中，相较于只呈现单通道或二通道的信息，呈现三通道信息(视觉、听觉、触觉)是否能有效提高被试对材料的识别绩效(识别速度、识别正确率)，是否能让被试获得更好的虚拟现实体验(沉浸感、存在感)？三通道条件下，各个通道如何整合完成整体粗糙度感知，各通道在整体感知中分别占有多少权重？这些问题有待进一步的探究。随着我们在这一研究领域内的不断探索，在未来，视觉、听觉信息可能会以超出常识的方式，极大的丰富人们在虚拟现实环境中的体验(Collins & Kapralos,2019)。

# 参考文献

吴淼.(2019)．视触觉交互的纹理力触觉感知实验研究及应用(硕士学位论文)，东南大学，南京.   
Aktar,T.,Chen,J.,Etelaie,R.,Holmes,M.,&Henson,B.(O17).Humanroughness perceptionandpossblefactors effecting roughness sensation. Journal of Texture Studies,48(3),181-192.   
Aoyama, S.,Iwai,D.,& Sato, K. (2016).Altering resistive force perception by modulating velcity of dot pattern projected onto hand. In Proceedings of the 2016 workshop on Multimodal Virtual and Augmented Reality (p. 7).

Adams,W.J.,Kerigan,I.S.,& Graf,E.W. (2o16).Touch influencesperceived glossScientific Reports,6(1),

21866-21866.

Altinsoy, M.E. (2oo4).The influence of frequency on the integration of auditoryand tactile information.

Altinsoy,M.E. (2O08).The effect of auditorycues on the audiotactile roughness perception: Modulation frequency and sound pressure level. In HAID'08 Proceedings of the 3rd international workshop on Haptic and Audio Interaction Design (pp. 120-129).   
Bizley, J. K.,Shinn-Cunningham,B.G.,&Lee,A. K.C. (20l2). Nothing isirrelevant ina noisy world: Sensory illusionsreveal obligatory within-and across-modality integration.The Journal of Neuroscience,32(39), 13402-13410.   
Bi, W.,Newport,J.,& Xiao,B.(2018).Interaction between static visualcues and force-feedback on the perception of mass of virtual objects. In Proceedings of the 15th ACM Symposium on Applied Perception (p. 12).   
Bosman,I.D.V.(O18).Using binauralaudioforinducing intersensoryillsions tocreate ilusorytactilefeedback in virtual reality. (Unpublished master's thesis). University of Pretoria   
Cooper,N.,Milella,F.,Pinto,C.,Cant,I.,White,M.,& Meyer,G. (2018).The effectsof substitute multisensory feedback on task performance and the sense of presence in a virtual reality environment. PLOS ONE,13(2).   
Collins,K.,&Kapralos,B.(20l9).Pseudo-haptics: Leveragingcross-modalperceptioninvirtualenvironments.The Senses and Society,14(3),313-329.   
Culbertson,H.,Schor,S.B.,& Okamura,A.M. (2018). Haptics: The present and future of artificial touch sensation. Annual Review ofControl, Robotics, and Autonomous Systems,1(1).   
Crommett,L.E.,Pérez-Bellido,A.,& Yau,J. M.(2017).Auditory adaptation improves tactile frequency perception. Journal of Neurophysiology,117(3),1352-1362.   
Eitan,Z.,& Rothschild,I.(2011). How music touches: Musical parameters and listeners'audio-tactile metaphorical mappings: Psychology of Music,39(4), 449-467.   
Etzi,R.,Ferise,F.,Bordegoni,M.,Zampini,M,&Gallce,A. (2o18).Theeffectofvisualandauditory information on the perception of pleasantnessand roughness of virtual surfaces. Multisensory Research,31(6),501-522.   
Ernst,M.O.,&Banks,M.S. (20o2).Humans integrate visualand haptic information in astatisticalloptimal fashion. Nature, 415(6870), 429-433   
Egmond, R.V.,Lemmens,P.,Pappas,T.N.,&Ridder,H.D. (2o09).Roughness insound and vision.Proceedings of SPIE,2009 Vol. 7240.   
Guest, S.， Catmur, C., Lloyd, D.，& Spence，C. (2002). Audiotactile interactions in roughness perception. Experimental Brain Research,146(2),161-171.   
Gunther,S.，Makhija,M.，Müller,F.,Schon,D.,Muhlhäuser,M.,& Funk,M. (2019).PneumAct: Pneumatic kinesthetic actuation of body joints in virtual reality environments. In Proceedings ofthe 2019 on Designing Interactive Systems Conference (pp. 227-240).   
Hecht,D.,Reiner, M.,& Karni,A. (2oo8). Enhancement of response times to bi- and tri-modal sensory stimuli during active movements. Experimental Brain Research,185(4), 655-665.   
Hirao, Y., Takala, T. M., & Lecuyer, A. (2020). Comparing motion-based versus controller-based pseudo-haptic weight sensations in VR. In 2O20 IEEE Conference on Virtual Reality and 3D User Interfaces Abstracts and Workshops (VRW) (pp.305-310).   
Honson,V.,Huynh-Thu,Q.,Arnison,M.,Monaghan,D.,Isherwood,Z.J.,& Kim,J. (202).Efectsofshape, roughness and gloss on the perceived reflectance ofcolored surfaces.Frontiers in Psychology,11, 485.   
Hoggan,E.,&Brewster,S. (2Oo7).Designing audioandtactilecrossmodalicons formobiledevices.InProceedings of the 9th international conference on Multimodal interfaces (pp.162-169).   
Hashimoto,T.,Narumi,T.,Nagao,R.,Tanikawa,T.,& Hirose,M. (2018).Effect of pseudo-haptic feedback on touchscreens on visual memory during image browsing. In International Conference on Human Haptic Sensing and Touch Enabled Computer Applications (pp. 551-563).   
Ho,Y.X.,Landy,M.S.,& Maloney,L.T.(2O6).How directionof illumination affects visually perceived surface roughness. Journal of Vision, 6(5), 634-648.   
Ho,Y. X., Maloney,L. T.,& Landy,M. S. (2o07).The effect of viewpoint on perceived visual roughness. Journal of Vision,7(1),1-1.   
Hannig,G.,& Deml,B. (2oo8). Scrutinizing pseudo haptic feedback of surface roughness in virtual environments. In 2008 IEEE Conference on Virtual Environments, Human-Computer Interfaces and Measurement Systems (pp. 1-4).   
Jones,B.,& O'Neil, S. (1985). Combining vision and touch in texture perception. Atention Perception & Psychophysics,37(1),66-72.   
Jousmaki, V.,& Hari, R. (1998). Parchment-skin ilusion: Sound-biased touch. Current Biology,8(6).   
Kapralos,B., Moussa,F., Colins,K.,& Dubrowski,A.(2017).Fidelity and multimodal interactions,79-101.   
Kawabe,T. (2020). Mid-air action contributes to pseudo-haptic stiffness effects. IEEE Transactions on Haptics, 13(1), 18-24.   
Kim, S.-C., Kyung,K.-U.,& Kwon,D.-S. (207). The effct of sound on haptic perception. In Second Joint EuroHaptics Conference and Symposium on Haptic Interfaces for Virtual Environment and Teleoperator

Systems (WHC'07) (pp.354-360).

Kang,N.,& Lee,S.(20l8).A meta-analysis of recent studies on haptic feedback enhancement in immersiveaugmented reality. In Proceedings of the 4th International Conference on Virtual Reality (pp. 3-9).

Klatzky, R.L.,& Lederman, S. J. (2010). Multisensory texture perception, 211-230.   
Lederman, S.J.,& Taylor, M. M. (1972). Fingertip force,surface geometry,and the perception of roughness by active touch. Attention Perception & Psychophysics,12(5),401-408.   
Lederman, S. J. (1979). Auditory texture perception. Perception, 8(1),93-103.   
Lederman, S. J., & Abbot, S.G. (1981).Texture perception: studies ofintersensory organization using a discrepancy paradigm, and visual versus tactual psychophysics. Journal of Experimental Psychology: Human Perception and Performance,7(4), 902-915.   
Lederman, S.J.,Thorne, G.,& Jones,B.(1986).Perception oftexture by vision and touch: multidimensionality and intersensory integration. Journal of Experimental Psychology: Human Perception and Performance,12(2), 169-180.   
Lederman, S. J., Klatzky,R.L., Hamilton, C.L.,& Ramsay, G.I. (1999). Perceiving roughness via a rigid probe: Psychophysical effects of exploration speed and mode of touch.   
Lederman,S.J.,Martin,A., Tong, C.,& Klatzky,R.L. (2oo3). Relative performance using haptic and/or touchproduced auditory cues in a remote absolute texture identification task. In 11th Symposium on Haptic Interfaces for Virtual Environment and Teleoperator Systems, 2003. HAPTICS 2003.Proceedings.(pp.151-158).   
Lecuyer, A.,Coquillart,S., Kheddar,A.,Richard,P.,& Coifft,P.(ooo).Pseudo-haptic feedback: Canisometric input devices simulate force feedback? In Proceedings IEEE Virtual Reality 200o (Cat. No.0oCB37048) (pp. 83-90).   
Lin,J.-W.,Han,P.-H.,Lee,J.-Y.,Chen,Y.-S., Chang,T.-W., Chen,K.-W.,&Hung,Y.-P. (2017). Visualizing the keyboard in virtual reality for enhancing immersive experience. In ACM SIGGRAPH 2017 Posters on (p. 35).   
Li,M.,Sareh,S., Xu, G.,Ridzuan,M.B.,Luo,S., Xie,J.. Althoefer,K. (2016).Evaluationof pseudo-haptic interactions with soft objects in virtual environments. PLOS ONE,11(6).   
Marucci,M.,Fumeri, G.D.,Borghini,G.,Sciaraa,N.,candola,M.,Pavone,E.F.,..Arico,P. (2021).Theimpact of multisensory integration and perceptual load in virtual reality setings on performance,workload and presence. Scientific Reports,11(1), 4831-4831.   
Malpica,S.,Serrano,A.,Allue,M.,Bedia,M. G.,& Masia,B. (202O). Crossmodal perception in virtual reality. Multimedia Tools and Applications,79(5),3311-3331.

Matsumoto,D.,Zhu,Y.,Tanaka,Y.,Yamazaki,K.,Hasegawa,K.,Makino,Y,&Shinoda,H.(2o16).Animmersive visuo-haptic VR environment with pseudo-haptic effcts on perceived stifness. International AsiaHaptics Conference, 281-285.

Okamoto,S.,Nagano,H.,& Yamada,Y. (20l3).Psychophysical dimensionsof tactile perception of textures.IEEE Transactions on Haptics, 6(1), 81-93.   
Ota,Y.,Ujitoko,Y.,Ban,Y.,Sakurai, S.,&Hrota,K. (2O2o).Surface roughness judgment during finger exploration is changeable by visual oscilations. In International Conference on Human Haptic Sensing and Touch Enabled Computer Applications (pp. 33-41).   
Poling,G.L., Weisenberger, J. M.,& Kerwin,T. (2003). The role of multisensory feedback in haptic surface perception. In lth Symposium on Haptic Interfaces for Virtual Environment and Teleoperator Systems, 2003. HAPTICS 2003. Proceedings. (pp. 187-194).   
Peva,D.,Baird,B.,Izmrli,O.,&Blevins,D.(Oo4).Hapticandsound corrlations: pitch,loudness and exture. In Proceedings. Eighth International Conference on Information Visualisation,2004.IV 2004. (pp.659-664).   
Ramirez,A. G.R.,Luna,F. J. G., Villgas, O.O. V.,& Nandayapa,M. (2018). Applications of Haptic Systems in Virtual Environments: A Brief Review, 349-377.   
Paulun,V.C.,Schmidt,F.,Assen,J.J.R.van,&Fleming,R. W. (20l7).Shape, motion,and optical cues tostfss of elastic objects.Journal of Vision,17(1),20-20.   
Suzuki,Y., Suzuki, M., Gyoba,J.,2006.Effcts of auditory feedback on tactile roughness perception.Tohoku Psychol.Folia 65,45-56.   
Suzuki,Y., Gyoba,J.,&Sakamoto,S. (2o08).Selective efects ofauditory stimuli ontactile roughness perception. Brain Research,1242,87-94.   
Sato, Y.,Hiraki,T.,Tanabe,N., Matsukura, H.,Iwai,D.,& Sato,K. (2O2O). Modifying texture perception with pseudo-haptic feedback for a projected virtual hand interface. IEEE Access,8,120473-120488.   
Schmidt,F.,Paulun,V.C.,Assen,J.J.R.van,&Fleming,R. W. (2o17). Inferring the stiffness ofunfamiliarobjects from optical, shape, and motion cues. Journal of Vision,17(3),18-18.   
Samad,M., Gatti,E., Hermes,A.,Benko,H.,& Parise,C. (2019). Pseudo-haptic weight: Changing the perceived weight of virtual objects by manipulating control-display ratio.In Proceedings ofthe 2019 CHI Conference on Human Factors in Computing Systems (p. 320).   
Todd,J. T.,& Norman, J.F. (2018). The visual perception of metal. Journal of Vision,18(3), 9-9.   
Ujitoko,Y.,Ban,Y.,& Hirota,K.(2019a).Modulating fine roughness perceptionof vibrotactile textured surface using pseudo-haptic effect.IEEE Transactions on Visualization and Computer Graphics,25(5),1981-1990.   
Ujitoko,Y.,Ban,Y.,& Hirota,K.(O19b).Presenting static friction sensationat stick-sliptransition using pseudohaptic effect. In 2019 IEEE World Haptics Conference (WHC) (pp.181-186).   
Vardar,Y.,Wallraven, C.,& Kuchenbecker, K.J. (2O19).Fingertip interaction metricscorrelate with visual and haptic perception ofreal surfaces.In 2019 IEEE World Haptics Conference (WHC) (pp.395-400).   
Weisenberger,J.M.,& Poling, G.L.(2004). Multisensory roughness perception of virtual surfaces: effects of correlated cues. In 12th International Symposium on Haptic Interfaces for Virtual Environment and Teleoperator Systems,2004.HAPTICS 04.Proceedings. (pp.161-168).   
Wall,S.A.,& Harwin, W.S. (2Oo1).Interaction of visualand haptic information in simulated environments:Texture perception.Lecture Notes in Computer Science,108-117.   
Wang,D.,Ohnishi,K.,& Xu, W. (202O).Multimodal haptic display for virtual reality: Asurvey.IEEE Transactions on Industrial Electronics,67(1),610-623.   
Zampini, M., Guest, S.,& Spence,C. (2003). The role of auditory cues in modulating the perception of electric toothbrushes.Journal of Dental Research,82(11),929-932.

# The vivid tactile experience from vision and auditory: Clues from multisensory channel integration

Wan Bicheng,Ma Shu, Yang Zheng,Li Hongting (PsychologyDepartment,Zhejiang Sci-Tech University,Hangzhou 31oo18,China)

Abstract: Virtual reality creates an immersive experience for users by providing visual, auditory, and tactile information.However, tactile feedback still faces many technical bottlenecks,which limit natural interaction in the virtual reality environment. Pseudo-haptic technology based on multisensory illusion can enhance and enrich tactile perception with the help of information from other channels,which is one of the effective ways to optimize tactile perception in the virtual reality environment. In order to explore the problem in a more targeted way, the study focuses on roughness perception among different dimensions of tactile perception. We discuss the multi-sensory channel integration of visual, auditory,and tactile in roughness perception, then analyze how the visual cues (density of surface texture， light and shadow, control display rate） and auditory cues (pitch/frequency， loudness） affect roughness perception, moreover, summarize the methods of changing roughness perception by manipulating these cues. Finally, we discuss the differences of visual,auditory, and tactile information between virtual reality environment and real-world in representation and perceptual integration when using pseudo-haptic feedback technology, proposing practical solutions and future research directions to improve the tactile experience.

Key words: roughness perception, multi-sensory channel integration, visual cues, auditory cues