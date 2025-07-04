# 触觉二维图像识别中2D-3D空间信息转换的认知机制

# 覃缨惠1,2 於文苑1,2,3 傅小兰1,2 刘烨1,2

（1中国科学院心理研究所，脑与认知科学国家重点实验室，北京100101）（²中国科学院大学心理学系，北京100049）（之江实验室基础理论研究院，杭州311121）

摘要 可触摸的触觉二维图像是视觉障碍人群获取图像信息的重要方式。目前大多数触觉二维图像都是直接由视觉二维图像转化为的可触摸线条图。在视觉二维图像中，通常运用透视和视角等视觉原理将三维空间关系转换为二维平面关系。视觉系统经过长期大量知觉学习，习得了这种二维到三维的映射关系。但是触觉识别二维图像时，触觉系统如何建立二维平面与三维空间的映射，目前尚有待进一步的研究。影响触觉识别二维图像中二维-三维空间信息转换的视觉因素主要有透视、视角、遮挡、纹理梯度和镂空，直接将视觉二维图像转化为的触觉二维图像时，图像中包含的上述视觉因素通常会干扰触觉识别。结合已有研究，试图提出“双表象加工模型”来解释触摸二维图像时二维到三维空间信息转换的认知机制。该模型认为触觉识别二维图像依赖于两个表象系统的整合，即物体表象系统（涉及物体的大小、形状和纹理）与空间表象系统（涉及物体的空间关系、透视和视角)。两种表象系统的信息最终进行整合，在物体表象和空间表象成功匹配的基础上建立二维图像与三维空间之间的映射，通达长时记忆中的三维物体表征。双表象加工模型将有助于我们深入认识触知觉的认知机制，也将为触觉二维图像的设计提供理论依据。

# 关键词触觉，二维图像，触觉识别，透视，视角

触觉对于人类和动物的生存具有不可替代的作用，包括人类在内的灵长类动物在用手抓取物体时，获取触觉信息为使用和操作物体服务(Sathian,2016)，并通过触感影响触摸物体时的情绪体验 (Kitada et al.,2021; Pasqualotto et al.,2020; Yasaka et al.,2019)。大脑通过多个感觉通道接收信息，并将其整合形成多模态表征(Lacey& Sathian,2014;Perini etal.,2020)，在无法充分获取视觉信息的情况下，比如视觉受损或者处于黑暗环境，触觉是视觉的重要替代感觉(Toprak et al., 2018)。

据统计，2020 年全球共有3.99 亿低视力人群，其中包括 7090万完全丧失视力的视觉障碍人群(Flaxman etal.,2017)，视觉障碍人群学习诸如几何、艺术和地理等依赖视觉信息的知识时，需要使用触觉二维（two-dimensional,2D）图像(Bara et al.,2018; Cavazos Quero et al.,2021; Szubielskaetal.,2019)。近年来出现的电子触觉显示器可以实时、动态地显示可触摸的二维图像，甚至可能帮助视觉障碍人群使用互联网(Kim etal.,2019；焦阳 等,2016；卢纯福，宗先信,2017)。专门为触觉二维图像研究开发的多点触控交互式数据分析系统，可以捕捉、分析、编码和解释用户在执行触觉任务时的行为(Garcia etal.,2020)。但是，目前这些产品生成的二维平面图像，都是基于视觉原理来呈现三维（three-dimensional,3D）物体和场景，通常运用大量视觉因素，尤其是视觉单眼线索(主要包括透视、视角、遮挡、纹理梯度和镂空)，来表达深度和立体信息(Lebreton,2016)，将三维空间关系转换为二维平面关系。虽然视觉系统经过大量知觉学习(Zhang&Li,2020；王葛彤 等,2020)，可以习得二维与三维的空间关系映射，但是有研究发现蒙眼明眼人和视障者通过触觉识别自然物体的二维线条图的正确率只有 $30 \%$ 至 $40 \%$ (Sinha&Kalia,2012)，因此诸如透视和视角等这些视觉因素可能阻碍触觉识别,不能直接迁移到触觉二维图像设计(Bauer etal.,2015；龚江涛 等,2018；於文苑 等,2019),这导致传统的纸质触觉图像教具及其制作设备的使用率较低(焦阳 等,2016)。由此可见，虽然触觉二维图像的制作技术日臻成熟，但是触觉识别二维图像时，如何建立三维空间与基于视觉原理的二维空间之间的映射，目前尚不清楚，如何更好地设计触觉二维图像，以及如何有效地帮助视觉障碍人群提高触觉识别二维图像的绩效，仍是亟待解决的问题。因此，考察影响触觉识别二维图像的视觉因素不仅对认识触知觉的认知机制具有重要意义，也可以为触觉二维图像的设计提供理论指导和建议。

本文围绕触觉二维图像识别中的二维-三维（2D-3D）空间信息转换这一主题，以透视和视角等反映二维与三维空间关系映射的视觉模态特有因素为切入点，综述了它们对触觉识别二维图像的影响，并分析其发挥作用的认知神经机制。结合已有研究，本文提出触觉识别二维图像的“双表象加工模型”，用于解释触觉识别二维图像的认知过程中，触觉系统如何建立二维平面与三维空间的映射。在该模型中，通过触觉感知的信息分别形成物体表象（涉及物体的大小、形状和纹理）和空间表象（涉及物体的空间关系、透视和视角)，触觉识别二维图像需要依赖这两种表象系统的有效整合，成功匹配物体表象和空间表象，建立二维图像

与三维物体表征之间的映射，通达长时记忆中的三维物体表征，实现触觉二维图像的识别。  
最后，本文进一步总结了未来研究亟需解决的问题，以及需要关注的研究方向。

# 1影响触觉2D-3D空间信息转换的视觉因素

以往研究中涉及到的影响二维图像触觉识别的因素可大致分为两类：第一类是二维图像的特征，如图像中的纹理(Nguyen et al.,2018; Thompson et al.,2006; Theurel et al.,2013)、透视(Gong et al.,2020; Lebaz.et al.,2012; Lederman et al.,1990；龚江涛 等,2018)、视角(Helleret al.,2002)和图像的复杂度(Yu et al.,2017)；第二类是触摸者的个体因素，缺乏触觉经验、对图像的熟悉度低以及盲人缺乏视觉经验等都会导致个体难以触觉识别二维图像(Ledermanet al.,1990; Mazella et al.,2018; Overvliet& Krampe,2018)。由于现有的触觉二维图像都是基于视觉原理生成的平面图像，遵循平面视觉显示的原理和特性，而这些原理和特性可能并不适用于触知觉，因此本文主要探讨影响触觉2D-3D空间信息转换的视觉因素。

影响触知觉的视觉因素主要是在二维平面上用来表达三维空间的深度和立体信息的视觉单眼线索，主要包括透视、视角、遮挡、纹理梯度和镂空等(Lebreton,2016)。当在二维平面上呈现三维物体和场景时，现有的呈现方式几乎都是基于上述视觉原理来表达深度和立体信息。虽然外界物体投射到视网膜上的成像是二维图像，但是视觉系统通过双眼视差和单眼线索，以及大量的知觉学习和眼手协调交互，可以快速、有效地获取事物的深度信息和三维立体特征(Zhang&Li,2020；王葛彤 等,2020)。但是，人们缺乏通过触觉将二维平面中的深度信息转换为三维空间的经验(Klatzky&Lederman,2011)，因此可能难以获得二维图像中表达的深度信息(Heller et al., 2006; Nguyen et al., 2018)。

![](images/c5f3138fb3ed7575bbd85d6cbc1480d9051b03d471d09949656a782680d11593.jpg)  
图1视觉单眼线索图例

如图1a所示，透视是在两维的平面上利用线和面趋向会合的视觉原理表现三维物体和立体空间，是最重要的单眼线索，与视角密切相关，提供了物体的三维视角。对于同一个三维物体，在不同视角呈现的二维图像存在不同，彼此之间所表现出的物体旋转角度的变化，势必会涉及透视关系的变化(Heller et al.,2006)。图1b 展示了六棱柱二维线条图中的三种视角，包括顶部视角、三维视角和正面视角，其中顶部视角和正面视角无法展示六棱柱的三维空间信息，而利用了透视关系的三维视角可以表达六棱柱的三维空间信息。除了透视外，镂空、遮挡和纹理梯度也是获取深度信息的单眼线索（见图1)。在三维物体中，镂空是指去除物体的内部，在物体中留出空间，当镂空的三维物体变成二维线条图（如图1c所示）时，通过触摸线条图难以理解其中镂空部分的信息。遮挡(也称为重叠)提供了物体空间位置的前后和远近信息，被遮住部位的信息需要知觉进行填充(Lebreton,2016)。二维图像中的遮挡线索是视觉模态下特有的空间表象方式，但是仅靠触摸很难分辨出相互重叠部分的远近，也无法将被遮挡住的部分填充。如图1d中的樱桃，视觉观看时人们很容易理解是三个互相重叠的樱桃，但触觉触摸时容易将三个樱桃知觉为一个物体。纹理梯度是指随着距离变化，物体表面纹理在近处稀疏、远处密集(见图1e)。

上述视觉因素，其中视角和透视目前在触知觉领域研究相对较多，而遮挡、镂空和纹理梯度目前少有人关注，仅有个别研究考察了纹理梯度对触觉识别二维图像的影响，发现适当的纹理可以促进触觉识别二维图像的识别绩效(Nguyen et al.,2018;Thompson et al.,2006;Theureletal.,2013)。例如，通过纹理信息来表达图像的深度信息有利于触觉的识别，在二维图像中对物体的不同面使用不同的纹理，可以为触觉感知提供物体的空间信息(Thompson etal.,2006)。将整个物体形状轮廓浮起制作二维图像后，再添加物体的细节纹理，其触觉的识别绩效比仅有线条图和仅有形状轮廓无纹理的二维图像都高(Theurelet al.,2013)。根据物体每个部分距离观察者的远近，改变物体线条的粗细，离观察者越近线条越粗，以此增加深度信息，也可以提高触觉识别二维图像的绩效(Nguyen et al.,2018)。对于视觉模态，透视、视角、遮挡、纹理梯度和镂空这类单眼线索运用在二维图像中可以提供物体的深度信息，但是如果这些线索没有通过类似上述的特殊处理，那么对于触觉模态，这些线索则可能会干扰二维图像的触觉识别（Gong et al.,2020）。

触觉识别二维图像的过程，是将触觉感知到的二维图像所建构生成的三维心理表征与头脑中的三维物体概念表征进行匹配的过程。相比之下，触觉识别三维物体相对于触觉识别二维图像则少了从二维到三维的映射和建构过程，讨论视角对触觉识别三维物体的影响，也可能对我们进一步了解视角和透视在触觉识别二维图像中的作用有所启发。下面，本文首先介绍视角对触觉识别三维物体的影响，然后着重讨论透视和视角对触觉识别二维图像的影响。

# 1.1视角对触觉识别三维物体的影响

视知觉存在物体恒常现象(Qian& Petrov,2016)，物体依赖于视角的信息和独立于视角的信息会被同时编码(Tarr&Hayward,2017)。触觉模态也存在物体恒常现象，当触觉识别三维物体时，人们需要整合一个物体的多个触觉角度，即来自不同手和不同手指的触觉信息，从而形成物体表征，用于物体的定位、识别和操作(Heed et al.,2015;Yau et al.,2016)。这种手部触摸的角度在以往研究中也被称为“视角”。由于双手能同时从不同角度触摸物体，所以直觉上触觉识别三维物体应该是视角独立的。但是，研究发现明眼人触觉识别三维人造几何物体时存在视角偏好。当物体正对被试的一面用布遮盖，只能触摸背对被试的那一面时，这种背面视角条件相对正面视角（物体背对被试的那一面被布遮盖，被试只能触摸正对自己的那一面）物体识别绩效更好(Newell et al.,2001)。即使允许蒙眼明眼人对物体的多个表面进行更全面的触觉探测，当要求匹配的物体发生了视角的旋转，触觉识别仍然受到视角变化的干扰(Lacey etal.,2007)。研究者认为这可能是由于人们惯用的触摸方式是拇指不动，其它四根手指探索，这种限制使得触觉探测偏向于物体的背对被试的“视角"(Lacey etal.,2007)。

上述两项研究采用的都是人造几何物体，可能是因为人们对这类物体不熟悉，因而导致识别受到视角影响(Woods et al.,2008)。因此有研究对比了熟悉的三维物体（例如，玩具马、玩具房子）与人造几何物体的触觉识别，发现对于不熟悉的三维物体，蒙眼明眼人在触觉模态和视觉模态的物体识别都受到物体视角变化的影响，即都是视角依赖；对于熟悉的三维物体，蒙眼明眼人的触觉识别不受物体视角变化的影响，即视角独立(Woods etal.,2008)。如果蒙眼明眼人对不熟悉的三维几何物体进行一定的触觉学习，对其进行触觉识别也可以不再受视角的干扰(Lacey et al., 2009)。

与蒙眼明眼人触觉识别人造几何物体的视角依赖相反，早期盲人(early blind，EB，三岁以前就失明的盲人)对人造几何物体的触觉识别是视角独立的(Occelli etal.,2016)。由此可见蒙眼明眼人的触觉三维物体识别是否依赖于视角，取决于对物体的熟悉度，而视障者的触觉三维物体识别是视角独立的，与物体的熟悉度无关。蒙眼明眼人与视障者在这方面的差异，可能是因为视障者缺乏视觉经验，导致在触摸和加工物体信息时更关注物体各部分之间的空间关系(Occelli et al.,2016)，同时也有可能是因为视障者的触觉经验更丰富，可以更有效地获取物体各部分之间空间关系的触觉信息。如 Withagen 等人(2013)在触觉识别三维物体的研究中发现，成年视障者的触觉探索策略比视障儿童更成熟，识别绩效更好。但是，对于蒙眼明眼人，可能无法像视障者那样有效地获取空间关系的触觉信息，相对更加依赖于物体特征的触觉识别，因此对于不熟悉的三维物体，更容易受到视角变化的干扰。

# 1.2透视和视角对触觉识别二维图像的影响

二维图像中的透视信息，可以在视觉上提供三维物体的高度、宽度、深度和视角信息。物体视角变化会影响透视的表达。目前，有关透视和视角影响二维图像触觉识别的研究发现主要有以下四个方面。

第一，透视关系产生的三维视角会干扰二维图像的触觉识别。在触觉识别自然物体的二维线条图时，相对于不具有透视信息的二维线条图，蒙眼明眼人对含有透视信息的二维线条图的识别绩效更低(Gong et al.,2020; Lebaz.et al.,2012; Lederman et al.,1990；龚江涛等,2018)。这表明自然物体二维图像中包含的透视关系会干扰对其的触觉识别。这可能是因为具有强烈透视感的图像，包含了物体多个面的三维视角的图像，虽然这可以加深视觉对图像深度信息的理解，但却增加了触觉二维图像的复杂度，在一定程度上会造成触觉识别的障碍。与上述研究发现相一致，实践领域积累的经验也认为通过触觉很难识别二维图像中的透视关系。例如，北美盲文权威指南(Authority,2010)认为视障人群缺乏视觉经验，很难理解二维图像中的透视线索，因此建议除非明确需要，否则透视应该从触觉图像中移除。

第二，触觉识别三维物体的二维图像时，存在视角偏好。当通过触觉从4张二维图像中选出与目标三维几何物体一致的图像时，蒙眼明眼人(Heller etal.,2002)和盲人(Heller et al,2006)都是俯视视角的识别绩效最好；当从4张视角不同的、但物体相同的二维房屋图像中找出指定的视角的二维图像时，低视力被试和盲人被试都是二维图像为俯视视角时的绩效最好(Heller etal.,2009)。这两项研究表明二维图像的触觉识别会受到视角的影响，出现俯视视角的识别优势可能是因为 Heller 等人(Heller et al.,2009)在这些研究中使用的三维物体在俯视视角下能提供最多的空间关系信息和物体特征，例如柱状几何体的独特顶部和房屋的独特屋顶可以提供最佳的辨别信息。然而，视角的优势效应受到刺激类型和任务难度的影响，当触摸的三维物体从简单几何体变为复杂几何体时，盲人、低视力和蒙眼明眼人对俯视视角的识别优势消失(Heller et al.,2009;Heller et al.,2006)。目前 Heller 的研究受限于使用的三维物体的类型，不足以说明触觉识别二维物体的最佳视角是俯视视角，不同类别的物体可能存在不同的优势视角。在触觉识别日常生活常见物体(如苹果、裤子和剪刀等)二维图像的研究中，轴对称的物体存在对称面识别优势(Gong et al.,2020; Sinha&Kalia,2012；龚江涛 等,2018)。诸如蝴蝶和裤子这类对称物体，当以对称面呈现时，相对于非对称物体的二维图像更易识别。因此未来的研究需要进一步探究不同类别的物体的二维图像可能存在的视角偏好。

第三，透视在个别条件下可能会促进二维图像的触觉识别。例如，当要求蒙眼明眼人从4张二维图像选项中，选出与目标二维图像中的物体一致的图像，如果目标图像是具有透视的三维视角，则相对于目标图像不具有透视的三维视角，其识别绩效更好；但是如果4个备选项具有透视，相对于备选项不具有透视，这种优势效应则不存在(Heller etal.,2006)。当从 4 张二维图像中选出与复杂的三维几何物体一致的图像时，早期盲人的识别绩效也是具有透视的二维图像绩效最好(Heller etal.,2009)。这说明蒙眼明眼人和盲人可以通过触觉理解透视提供的物体各个部件之间的空间关系(Heller et al.,2009; Heller et al.,2006)；当目标二维图像具有透视时出现优势效应，可能是因为透视提供了更多的空间信息，才能更好地与备择的二维图像进行匹配；当目标是三维物体时，物体本身就已经提供了足够的空间信息，所以4个备择选项具有透视也可以促进识别绩效。

第四，通过后天的训练，缺乏视觉经验的视障者能够理解透视线索中的深度信息。当要求被试将两个木板形成的三维夹角物体与多个不同角度的夹角二维图像进行匹配时，明眼人、先天盲人和后天盲人的识别绩效并没有显著差别；当要求被试画出触摸到的木板夹角时，先天盲人的画作也呈现出符合三维物体透视规则的二维图像(Heller etal.,2002)。有个案研究发现，通过指导盲人进行后天的练习，可以使其习得透视规则，并能画出不同角度下三维物体具有透视规则的二维图像(Kennedy&Juricevic,2016)。

以上研究表明，触觉识别二维图像存在视角偏好，物体的类别不同偏好的视角也可能不同。此外，尽管触觉理解透视存在一定难度，但并不是完全不可理解。因此有研究者尝试在触觉二维图像中创造一些局部线索以提示透视和视角信息，正如前文所述，二维图像中物体不同视角的表面使用不同的纹理，在触觉上给被试提供物体的空间信息，可以提高识别绩效(Thompson etal.,2006)；或是根据物体每个部分距离观察者的远近,改变物体线条的粗细，离观察者越近线条越粗，蒙眼明眼人能有效识别图像中的透视和深度信息，触觉识别绩效显著提高(Nguyen et al.,2018)。由此可见，进一步研究影响触觉识别二维图像的视觉因素，有助于改进触觉二维图像的设计，进而提升触觉识别二维图像的绩效。

# 2触觉2D-3D空间信息转换的神经基础

触觉识别二维图像与触觉识别三维物体一样，首先离不开对其中包含的线条或物体表面的朝向和曲率、纹理信息的触觉感知。目前有关触觉的神经机制研究主要集中在二维和三维的形状与纹理的触觉感知，但是有关触觉如何基于二维图像识别其中的三维物体和空间的神经基础尚缺乏相关研究。

触觉感知线条或物体表面的朝向和曲率与纹理的基础是位于皮肤浅层、肌肉、肌腱、关节和韧带的各种不同的机械感受器，它们对皮肤变形和肢体运动做出反应，产生触觉和本体感觉，通过内侧丘系通路传导至丘脑，最终传递至大脑皮层的躯体感觉皮层，包括位于布罗德曼1、2、3a 和 3b 区的初级躯体感觉皮层(primary somatosensory cortex,S1)和次级躯体感觉皮层(secondary somatosensory cortex, S2)(Delhaye et al.,2018; Yau et al.,2016)，它们参与编码触觉刺激的粗糙度、朝向、曲率和形状(Kitada,2016); Yau et al.,2016)，3b 区损伤会导致触觉识别纹理和形状辨别的能力丧失，2区的损伤会导致无法触觉感知物体形状和大小的变化(Delhaye et al., 2018)。

目前有关触觉神经基础的大量研究发现，触觉与视觉在表征物体信息的神经基础上存在一定的重合或存在相似的模式(Kitada,2016; Lacey & Sathian,2014; Sathian,2016; Yau et al.,2016)，这表明触觉信息编码激活的神经网络并不是触觉模态特异的，而是与多个感觉模态相关联。由于目前的触觉二维图像几乎都是基于视觉原理生成，所以触觉识别二维图像时可能更加依赖视觉系统的参与，以及视觉与触觉信息的整合，因此触觉与视觉重合或视-触觉跨模态整合的神经基础可以为触觉识别二维图像的神经机制提供研究思路。

# 2.1触觉和视觉重合的神经基础

首先，触觉与视觉模态在加工形状、大小和纹理等感觉信息时的神经基础存在较大程度的重合。触觉和视觉识别物体形状的脑区都涉及顶内沟(intraparietal sulcus,IPS)和外侧枕叶(lateral occipital complex,LOC)(Sathian,2016)。LOC 是视觉和触觉加工形状信息的重要区域，在视觉研究中发现视觉呈现二维图像和三维物体(如工具、动物、玩具等)时该区域会激活(Amedi etal.,2002)，在触觉研究中也发现LOC 在触摸三维物体时会激活(Hernandez-Perez etal.,2017)，在触摸二维字母图像(Stoesz et al.,2003)和简单的二维形状(如弯钩)(Prather et al,2004)时激活。触觉检测到物体大小变化时会激活顶内沟(intraparietal sulcus，IPS)和外侧前额叶，在视觉模态也发现了相似的激活模式(Perini et al.,2020)。对纹理和粗糙度的触觉判断也涉及视觉皮层，触觉感知凸起圆点的粗糙度时激活岛盖皮层（operculo-insular cortex）和腹侧颞叶皮层（ventral temporal cortex,VTC)，触觉感知凸起圆点的空间密度时激活初级躯体感觉皮层和视觉皮层(Eck et al.,2016)。

其次，视觉皮层参与触觉通道的二维图像生成和触觉表象生成。从未有过视觉经验的先天盲人使用电子触摸笔绘制二维图像时，初级视觉皮层V1被显著激活(Likova,2012)。蒙眼明眼人和先天盲人通过触觉感知物体后，在脑海中生成曾触摸过的物体表象会激活 S1，这与视觉模态的心理表象任务激活的区域一致(de Borst &de Gelder,2016; de Borst&de Gelder,2019)。

第三，触觉工作记忆与视觉工作记忆任务激活相同的脑区。通过触摸3个凸起线条组成的夹角来测量触觉工作记忆时，额下回(inferior frontal gyrus,IFG)、后顶叶(posterior parietalcortex,PPC)，以及额中回(medial frontal gyri,mFG)显著激活(Yang et al.,2014)，其中额下回和额中回也参与触觉纹理的工作记忆加工(Kaas et al.,2013)，上述所有这些脑区同时也参与视觉工作记忆(Yang et al.,2014)。而且进一步的研究表明，视觉工作记忆与触觉工作记忆过程中的选择性注意可能受到共享的超模态（supramodal）控制加工的调节(Katus & Eimer,2020a)，但是两者的空间注意转移可能受到模态特异性的机制调控(Katus &Eimer,2020b)。

最后，当二维图像的加工逐渐熟悉化时，触觉模态和视觉模态都会出现相似的神经激活模式。鼻周皮层(perirhinalcortex,PRC)是多模态信息整合的重要脑区，参与视-触觉信息整合(Cacciamani&Likova,2016;Holdstock etal.,2009)。当使用图像和面孔图片进行视觉模态的

“新-旧”判断任务时，“旧刺激”对应的鼻周皮层激活减弱(Hensonetal.,2003)；当触觉感知的二维图像熟悉度变化时也观察到了鼻周皮层相似的激活减弱模式(Cacciamani&Likova,2016)。

上述研究提示触觉加工二维图像的神经基础与视觉模态存在较大程度的重合(Desmarais et al.,2017; Lacey& Sathian,2014; Sathian,2016)。两个模态重合的神经基础可能表明两者共享表征系统，但也可能是因为这些区域是跨模态感知觉的基础脑区(Cacciamani&Likova,2016)，因此触觉识别二维图像的神经机制仍需进一步的研究。

# 2.2触觉和视觉整合的神经基础

尽管触觉模态和视觉模态的神经基础有一些重合相似之处，但这两个模态在感知属性和感知效率上也存在差异，因此两个模态感知的信息也需要相互整合，以避免因环境复杂而造成的误判(Toprak et al.,2018)。当认知系统整合两个模态的信息时，相对于只有触觉模态的信息，对信息的感知精度更高(Ernst& Banks,2002; Toprak et al.,2018; Wan et al.,2020)(Ernst& Banks,2002; Toprak et al.,2017; Wan et al.,2020)，手的触摸运动速度也更快(Camponogara& Volcic,2019)。

腹侧通路和背侧通路中的皮层区域以前被认为是专门加工视觉信息的区域，近年来发现也参与触觉任务(Freud et al.,2017; Lacey& Sathian,2014; Sathian,2016)。如前文所述，LOC参与视觉和触觉物体识别，LOC中参与视觉和物体识别的特定区域被称为外侧枕叶触觉视觉区域（lateral occipital tactile-visual region，简称LOtv），这一区域也被认为是视觉和触觉进行整合的区域(Lacey& Sathian,2014)。

成人的大脑以统计上最佳的方式整合与物体相关的视觉和触觉信息，根据其可靠性对每种感觉通道的信息进行加权(Ermst& Banks,2002)。关于物体感知的神经基础如何将视觉和触觉感知整合为更抽象和更有意义的知觉信息以进行学习或识别的神经机制目前尚未彻底研究清楚。但是有许多研究表明这种整合能力并非与生俱来，而是由人在发育过程中逐渐发展学习的结果，在8岁之前，人的视觉和触觉空间信息的整合远非最佳，到8至10 岁时，儿童的视觉和触觉整合才发育得如成年人一样(Goriet al.,2008)。先天盲人或视障人士虽然经过多年的视觉剥夺，未能发展多感觉通道整合，但在视觉手术后，恢复视觉数月内其视触整合能力就可以发展到成人最佳水平(Sennaetal.,2021)。这表明早期接触多感觉通道的信号对于多感觉信息整合的发展并不是必不可少，即使经过多年的视觉剥夺，仍然可以通过后天

学习获得。

# 3触觉2D-3D空间信息转换的理论模型

触觉识别二维图像需要将感知到的二维平面信息建构为三维物体和空间信息，并与记忆中的三维物体表征进行匹配，因此如何基于二维平面信息建构三维物体和空间信息对触觉识别二维图像非常重要。此外，触觉识别二维图像受到触觉感觉通道容量的限制，有限的通道容量使触觉无法进行整体加工，而是依据触摸的顺序进行序列加工(Loomis et al.,1991)；在触摸过程中，触摸者需要将触摸的信息（线条的朝向和曲率、大小和纹理等）暂时存储到工作记忆中，与随后触摸的信息进行整合，逐渐形成完整的物体表征(Yoshida etal.,2015)，因此触觉识别更加依赖于工作记忆中实时更新的物体表征，需要占用更多的工作记忆资源(Lacey& Sathian,2014)。对于明眼人来说，触觉形成的物体表征与视觉表象类似(Overvliet etal.,2013)。当触觉二维图像中包含透视和视角这些视觉因素时，视觉表象在触觉识别二维图像中的作用尤为重要。Klatzky 和Lederman(1988)最早关注到表象在触觉识别二维图像中的重要作用，提出“表象调节模型”来解释触觉识别二维图像的认知机制。

# 3.1表象调节模型

表象调节模型（image-mediationmodel）认为触觉识别二维图像是通过触觉感受器感知图像中的线条、节点等信息，在大脑中进行视觉转换，形成视觉表象，然后视觉表象与大脑中储存的知识表征进行对比，最后完成识别(Overvliet et al.,2013)。

![](images/8e59b8c887ec0357a97c9f2c2bfd670206645786d00e79e68a62fd17de99f884.jpg)  
图2表象调节模型 (引自(Lederman et al.，1990))

表象调节模型（如图1所示）得到了一些研究证据的支持，例如，没有视觉经验的先天盲人的二维图像识别绩效低于视觉经验丰富的蒙眼明眼人(Lederman et al.,1990)，视觉表象能力高的蒙眼明眼人识别绩效高于表象能力低的蒙眼明眼人(Lebaz.etal.,2012)。但是，也有研究发现蒙眼明眼人与盲人的二维图像触觉识别绩效没有显著差异(Heller et al.,2009;Lebaz.etal.,2012; Picard etal.,2010)，这并不支持表象调节模型的“视觉转换”和“视觉表象”机制，因为先天盲人几乎没有视觉经验，如果转化为视觉表象是触觉识别二维图像的必要步骤，那么蒙眼明眼人的识别绩效应该优于先天盲人。

# 3.2物体表象与空间表象

尽管先天盲人几乎没有视觉经验，可能无法与明眼人形成一样的视觉表象，但是并不意味着盲人无法形成表象。近年来的表象研究发现视觉表象可以分为物体表象(object imagery)和空间表象(spatialimagery)两个不同的子系统；物体表象涉及物体的知觉特征，包括物体的形状、纹理、颜色和亮度等，空间表象涉及物体的空间位置、物体的各组成部分，以及各部分之间的空间关系和形态变化等信息(Blajenkova et al.,2006; Hoffler et al.,2017; Pearson, 2019;Roldan,2017; Sheldonet al.,2017)。个体形成表象时，对物体表象和空间表象的偏好存在差异(Lacey et al.,2011)，通过物体-空间表象问卷(Object-Spatial Imagers Questionnaire, OSIQ;Blajenkova et al.,2006)可以评估个体对两种表象类型的偏好和形成表象的能力。触觉系统也存在与视觉表象系统类似的物体表象和空间表象子系统，而且个体对两种表象类型的偏好会影响三维物体触觉信息的整合，进而影响对该物体的触觉识别(Lacey etal.,2011)。前文提到对于三维物体的触觉识别，蒙眼明眼人受到视角影响，出现视角依赖，盲人则是视觉独立(Occelli etal.,2016)，本文认为这可能是因为盲人缺少视觉经验，可能难以形成物体表象，但是盲人具有丰富的触觉经验，可以根据触觉信息形成比较准确的空间表象，因此在触觉识别二维图像时更依赖空间表象。明眼人由于具有丰富的视觉经验，对于熟悉的物体，已经在头脑中形成了准确、丰富的物体表象，因为在触觉识别二维图像时更依赖物体表象，导致在角度改变之后，很难想象出物体的结构。

基于上述分析，本文认为触觉识别二维图像的认知过程可能涉及物体表象和空间表象这两种不同的表象加工模块。虽然表象调节模型可能解释了一部分触觉识别二维图像的机制，但该模型没有考虑两种表象类型的加工特点，以及个体对表象类型的偏好对触觉识别的影响。基于前人的研究，本文试图提出一个区分物体表象和空间表象加工模块的双表象加工模型，进一步扩展和丰富触觉识别二维图像的理论观点。

# 3.3双表象加工模型

针对触觉识别二维图像的认知机制，本文提出双表象加工模型（dual-imagery processingmodel)，如图2所示。该模型认为触觉识别二维图像包括两条表象加工的模块，一条是基于物体表象（涉及物体的纹理、形状和大小）的模块，另一条是基于空间表象（涉及物体的（空间关系、透视和视角）的模块，触觉识别二维图像需要依赖两个表象系统的有效信息整合。其主要观点包含以下三点：

第一，“触觉感知”模块接收来自位于皮肤、肌肉、肌腱和韧带的机械感受器提供的触觉和本体感觉信息，获取物体的纹理、形状和大小信息，并通过进一步的感觉整合，进一步获取物体各个部分的空间关系信息，以及透视和视角信息。空间表象要通过进一步的感觉整合，获取物体各个部分的空间关系信息后才能形成，但并不意味着空间表象在时间上就落后于物体表象，二者形成的先后顺序是依据当前执行的认知任务决定，有限的认知资源会在两类表象之间进行动态的分配。

第二，“工作记忆”模块接收来自“触觉感知”提供的物体信息（纹理、形状和大小）主要形成二维图像的物体表象，这一过程构成基于物体表象的加工子模块，“工作记忆”模块接收空间信息（空间关系、透视和视角）主要形成二维图像的空间表象，这一过程构成基于空间表象的加工子模块。

第三，触觉是否能够成功地识别二维图像，取决于物体表象和空间表象两条加工子模块的共同作用。“长时记忆”模块中存储着个体以往的知识经验和物体表征，与其他模块之间存在动态的、相互的信息传递。两种表象系统的成功整合需要在二维图像与三维空间的映射基础上对物体表象和空间表象进行匹配。如果物体表象与空间表象之间可以有效整合，那么促进个体通达长时记忆中的物体表征；如果两者不能有效地整合，则可能导致无法有效识别。通过大量触觉识别二维图像的学习和训练，可能会提升个体触觉识别二维图像的能力。

![](images/33da60b987a823b3f13fb60353e6015bf6084be767e9558a81bae5cfe6c7b55b.jpg)  
触觉学习   
图3双表象加工模型

虽然本文提出的双表象加工模型仍有待进一步的实验验证，但是目前有关蒙眼明眼人和视障者的二维图像触觉识别的研究结果可以作为该模型的辅助证据，该模型也可以对这些研究结果进行初步解释。

首先，双表象加工模型可以解释包含透视关系的二维图像为何更加难以触觉识别。正如前文所述，包含透视关系的三维视角的二维图像通常会降低其触觉识别的绩效(Gong et al.,2020;Lebaz.et al.,2012;Lederman et al.,1990；龚江涛 等,2018)。根据该模型，这可能是因为包含透视关系的三维视角势必扭曲了三维物体呈现在二维平面上的侧面的形状，通过触觉虽然可以获取线条之间的空间关系，但是可能导致构建的空间表象与三维物体本身的形状不一致，难以构建正确的物体表象，无法与长时记忆中的物体表征成功匹配，增加了对二维图像识别的难度。

其次，双表象加工模型可以解释二维图像匹配时出现的视角偏好。前文所述的视角偏好(Gong et al.,2020; Heller et al.,2006; Heller etal.,2009; Sinha& Kalia,2012；龚江涛 等,2018)可能是因为特定视角呈现的二维图像可以使触摸过程中产生的物体表象和空间表象更好地整合，从而导致该视角更容易识别。例如，诸如蝴蝶和裤子这类对称物体，当以对称面呈现时，其物体表象和空间表象更加一致，从而更易整合。

最后，双表象加工模型可以解决视觉经验的争议。以往研究对于视觉经验在触觉识别二维图像中的作用一直存在争议。有研究发现盲人的触觉识别二维图像的绩效比明眼人差(Cornoldi et al.,2009; Gong et al.,2020; Lederman et al.,1990)，然而，也有研究发现视障者和蒙眼明眼人的绩效没有显著差异(Heller et al.,2009;Lebaz.et al.,2012; Picard et al.,2010)。根据双表象加工模型，这可能是因为视觉经验也许并不直接影响触觉识别二维图像的绩效，但是却影响个体的表象能力和表象偏好，进而导致触觉识别二维图像的绩效出现差异。有研究发现当要求蒙眼明眼人、早期盲人和晚期盲人通过触觉记忆二维图像并进行再认测试时，发现三类被试的测试绩效存在显著差异，而且他们的任务绩效与其表象能力呈显著正相关(Picard etal.,2010)。此外，另一项研究发现在触觉记忆路线图并进行再认测试时，要求辨认圆点最后出现位置，蒙眼明眼人和先天盲人识别绩效无显著差异，当要求再认整个路线图时，蒙眼明眼人识别绩效更好(Cornoldietal.,2009)，这可能是因为明眼人倾向于使用物体表象以记忆整个路线图来完成再认测试，而先天盲人倾向于使用空间表象以记忆每个部位的相对位置，从而导致了再认整个路线图时的识别绩效差异。

# 4总结与展望

本文总结和梳理了影响触觉识别二维图像的主要视觉因素，并分析了其背后的可能神经机制，提出双表象加工模型以解释触觉识别二维图像的认知机制。当前，有关触觉识别二维图像的研究方兴未艾，未来仍有大量的科学问题和应用难题亟待解决。

首先，需要对本文提出的双表象加工模型进行系统的实验验证。基于该模型的观点，以往研究中发现的视障人群与明眼人在触觉识别二维图像（甚至包括触觉识别三维物体）中表现出的差异，可能是因为两者在触觉过程中形成的表象类型不同。因此，未来应考察视觉障碍人群与明眼人是否存在物体表象和空间表象的不同偏好。目前针对明眼人的研究表明，视觉表象存在个体偏好，不同的表象偏好会影响物体表征的整合(Sathian et al.,2011)。那么视障群体中先天盲人、早期盲人以及晚期盲人之间是否也存在差异，以及盲人与明眼人之间是否存在群体差异，这一问题尚不明确。此外，目前考察触觉表象能力的研究大多是通过自我报告问卷进行测量(Pearson,2019)，这样测出的触觉表象能力不一定可靠。视觉表象的生动程度不是一个固定的特征，而是可能时刻动态变化，通过脑成像技术检测包括感知觉和整个视觉系统重叠程度在内的整个大脑网络的活动可以测量这些变化(Bergmann et al.,2016;Dijkstra et al.,2017;Pearson,2019)。结合前文提到的视觉和触觉的物体表象和物体属性的神经基础模式存在一定的重合(Desmarais et al.,2017; Lacey & Sathian,2014; Sathian,2016)，脑成像技术检测大脑活跃网络也可以用来测量触觉表象的生动程度。

其次，未来的研究需要进一步探讨本文提出的双表象加工模型如何在实践领域指导视障辅助设备中二维图像的设计和触觉引导。近年来，随着触觉电子显示技术的发展，触觉二维图像的设计和呈现迫切需要相关认知机制的研究作指导。双表象加工模型将触觉二维图像的识别过程分离为物体表象和空间表象加工两个模块，提示未来实践领域可以分别针对物体表象和空间表象加工进行设计构思，通过突出物体的诊断性形状结构(如物体的典型视角形状、对称性结构等）来促进物体表征模块，通过不同粗细和密度的线条提示透视、视角、遮挡或者镂空信息，进而促进空间表象模块的加工。未来需要基于该模型的观点，针对实践领域的具体问题开展验证性研究和应用研究，提出具有可操作性的设计和引导用户进行触觉感知的指导原则。同时，相关应用研究也可能反过来对触觉二维图像的认知机制研究提供启发和帮助。

第三，视障者缺乏的视觉经验是否可以通过大量的触觉学习进行弥补，从而使其更好地认识透视和视角关系，将二维图像与三维物体之间建立映射联系，仍有待进一步的研究。前人研究表明触觉学习和训练对触觉识别二维图像(Vinter et al.,2018;Vinter et al.,2020)和三维物体(Laceyetal.,2009)都有促进作用。未来研究应关注触觉学习是否能将二维透视图像与不同视角的三维物体建立映射，最终实现视角独立的触觉识别；关注触觉学习是否可以在二维图像的透视与三维物体的视角之间建立联系，消除透视对触觉识别二维图像的影响。

最后，未来也应该关注相关领域的发展心理学问题。已有研究发现练习可以增强儿童对二维图像的触觉识别能力(Overvliet & Krampe,2018; Vinter et al.,2018; Vinter et al.,2020)，触觉二维图像识别能力随着年龄的增长而提高(Mazellaet al.,2018;Withagen etal.,2013)。但是,目前关于触觉二维图像识别能力的年龄差异由何种原因导致，仍不清楚。这种识别能力的差异可能是因为成人的触觉探索策略比儿童成熟(Withagenet al.,2013)，也有可能是因为儿童和成人的空间参照系和工作记忆容量的差异(Overvliet&Krampe,2018)，还有可能是触觉识别形状的能力随着年龄的增长而增加(Mazellaetal.,2018)。对触觉识别二维图像能力的发展心理学研究将有助于进一步认识触知觉的认知机制，并为训练和培养儿童视障者的触知觉能力提供理论指导和建议。

# 参考文献

龚江涛，於文苑，曲同，刘烨，傅小兰，徐迎庆(2018)．影响触觉图像识别因素的量化分析．计算机辅助设计 与图形学学报,30(08):1438-1445.doi: 10.3724/SP.J.1089.2018.16799   
焦阳，龚江涛，徐迎庆(2016).盲人触觉图像显示器 graile 设计研究．装饰，No.273(01),96－98. doi:CNKI:SUN:ZSHI.0.2016-01-031   
卢纯福，宗先信(2017)．盲人触觉图形显示设计方法研究．设计,000(007),126-127.doi:10.3969/j.issn.1003- 0069.2017.07.054   
王葛彤，席洁，陈霓虹，黄昌兵.(2020).双眼视差的神经机制与知觉学习效应．心理科学进展,1-14. doi:10.3724/SP.J.1042.2021.00056   
於文苑，刘烨，傅小兰，龚江涛，徐迎庆(2019)．触觉二维图像识别的认知机制．心理科学进展,27(4),611- 622. doi:10.3724/sp.J.1042.2019.00611   
Amedi,A.,Jacobson,G.,Hendler,T.,Malach,R.,& Zohary,E.(2002).Convergence of visual and tactile shape processing in the human lateral occipital complex. Cerebral Cortex， 12(11)，1202 - 1212. doi:10.1093/cercor/12.11.1202   
Braile Authority of North America.2010.Guidelines and standards for tactile graphics.The Braille Authority of North America. Retrieved from http: //www.brailleauthority.org/tg/web-manual/index.html   
Bara,F.,Gentaz,E.,& Valente,D.(2O18).Theefectoftactileillustrations oncomprehension ofstorybooks bythree children with visual impairments: An exploratory study. Journal of Visual Impairment & Blindness,112(6), 759 - 765. doi:10.1177/0145482X1811200610   
Bauer, C.,Yazzolino,L.,Hirsch,G.,Cattaneo,Z,Vecchi,T.,& Merabet,L.B.(O1).Neuralcorrelatesassociated withsuperiortactile symmetryperceptionin theearlyblind. Cortex， 63， 104 -117. doi:10.1016/j.cortex.2014.08.003   
Bergmann,J.,Genc,E.,Kohler,A.,Singer,W.,&Pearson,J. (2o16).Smaler primaryvisual cortex isassciated with stronger, but less precise mental imagery. Cerebral Cortex,26(9),3838-3850.doi:10.1093/cercor/bhv186   
Blajenkova, O., Kozhevnikov, M.,& Motes, M.A. (2006). Object - spatial imagery: A new self - report imagery questionnaire. Applied cognitive psychology, 20(2),239 - 263.doi:10.1002/acp.1182   
Cacciamani,L.,& Likova,L.T.(2O16).Tactile object familiarity in the blind brain reveals thesupramodal perceptual-mnemonic nature of the perirhinal cortex. Frontiers in human neuroscience, 10， 92. doi:10.3389/fnhum.2016.00092   
Camponogara,I.,& Volcic,R. (2019). Grasping adjustments to haptic,visual,and visuo-haptic object perturbations are contingent on the sensory modality. Journal of neurophysiology， 122(6)， 2614 - 2620. doi:10.1152/jn.00452.2019   
Cavazos Quero,L.,Bartolomé,J.I.,& Cho,J. (2O21).Accessible visual artworks forblind and visually impaired people: Comparing a multimodal approach with tactile graphics. Electronics，10(3)， 297. doi: 10.3390/electronics10030297   
Cornoldi, C.,Tinti, C., Mammarella,I. C.,Re,A. M.,& Varoto,D. (209). Memory for an imagined pathway and strategy effects in sighted and in totally congenitally blind individuals.Acta Psychologica,130(1),11-16. doi:10.1016/j.actpsy.2008.09.012   
de Borst, A.W.,& de Gelder,B. (2016).fMRI-based multivariate patern analyses reveal imagery modality and imagery content specific representations in primary somatosensory, motor and auditory cortices. Cerebral Cortex,27(8),3994-4009.doi:10.1093/cercor/bhw211   
de Borst,A.W.,& de Gelder,B.(2019).Mental imagery follows similar corticalreorganization as perception: Intramodal and cross-modal plasticity in congenitally blind. Cerebral Cortex，29(7)，2859 - 2875. doi:10.1093/cercor/bhy151   
Delhaye,B.P.,Long,K. H.,& Bensmaia,S.J. (2018). Neural basis of touch and proprioception in primate cortex. Comprehensive Physiology, 8(4),1575-1602.doi:10.1002/cphy.c170033   
Desmarais,G.,Meade, M., Wels,T.,& Nadeau, M. (2017). Visuo-haptic integration in object identification using novel objects.Atention,Perception and Psychophysics,79(8),2478 -2498.doi:10.3758/s13414-017-1382-x   
Dijkstra,N., Bosch,S.E.,& Gerven, M.A.J.v.(2O17). Vividness ofvisual imagery depends on the neural overlap withperception in visual areas. The Journalofneuroscience, 37(5)， 1367-1373. doi:10.1523/JNEUROSCI.3022-16.2016   
Eck,J.,Kaas,A..,Mulders,J.L.,Hausfeld,L.,Kourtzi,Z.,& Goebel,R. (2016).The effectof task instructionon haptic texture processing: The neural underpinning of roughness and spatial density perception. Cerebral Cortex,26(1),384 - 401. doi:10.1093/cercor/bhu294   
Ernst,M.O., & Banks,M.S.(2o02). Humans integrate visual and haptic information in a statistically optimal fashion. Nature, 415(6870),429 - 433. doi:10.1038/415429a   
Flaxman,S.R.,Boure,R.R.A.,Resnkof,S.,Ackland,P.,Braithwaite,T.,Cicineli,.V...Vara,R.(217). Global causes of blindnessand distance vision impairment 1990-2O20: a systematic review and meta-analysis. The Lancet global health,5(12),1221 - 1234. doi:10.1016/s2214-109x(17)30393-5   
Freud,E., Culham, J. C., Plaut,D.C.,&Behrmann,M. (2017).The large-scaleorganization ofshape processing in the ventral and dorsal pathways.Elife,6,27576.doi:10.7554/eLife.27576   
Garcia,G. G., Grau,R.R.,Aldrich,F.K.,& Cheng,P.C.(2020). Multi-touch interaction data analysis system (MIDAS) for2-D tactile display research.Behavior Research Methods,52(2),813 -837.doi:10.3758/s13428- 019-01279-1   
Gong,J., Yu, W.,Ni,L.,Jiao,Y.,iu,Y.,Fu,X,& Xu,Y. (22o,October). "can't name it,butIcan perceiveit" conceptual and operational design of "tactile accuracy”assisting tactile image cognition.Paper presented at the The 22nd International ACM SIGACCESS Conference on Computers and Accessbility, Virtual Event, Greece. doi: 10.1145/3373625.3417015   
Gori,M.,Del Viva, M., Sandini, G.,& Burr,D.C. (20o8). Young children do not integrate visual and haptic form information. Current biology,18(9), 694 - 698. doi:10.1016/j.cub.2008.04.036   
Heed,T.,Buchholz,V.N.,Engel,A.K.,&Roder,B.(2O15).Tactileremapping: Fromcoordinate transformatioto integration insensorimotorprocessing. Trendsin cognitivesciences， 19(5)， 251 - 258. doi:10.1016/j.tics.2015.03.001   
Heller,M.,Riddle,T.,Fulkerson,E.,Wemple,L., Walk,A., Guthrie,S... Klaus,P.(2009). The influenceof viewpoint and object detail in blind people when matching pictures to complex objects.Perception,38,1234- 1250. doi:10.1068/p5596   
Heler,M.A.，Brackett, D.D., Scroggs,E.，Steffen, H.，Heatherly，K.，& Salik,S.(2002). Tangiblepictures: Viewpoint effects and linear perspective in visually impaired people. Perception， 31(6)， 747-769. doi:10.1068/p3253   
Heler,M.A., Kennedy,J.M.,Clark,A., McCarthy,M.,Borgert,A., Wemple,L,...Riddle,T. (206). Viewpoint and orientation influence picture recognition in the blind.Perception,35(10),1397 -1420.doi:10.1068/p5460   
Henson,R.N.A., Cansino,S.,Herron,J.E.,Robb, W.G.K,&Rugg,M.D.(20o3).Afamiliaritysignal in human anterior medial temporal cortex? Hippocampus,13(2),301-304. doi:10.1002/hipo.10117   
Hernandez-Perez,R., Cuaya,L. V., Rojas-Hortelano,E., Reyes-Aguilar,A., Concha,L.,& de Lafuente,V. (2017). Tactile object categories can be decoded from the parietal and lateral-ocipital cortices. Neuroscience, 352, 226 - 235. doi:10.1016/j.neuroscience.2017.03.038   
Hoffler,T.N., Koc - Januchta,M.,&Leutner,D.(2O17).More evidence for threetypes ofcognitive style: Validating the object - spatial imagery and verbal questionnaire using eye tracking when learning with texts and pictures. Applied cognitive psychology,31(1),109 -115. doi:10.1002/acp.3300   
Holdstock,J.S.,Hocking,J.,Notley,P.,Devlin,J.T,&Price,C.J.(oo9).Integratingvisualandtactileinforation in the perirhinal cortex. Cerebral Cortex,19(12),2993-3000.doi:10.1093/cercor/bhp073   
Kaas,A.L.,van Mier, H., Visser, M.,& Goebel,R. (20l3). The neural substrate for working memory of tactile surface texture. Human brain mapping, 34(5),1148 - 1162. doi:10.1002/hbm.21500   
Katus,T.,& Eimer,M. (202Oa).Retrospective selection in visual and tactile working memory is mediated by shared control mechanisms. Journal of cognitive neuroscience,32(3),546 - 557.doi:10.1162/jocn_a_01492   
Katus,T.,&Eimer,M. (202ob).Shifts of spatial atention invisual and tactile working memory arecontrolled by independent modality-specific mechanisms.Cerebral Cortex,30(1),296 -310.doi:10.1093/cercor/bhz088   
Kennedy, J.M., & Juricevic,I. (2o16). Foreshortening, convergence and drawings from a blind adult. Perception, 35(6), 847 - 851. doi:10.1068/p5316   
Kim,S.,Park,E.-S.,&Ryu,E.-S.(2o19).Multimedia vision for the visually impaired through2d multiarraybraille display. Applied Sciences, 9(5), 878.doi: 10.3390/app9050878   
Kitada,R. (2016). The brain network for haptic object recogniton.In (pp. 21 -37). Tokyo: Springer Japan. doi:10.1007/978-4-431-55772-2_2   
Kitada,R.,Ng,M.,Tan,Z.Y.,Lee,X.E,&Kochiyama,T. (2O21).Physicalcorrelatesofhuman-like sofness elicit high tactile pleasantness. Scientific Reports,11(1),16510.doi:10.1038/s41598-021-96044-w   
Klatzky,R.L.,& Lederman,S.J. (1988).The intellgent hand.In (Vol.21,pp.121-151): Elsevier Science & Technology. doi:10.1016/S0079-7421(08)60027-4   
Klatzky,R.L.,& Lederman,S.J. (20l1). Haptic object perception: Spatial dimensionality and relation to vision. Philosophical transactions.Biological sciences,366(1581),3097 -3105.doi:10.1098/rstb.2011.0153   
Lacey,S.,Peters,A,&Sathian,K. (2o7).Cro-modal objectrecognitionisviewpoit-independent.PloSone, 2(9), e890 - e890.doi:10.1371/journal.pone.0000890   
Lacey,S.,Pappas,M.,Kreps,A.,Lee,K.,& Sathian,K. (2o9).Perceptual learning of view-independence in visuo haptic object representations. Experimental Brain Research,198(2-3),329 -337. doi:10.1007/s00221-009- 1856-8   
Lacey,S.,Lin,J.B.,& Sathian,K. (20l1).Object and spatial imagery dimensionsinvisuo-haptic representations. Experimental Brain Research,213(2),267-273.doi:10.1007/s00221-011-2623-1   
Lacey, S.,& Sathian, K.(2O14). Visuo-haptic multisensory object recognition,categorization,and representation. Frontiers in psychology, 5,730.doi:10.3389/fpsyg.2014.00730   
Lebaz.,Jouffrais,& Picard.(2012).Haptic identificationof raised-line drawings:High visuospatial imagers outperform low visuospatialimagers.Psychologicalresearch,76(5),67- 675.doi:10.1007/s00426-01-0351- 6   
Lebreton,P.(2016).Assessing human depth perception for 2Dand3D stereoscopic images and video andits relation withtheoverall3D QoE. (doctorial dissertation)，Technische Universitaet Berlin,Germany. doi:10.14279/depositonce-5126   
Lederman,S.J.,Klatzky,R.L., Chataway,C.,& Summers,C.D.(199o).Visual mediationand the haptic recognition of two-dimensional pictures of common objects. Perception Psychophysics， 47(1)， 54- 64. doi:10.3758/BF03208164   
Likova,L.T. (2012).Drawing enhances cro-modal memory plasticity inthe human brain: Acase study ina totally blind adult. Frontiers in human neuroscience, 6(2012),44 - 44.doi:10.3389/fnhum.2012.00044   
Loomis,J.,Klatzky,R.L,&Lederman,S.J. (1991).Similarityoftactualandvisual picturerecognition with liited field of view. Perception, 20(2),167 - 177. doi:10.1068/p200167   
Mazella,A.,Albaret,J.-M.,&Picard,D.(2018).The development of haptic processing skils from childhood to adulthood by means of two-dimensional materials. Canadian journal of experimental psychology,72(1), 48 - 57. doi:10.1037/cep0000121   
Newell,F.,Erst,M.,Tjan,B.,&Bulthoff,H.(Oo1).Viewpointdependence invisualand hapticobjectrecogiion. Psychological science,12,37 - 42. doi:10.1111/1467-9280.00307   
Nguyen,A. M.,Ferro,T.J.,& Pawluk,D.T. V. (2018). Efectiveness of using local cues to indicate perspective in tactile diagrams for people with visual impairments.Journal of Visual Impairment & Blindness,112(6),731- 744. doi:10.1177/0145482X1811200608   
Occeli, V.,Lacey,S.,tephens,C.,John,T.,& Sathian,K.(2016).Hapticobjectrecognitionis view-independent in early blind but not sighted people.Perception, 45(3),337-345. doi:10.1177/0301006615614489   
Overvliet, K.E. Wagemans, J.,& Krampe,R. T. (2013). The effects of aging on haptic 2D shape recognition. Psychology and Aging,28(4),1057 - 1069.doi:10.1037/a0033415   
Overvliet,K.E.,& Krampe,R.T. (2018).Haptic two-dimensional shape identification in children,adolescents,and young adults. Journal of experimental child psychology, 166,567 - 580. doi:10.1016/j.jecp.2017.09.024   
Pasqualotto,A., Ng, M.,Tan,Z.Y.,& Kitada,R. (2O2). Tactile perception ofpleasantnessin relation to perceived softness. Scientific Reports,10(1),11189. doi:10.1038/s41598-020-68034-x   
Pearson,J. (20l9).The human imagination: The cognitive neuroscience of visual mental imagery. Nature Reviews Neuroscience,20(10),624 - 634.doi:10.1038/s41583-019-0202-9   
Perini,F.,Powel,T.,Wat, S.J.,&Downing,P.E.(2O2O).Neuralrepresentationsofhapticobjectsize inthehuman brain revealed by multivoxel fMRI pattrns. Journal of neurophysiology， 124(1)， 218 - 231. doi:10.1152/jn.00160.2020   
Picard,D.,Lebaz,S.,Joufrais,C.,&onier,C.().Hapticrecogitionoftwo-dimensionalraised-linepters by early-blind,late-blind,and blindfolded sighted adults.Perception,39(2),224-235.doi:10.1068/p6527   
Prather,S.C., Votaw, J. R., & Sathian,K.(2Oo4). Task-specific recruitment of dorsal and ventral visual areas during tactile perception. Neuropsychologia, 42(8),1079 - 1087.doi:10.1016/j.neuropsychologia.2003.12.013   
Qian,J.,& Petrov, Y. (2O16).A depth ilusion supports the model of general object constancy: Size and depth constanciesrelated byasame distance-scalingfactor.Vision research， 129， 77-86. doi:10.1016/j.visres.2016.09.015   
Roldan,S.M. (2O17). Object recognition in mental representations: Directions for exploring diagnostic features through visual mental imagery.Frontiers in psychology,8(5),833-833.doi:10.3389/fpsyg.2017.00833   
Sathian,K.,Lacey,S.,Stila,R.,Gibson, G.O.,Deshpande,G.,Hu,X... Glielmi, C.(2011). Dual pathways for haptic and visual perception of spatial and texture information. NeuroImage, 57(2)， 462 - 475. doi:10.1016/j.neuroimage.2011.05.001   
Sathian,K. (20l6).Analysisofhaptic information inthecerebralcortex.JournalofNeurophysiology,116(4),1795- 1806. doi:10.1152/jn.00546.2015   
Senna,I.,Andres,E.,McKyton,A.,Ben-Zion,1,Zohary,E.,&Ernst,M.O.(2021).Development of multisensory integration following prolonged early-onset visual deprivation. Current biology,31(21), 4879 - 4885.e4876. doi:10.1016/j.cub.2021.08.060   
Sheldon,S.，Amaral, R.,& Levine,B.(2O17). Individual differences in visual imagery determine how event information is remembered. Memory, 25(3),360 - 369.doi:10.1080/09658211.2016.1178777   
Sinha, P.,& Kalia, A.A. (20l2). Tactile picture recognition: Errors are in shape acquisition or object matching? Seeing Perceiving, 25(3-4),287 - 302. doi:10.1163/187847511X584443   
Stoesz,M.R., Zhang,M., Weisser,V.D.,Prather,S.C.,Mao,H.,& Sathian,K. (2003). Neural networks active during tactile form perception: Common and diferential activity during macrospatial and microspatial tasks. International Journal of Psychophysiology, 50(1),41 - 49.doi:10.1016/S0167-8760(03)00123-5   
Szubielska,M.,Niestorowicz,E.,& Marek,B.(2019).The relevance ofobject size to the recognizabilityofdrawings by individuals with congenital blindness. Journal of Visual Impairment & Blindness,113(3), 295 - 310. doi:10.1177/0145482x19860015   
Tarr, M.J.,& Hayward, W. G. (2017).The concurrent encoding of viewpoint-invariant and viewpoint-dependent informationinvisualobjectrecognition.Visualcognition,25(1-3)，100-121. doi:10.1080/13506285.2017.1324933   
Theurel,A., Wit,A.,Claudet,P.,Hatwell,Y.,&Gentaz,E. (3).Tactilepicturerecognition byearlyblindcidren: The effect of ilustration technique. Journal of experimental psychology: Applied，19(3)， 233 - 240. doi:10.1037/a0034255   
Thompson,L.J., Chronicle,E.P.,& Collins,A.F. (2006). Enhancing 2-D tactile picture design from knowledge of 3-D haptic object recognition. European Psychologist,11(2),110 - 118.doi:10.1027/1016-9040.11.2.110   
Toprak,S., Navarro-Guerrero,N.,& Wermter, S. (2018). Evaluating integration strategies for visuo-haptic object recognition. Cognitive Computation,10(3),408 -425.doi:10.1007/s12559-017-9536-7   
Vinter,A., Bonin,P.,& Morgan, P. (2018). The severity of the visual impairment and practice matter fordrawing ability in children.Research in developmental disabilities,78,15-26.doi:10.1016/j.ridd.2018.04.027   
Vinter,A.,Orlandi,O.,& Morgan,P.(2O20).Identification of textured tactile pictures in visually impaired and blindfolded sighted children. Frontiers in psychology,11,345. doi:10.3389/fpsyg.2020.00345   
Wan, C.,Cai,P.,Guo,X., Wang,M.,Matsuhisa,N.,Yang,L.,Lv,Z.,Luo,Y.,Loh, X.J.,& Chen, X.(2020).An artificial sensory neuron with visual-haptic fusion. Nature Communications,11(1),4602.doi:10.1038/s41467- 020-18375-y   
Withagen,A., Kappers,A. M.L., Vervloed, M.P.J., Knoors,H.,& Verhoeven,L. (2013). The use of exploratory procedures by blind and sighted adults and children. Attention,perception &psychophysics,75(7),1451 - 1464. doi:10.3758/s13414-013-0479-0   
Woods,A.T.,Moore,A., & Newel,F.N. (2008). Canonical views in haptic object perception. Perception,37(12), 1867 - 1878. doi:10.1068/p6038   
Yang, J.,Yu,Y., Kunita,A., Huang,Q., Wu,J.,Sawamoto,N.,&Fukuyama,H. (2014). Tactile priming modulates the activation ofthe fronto-parietal circuit during tactile angle match and non-match processing: An fMRI study. Frontiers in human neuroscience,8, 926 - 926. doi:10.3389/fnhum.2014.00926   
Yasaka,K., Mori, T.,Yamaguchi, M.,& Kaba, H. (2019).Representationsof microgeometric tactile information during object recognition. Cognitive processing, 20(1),19 - 30.doi:10.1007/s10339-018-0892-3   
Yau,J.M., Kim,S.S.,Thakur, P.H.,& Bensmaia,S.J. (2016).Feling form: The neural basis of haptic shape perception. Journal of neurophysiology, 115(2),631 - 642. doi:10.1152/jn.00598.2015   
Yoshida,T.,Yamaguchi,A.,Tsutsui,H.,& Wake,T. (2015). Tactile search forchange has less memory than visual search for change.Atention, perception &psychophysics,77(4),1200-1211.doi:10.3758/s13414-014-0829-   
Yu, J.,Wu, Q.,Yang,J.Takahashi,S.,Ejima,Y.,& Wu,J. (2Ol7,August).Astudyofshape discriminationfortactile guide maps. In 2017 IEEE International Conference on Mechatronics and Automation (ICMA)(pp.565 - 570). IEEE. doi: 10.1109/ICMA.2017.8015879   
Zhang, Q.,& Li,S.(2020).The roles of spatial frequency in category-level visual search ofreal-world scenes.PsyCh journal, 9(1), 44 - 55. doi:10.1002/pchj.294

# Cognitive Mechanisms of 2D-to-3D Spatial Information

# Transformation in Haptic Recognition of 2D Images

QIN Yinghui1,2² ,YU Wenyuan1,2.3 ,FU Xiaolan1,2 ,LIU Ye1,2 (1 State Key Laboratory of Brain and Cognitive Science, Institute of Psychology, Chinese   
Academy of Sciences, Beijing 100101, China)(² Department of Psychology, University of Chinese   
Academy of Sciences,Beijing 10o049,China)(' Research Institute of Basic Theories, Zhejiang Lab, Hangzhou 311121,China)

Abstract: Two-dimensional (2D） tangible image is an important alternative way for visually impaired people to obtain image information. Most existing tactile 2D images are tangible line drawings directly transformed from visual 2D images. The expression of spatial information in the visual 2D images usually follows principles of perspective and viewpoint transforming thredimensional (3D) space into 2D planar. The mapping from 2D image to 3D space in visual system is learned through long-time perceptual learning. However, it stil needs further exploration about cognitive mechanisms of 2D-to-3D spatial information transformation established by haptic system in haptic recognition of 2D images. The visual factors that affect 2D to 3D spatial information transformation in haptic recognition of2D images mainly include perspective, viewpoint, occlusion, texture gradient, and hollow-out. When directly transforming 2D visual images into 2D tactile images, the visual factors mentioned above usually interfere with tactile recognition. Based on the findings of existing research，a dual-imagery processing model is proposed to explain the mechanisms of 2D-to-3D spatial information transformation by touching 2D tangible images. According to the model, haptic recognition of 2D images depends on the integration of two imagery systems,i.e., the object imagery system concerning about the size, shape,and texture features of an object,and the spatial imagery system concerning about the spatial relationship of the object following perspective and viewpoint principles. The successful integration of information from the two imagery systems requires the match between the object imagery to the spatial imagery based on the mapping of 2D image to 3D space. Dual-imagery processing model could contribute to the further exploration of haptic recognition and related cognitive mechanism,and provide theoretical guidance for the design of 2D tangible images.

Keywords: haptics, two-dimensional image,haptic recognition, perspective, viewpoint