# 基于理想点一矢量余弦投影的多属性决策方法

孔造杰1,²，李斌1，赵啸天1，耿立沙1,3，孙可远1(1．河北工业大学 经济管理学院，天津 300401;2.吉林大学珠海学院，广东 珠海 519041;3．石家庄科技工程职业学院管理工程系，石家庄050800)

摘要：针对现有的多属性问题决策过程大多无法体现决策者对产品的个人的多等级偏好以及缺乏一个客观合理的多属性评价基准的不足，提出一种基于矢量余弦投影的多属性偏好决策方法。首先，通过多等级成对比较法来确定决策者对各项属性的偏好度；其次，根据理想点来确定理想评价对象各项属性的理想值；最后，利用矢量余弦投影法计算一般多属性问题矢量在理想多属性问题矢量方向上的投影强度，然后根据强度的大小确定各个方案的优先级排序结果。通过一个算例验证了所提方法的有效性和可行性。

关键词：多属性问题；个人多等级偏好；理想点法；矢量余弦投影法 中图分类号：C934 doi: 10.3969/j.issn.1001-3695.2018.03.0166

# Multiple attribute decision making based on ideal point-vector cosine method

Kong Zaojiel, ², Li Bin1, Zhao Xiaotian1, Geng Lishal,³, Sun Keyuan1 (1.SchoolofEconomics&ManagementHebeiUniversityofTechnlogyianjin301,China;2ZhuhaiColegeofJilin University,Zhuhai Guangdong519041,China;3.Dept.ofManagementEnginering,Shjiazhuang Science&Technology Vocational Collge, Shijiazhuang 05080o, China)

Abstract:In viewofthedeficienciesofcurrent multipleatribute decision making methods cannotreflectthe individual preference on multiple gradesof thedecision makersand lack anobjectiveand reasonable multiple atribute evaluation benchmark.Thispaperproposedamultipleatributedecision making methodbasedonthe vectorcosine method.Firstly,itused thepairwisecomparisonofalternativesonmultiple grades todeterminedecisionmaker's preferenceforeachatribute.Secondly, itusedtheidealpointmethdtodeterminetheidealvalueofeachatributefortheidealevaluationobject.Finalyitusedthe vector cosine projection method tocalculate the projection intensityof the general multipleatribute problem vector nthe directionoftheidealmultipleatribute problemvector,these projectionintensities determinetherankingresultofteshemes. Through an example to demonstrate the feasibility of effectiveness of the proposed method.

Key words: multipleatribute decision making method; individual preference on multiple grades; ideal point method; vector cosine projection method

# 0 引言

随着人们对决策问题研究的深入，决策过程所考虑的问题属性数目也随之增加，使得多属性问题决策的难度也随之提高。所谓的多属性决策问题是指在综合考虑多个问题属性的前提条件下，利用科学的决策方法对决策方案进行客观与合理的评价，然后更具评价结果来对方案进行排序或优选，这类多属性决策问题广泛的存在现实生活中的众多领域，如工程、医疗卫生、经济和管理等众多领域。多属性决策问题已经成为决策领域关注的焦点，由于决策问题自身的复杂性，使得多属性决策问题的处理方法相对局限。目前，对于多属性决策问题的研究已经成为学术界研究的焦点，由于多属性问题具有主观性、模糊性、不确定性等特点，这使得对其的研究没有一个统一的标准，学者们从不同的视角出发对多属性决策问题进行了研究。

通过对多属性进行赋权，然后再结合相应的方法计算综合评价值，根据综合评价值来对多属性方案进行排序和选择，这种研究模式受到广泛的运用。在多指标问题的决策过程中，无论是过程的客观性还是决策者的个人偏好，这两者均对多属性权重有着重要的影响作用，在计算多属性间的权重值时需要将主客两个方面的影响进行综合考虑[1]。由于属性权重取值关乎整个决策的科学性与合理性，属性权重的取值不合理将有可能影响整个决策的成败，所以属性的权重显得尤为重要。属性权重计算方面的研究是学术界研究的热点，现阶段对于多属性权重的确定主要有主观赋权法、客观赋权法和主客观赋权法。其中，主观赋权法往往根据决策者对各个属性的主观的重视程度来进行赋权，这样就使得决策具有较大的随意性与主观性。客观赋权法则是每项属性按照一定的规则进行自动赋权计算的方法，这种以规则为导向的赋权方法虽能保证决策过程的客观性，但是无法体现决策者的个人偏好。主客观赋权法则是主观赋权法和客观赋权法这两类方法的一个综合，它既能保留决策者的个人偏好，又能尽量保证决策过程的客观性和合理性，因此，该种方法受到众多学者的青睐，学者们对主客观赋权进行了一系列的深入的拓展研究。陈伟[2]等将专家群体对属性的偏好考虑到属性权重的计算过程中来，通过建立比率标度得到主观权重，然后在此基础上采用组合赋权来获得各项属性的权重。何大义[3]等提出利用最小叉熵准则构建优化模型将属性的主观值矩阵和客观值矩阵分别确定属性的主观权重和客观权重进行集成。宋冬梅[4]等针对多目标多属性决策方法中,传统的主观赋权法决策者主观偏好过强,而客观赋权法又过多地依赖实测数据的局限性,提出一种新的主客观赋权方法。上述方法在计算属性的权值时大多数只是采用简单的赋权方法，如AHP（层次分析法）、ANP（网络分析法）等方法，这些方法一般只能构建单等级上的比较关系，而不能同时表达多种不同偏好关系。已有的关于多属性问题决策的研究的方法常用的有区间数[5\~7]、直觉模糊集[8\~10]、犹豫模糊数[11\~14]等，这些方法大多计算过程复杂且在应用时存在一定的局限性造成方法适用性不强而不宜推广。

综上所述，本文提出基于矢量余弦投影的多属性偏好决策方法，首先，通过多等级成对比较法来确定决策者对各项属性的偏好度；其次，根据理想点来确定理想评价对象各项属性的理想值，最后，将方案的每项属性作为一个维度，利用矢量余弦投影法计算一般多属性问题矢量在理想多属性问题矢量方向上的投影强度，根据强度的大小确定各个方案的优先级排序结果。

# 1 基础理论

# 1.1多等级成对比较法

多级偏好关系的最终体现需要借助多等级成对比较法，该方法最早应用在多属性权重计算领域[15]。由于该方法计算所得的权重能够克服传统方法只能实现单等级成对比较这一缺点，使其受到众多学者的青睐。鉴于多等级偏好法在多属性问题权重计算方面的优异表现，所以在本文中的需求偏好参数环节引入该方法来计算需求偏好度。为了能够充分表达决策者对产品需求的多级偏好，需定义一个分布式偏好关系。分布式偏好关系定义在多等级对称框架上，它可以同时描述成对对象间的优于、劣于、无差异和不确定这四种关系，经典的分布式偏好理论所用的识别框架为 $\Omega = \left\{ H _ { \scriptscriptstyle 1 } , H _ { \scriptscriptstyle 2 } , . . . , H _ { \scriptscriptstyle N } \right\}$ ，也被称之为一种分布式偏好。等级 $H _ { 1 } , H _ { 2 } , H _ { 3 } , . . . , H _ { N }$ 表示成对对象间由弱至强的优于程度， $H _ { - 1 } , H _ { - 2 } , H _ { - 3 } , . . . , H _ { - N }$ 表示成对对象间由弱至强的劣于程度， $H _ { 0 }$ 表示的是对象之间的无差异度，以 $H _ { 0 }$ 为中心，两边等级呈对称性。

# 1.2理想点法

理想点法的思路是决策者利用已有的信息构造出一个满足所有目标的理想点，理想点法常常和多指标问题联系在一起，它有着广泛的适用范围[16-17]。理想点法将指标分为正指标和逆指标这两大类，其中正指标的取值越大越好，逆指标的取值越小越好。理想点与逆理想点的定义如下：

当指标为正指标时，

$$
\left\{ \begin{array} { l l } { f _ { i } ^ { * } ( + ) = \operatorname* { m a x } f _ { i } ( x ) , i = 1 , 2 , . . . , n , } \\ { f _ { i } ^ { * } ( - ) = \operatorname* { m i n } f _ { i } ( x ) , i = 1 , 2 , . . . , n , } \end{array} \right.
$$

当指标为逆指标时，

$$
\left\{ \begin{array} { l l } { { f _ { i } } ^ { * } ( + ) = \operatorname* { m i n } f _ { i } ( x ) , i = 1 , 2 , . . . , n , } \\ { { f _ { i } } ^ { * } ( - ) = \operatorname* { m a x } f _ { i } ( x ) , i = 1 , 2 , . . . , n , } \end{array} \right.
$$

通过式(1)(2)确定正理想点 $f _ { i } ^ { * } ( + )$ 和逆理想点 $f _ { i } ^ { * } ( - )$ 。

# 1.3矢量余弦投影法

矢量余弦投影被广泛的运用到多维领域，它具有操作简单，使用方便等优点，矢量余弦投影法的示意图如图1所示。

![](images/7734bf40d1228829245fad9aa6bf7ef6087c336e35c00bee4b2a23be3993757a.jpg)  
图1余弦投影示意图

如图1所示，矢量 $\vec { { } _ { R } }$ 在水平方向上的余弦投影强度为$\left| { \vec { R } } \right| \cos a$ 。

# 2 矢量余弦投影的多属性偏好决策

# 2.1问题描述

假设一个多属性决策问题包括 $m$ 个备选方案和 $n$ 个评价属性，令 $Y = \left\{ y _ { 1 } , y _ { 2 } , \cdots , y _ { m } \right\}$ ， ${ \big ( } i = 1 , 2 , \cdots , m { \big ) }$ 为方案集， $X = \left\{ x _ { 1 } , x _ { 2 } , \cdots , x _ { n } \right\}$ ， ${ \bigl ( } j = 1 , 2 , \cdots , n { \bigr ) }$ 为属性集，由于受到决策者个人偏好的影响，使得其对于属性集中的各项属性偏爱程度不一致，针对某一特定的现实情况，决策者需从方案集中的众多方案中选取一个最适合当前环境的决策方案出来。

# 2.2多属性决策方案的矢量化

对于多属性决策方案而言，各项属性之间是相互独立的，彼此之间没有相关关系，这一点与多维向量的理论含义相契合，因此，本文考虑引入多维向量的概念，将每项属性看成一个维度，相应的每个多属性决策方案转化成一个多维矢量，当多属性方案所包含的属性数目为二时，此时的多属性决策方案可以在一个二维坐标系中用一个二维矢量来表示，两个属性的决策问题方案如图1所示,其中A1和 A2分别代表一个两个属性的决策问题。当多属性方案所包含的属性为三个时，此时的多属性方案可以在一个三维坐标系中用一个三维矢量来表示，三个属性的决策问题方案如图2所示，其中B1和B2分别代表一个三个属性的决策问题。依次类推可以拓到更多的维度，目前能够感知并且绘制的坐标系的最大维度是三维，虽然四维及以上的维度的坐标系无法感知和绘制，但是它们是实际存在的。

![](images/c4ad4b86954e09b967ed30263a62aa54ed651a51fd7013777f064f7aa9246881.jpg)  
图1二维矢量示意图

![](images/5400607d4d44a625b736f84e46fea858966d64cb476b2c6365a7a96d86d4c5fc.jpg)  
图2三维矢量示意图

# 2.3多属性偏好度的计算

利用多等级成对比较法计算出决策者对于每项属性的偏好度，决策者属性偏好度的主要求解步骤如下：

a）制定出对称框架 $\Omega$ 和等级得分值 $S _ { H }$ ,利用式（3）计算得分矩阵 $S$ ;

$$
S _ { i j } = [ s _ { i j } ^ { - } , s _ { i j } ^ { + } ] = [ \sum _ { n = - N } ^ { N } S \left( H _ { n } \right) \times b _ { i j } \left( H _ { n } \right) + S \left( H _ { - N } \right) b _ { i j } \left( \Omega \right) , \sum _ { n = - N } ^ { N } S \left( H _ { n } \right) \times b _ { i j } \left( H _ { n } \right) + S \left( H _ { N } \right) b _ { i j } \left( \Omega \right) ]
$$

b)决策者从不同的角度来考虑对象集中的各个对象，最后给出对象集上的分布式偏好关系 $D$ ·c）根据前两步所得的 $S$ 矩阵，计算出正规化的得分矩阵S,其中

$$
\overset { ^ { - } } { S } = \left( \overset { ^ { - } } { S _ { i j } } = [ s _ { i j } ^ { - } , s _ { i j } ^ { + } ] \right) _ { M \times M } , \overset { ^ { - } } { s _ { i j } } = \frac { 1 + s _ { i j } ^ { - } } { 2 } , \overset { ^ { + } } { s _ { i j } } = \frac { 1 + s _ { i j } ^ { - } } { 2 }
$$

d）在正规化得分矩阵 $\bar { s }$ 的基础上，通过式（4）构造各个对象的优先权的优化模型，接着由式（5）来求取 $[ w _ { i } ^ { - } , w _ { i } ^ { + } ]$ ,其中 $i = 1 , 2 , 3 , . . . , M$

$$
w _ { i } ^ { - } = \frac { 1 } { 1 + \displaystyle \sum _ { j = 1 , j \neq i } ^ { M } \frac { 1 - s _ { i j } } { s _ { i j } } } \quad \quad w _ { i } ^ { + } = \frac { 1 } { 1 + \displaystyle \sum _ { j = 1 , j \neq i } ^ { M } \frac { 1 - s _ { i j } } { s _ { i j } } }
$$

e）利用式（6）求取 $p$ ，形成可能度 $P$ ;

$$
\operatorname* { m a x } \left\{ 1 - \operatorname* { m a x } ( \frac { w _ { j } ^ { + } - w _ { i } ^ { - } } { l ( w _ { i } ) + l ( w _ { j } ) } , 0 ) , 0 \right\} , \# , \# \# l ( w _ { i } ) = w _ { i } ^ { + } - w _ { i } ^ { - } , l ( w _ { j } ) = w _ { j } ^ { + } - w _ { j } ^ { - }
$$

f）结合可能度矩阵 $P$ ，利用式（7）计算各对象的效用值$u _ { i } ( i = 1 , 2 , . . . , M ) ;$ （204号

$$
u _ { i } = \frac { \displaystyle \sum _ { j = 1 } ^ { M } p _ { i j } } { \displaystyle \sum _ { i = 1 } ^ { M } \sum _ { j = 1 } ^ { M } p _ { i j } } = \frac { \displaystyle \sum _ { j = 1 } ^ { M } p _ { i j } + \frac { M } { 2 } - 1 } { M ( M - 1 ) } , i = 1 , 2 , . . . , M .
$$

效用值的大小也可以反映每个对象的重要性，求得的效用值即为相应对象偏好度ui。

# 2.4多属性决策方案的矢量化与矢量投影强度计算

根据式（8）将决策者的个人偏好和方案的各项属性评价值两者结合在一起确定每个方案的偏好多属性矢量 $\vec { A } _ { i }$ 口

$$
\vec { A _ { i } } = ( u _ { 1 } \bullet x _ { i 1 } , u _ { 2 } \bullet x _ { i 2 } , \cdot \cdot \cdot , u _ { j } \bullet x _ { i j } )
$$

其中: $i$ 的最大取值为多属性方案数, $j$ 的最大取值为多属性方案的属性个数。结合前面提到的理想点的计算式(6)确定理想偏好多属性决策方案矢量 $\vec { \mathbf A }$ 。

$$
\stackrel {  } { A } = ( u _ { 1 } \bullet \operatorname* { m a x } x _ { i 1 } , u _ { 2 } \bullet \operatorname* { m a x } x _ { i 2 } , \cdots , u _ { j } \bullet \operatorname* { m a x } x _ { i j } )
$$

前面介绍了多属性决策问题的矢量化过程，通过式（8）成功将一个多属性问题转化成为一个多维矢量，通过式（9）确定理想偏好多属性决策方案。接下来则是最为关键的是如何将多属性问题中的多属性给集成在一起，通过集成所得到的数值来评价各个方案的优劣。在处理多指标问题的过程中，加权平均是最为常见的方法，权重的求取显得十分关键，但是，在实际应用中权重的求取往往带有较大的主观性在其中。鉴于此，本文选择矢量余弦投影方法来进行多属性的集成，它克服线性加权平均方法计算权重过程中的主观性不易控制的缺点，保证计算过程的客观性。

![](images/e46d3accf41fd9eb22e9b68bedd2fbb528c26a385743d168abe2a815dc4d7b69.jpg)  
图4多属性矢量余弦投影示意图

根据式（10）来计算一般多属性方案矢量在理想多属性决策方案矢量上的投影强度，根据所得方案投影强度 $\delta _ { i }$ 对各个方案进行排序。

$$
\delta _ { i } = \frac { \vec { S } _ { i } \bullet \vec { S } } { \left| \vec { S } \right| } = \frac { ( u _ { 1 } ^ { 2 } x _ { 1 1 } \bullet \operatorname* { m a x } x _ { i 1 } + u _ { 2 } ^ { 2 } x _ { 1 2 } \bullet \operatorname* { m a x } x _ { i 2 } + \dots + u _ { j } ^ { 2 } x _ { i j } \bullet \operatorname* { m a x } x _ { i j } ) } { \sqrt { u _ { 1 } ^ { 2 } \bullet \operatorname* { m a x } x _ { i 1 } ^ { 2 } + u _ { 2 } ^ { 2 } \bullet \operatorname* { m a x } x _ { i 2 } ^ { 2 } + \dots u _ { j } ^ { 2 } \bullet \operatorname* { m a x } x _ { i j } ^ { 2 } } }
$$

# 3 决策步骤

综上所述可得基于矢量余弦投影的多属性偏好决策方法的计算步骤如下所示：

a)根据多等级成对比较方法计算决策者对于各项属性的偏好度ui；

b)将上一步所求的结果代入式（8）中，计算得到多属性偏好方案矢量；

c)将多属性偏好方案矢量化后，并根据式（9）确定理想多属性偏好方案矢量；

d)利用式（10）计算一般多属性偏好方案矢量在理想多属性偏好方案矢量方向上的投影强度；

e)根据求得的所有方案矢量的投影强度来进行排序，选出最满意的方案。

# 4 算例分析

某公司组织公司员工外出旅游，可供选择的旅游目的地有4个分别为杭州、北京、昆明、哈尔滨，旅游目的地的选取主要受景色、费用、饮食和住宿这四个方面的影响，现在企业的领导者需要在这4个可供选择的目的地中选择出最终的目的地，很明显这是一个多属性决策问题，其中的景色、费用、饮食和住宿分别代表四个属性 $p _ { 1 }$ 、 ${ { p } _ { 2 } }$ 、 ${ p } _ { 3 }$ 、 $p _ { 4 }$ ，杭州、北京、昆明、哈尔滨分别用 $S _ { 1 }$ 、 $S _ { 2 }$ 、 $S _ { 3 }$ 、 $S _ { 4 }$ 。为了说明所提方法的有效性，下面分别利用AHP（层次分析法）和本文所提方法进行决策分析。

# 4.1层次分析法决策分析

通过对案例进行分析可得图5所示的层次结构示意图。

![](images/fe0d972155e3231dbdd714bce5a4a94ada7d083ef23f10541fad1a9ceaea0a4e.jpg)  
图5层次结构示意图

根据图5所示的层次结构图，通过专家打分法获得的判断矩阵如下：

$$
A = { \left[ \begin{array} { l l l l } { 1 } & { 2 } & { 1 / 2 } & { 2 } \\ { 1 / 2 } & { 1 } & { 1 / 3 } & { 1 } \\ { 2 } & { 3 } & { 1 } & { 3 } \\ { 1 / 2 } & { 1 } & { 1 / 3 } & { 1 } \end{array} \right] } B 1 = { \left[ \begin{array} { l l l l } { 1 } & { 2 } & { 2 } & { 3 } \\ { 1 / 2 } & { 1 } & { 1 } & { 2 } \\ { 1 / 2 } & { 1 } & { 1 } & { 2 } \\ { 1 / 3 } & { 1 / 2 } & { 1 / 2 } & { 1 } \end{array} \right] }
$$

$$
B 2 = { \left[ \begin{array} { l l l l } { 1 } & { 2 } & { 1 / 3 } & { 1 / 3 } \\ { 1 / 2 } & { 1 } & { 1 / 4 } & { 1 / 4 } \\ { 3 } & { 4 } & { 1 } & { 1 } \\ { 3 } & { 4 } & { 1 } & { 1 } \end{array} \right] } B 3 = { \left[ \begin{array} { l l l l } { 1 } & { 2 } & { 1 } & { 2 } \\ { 1 / 2 } & { 1 } & { 1 / 2 } & { 1 } \\ { 1 } & { 2 } & { 1 } & { 2 } \\ { 1 / 2 } & { 1 } & { 1 / 2 } & { 1 } \end{array} \right] }
$$

$$
B 4 = \left[ \begin{array} { l l l l } { 1 } & { 1 } & { 1 / 2 } & { 2 } \\ { 1 } & { 1 } & { 1 / 2 } & { 2 } \\ { 2 } & { 2 } & { 1 } & { 3 } \\ { 1 / 2 } & { 1 / 2 } & { 1 / 3 } & { 1 } \end{array} \right]
$$

利用MATLAB软件进行编程求解得到方案层的权重排序结果为

$$
\begin{array} { r l } & { W _ { A } = \left[ 0 . 2 6 2 8 , 0 . 1 4 0 9 , 0 . 4 5 5 4 , 0 . 1 4 0 9 \right] , } \\ & { W _ { B 1 } = \left[ 0 . 4 2 3 6 , 0 . 2 2 7 0 , 0 . 2 2 7 0 , 0 . 1 2 2 3 \right] , } \\ & { W _ { B 2 } = \left[ 0 . 1 4 2 8 , 0 . 0 8 7 4 , 0 . 3 8 4 9 , 0 . 3 8 4 9 \right] , } \\ & { W _ { B 3 } = \left[ 0 . 3 3 3 3 , 0 . 1 6 6 7 , 0 . 3 3 3 3 , 0 . 1 6 6 7 \right] , } \\ & { W _ { B 4 } = \left[ 0 . 2 2 7 , 0 . 2 2 7 , 0 . 4 2 3 6 , 0 . 1 2 2 3 \right] } \end{array}
$$

综上可得四个旅游地方案的权重值和排序情况如下：$W _ { C 1 } = 0 . 3 1 5 2 , W _ { C 2 } = 0 . 1 7 9 9 , W _ { C 3 } = 0 . 3 2 5 4 , W _ { C 4 } = 0 . 1 7 9 5$ 四个旅游地的优先级排序情况为昆明、杭州、北京、哈尔滨。

# 4.2基于理想点一矢量余弦投影的决策分析

公司通过问卷采集员工对旅游地相关信息的评价，根据乐观决策准则即少数服从多数的原则来确定每项属性的评分值，通过对评价结果进行整理得到该案例的原始决策矩阵如表1所示。

表1可供选择的旅游目的地信息表  

<html><body><table><tr><td></td><td>P1</td><td>P2</td><td>P3</td><td>P4</td></tr><tr><td>S</td><td>9</td><td>9</td><td>9</td><td>10</td></tr><tr><td>S</td><td>9</td><td>10</td><td>8</td><td>9</td></tr><tr><td>S</td><td>10</td><td>9</td><td>9</td><td>9</td></tr><tr><td>S4</td><td>8</td><td>8</td><td>8</td><td>9</td></tr></table></body></html>

注：矩阵中的数据为决策者对各个方案在对应属性上的评价值，评价值的取值区间为1-10，其中 $p _ { 1 }$ 、 ${ p } _ { 3 }$ 、 $p _ { 4 }$ 这三项属性属于正向指标，它们的得分越高越好， $p _ { 2 }$ 属于逆向指标，它的得分越低越好。

a）本文将决策者的偏好分为五个等级，分别为 ${ \cal H } _ { - 2 } , { \cal H } _ { - 1 }$ ，$H _ { 0 } , H _ { 1 } , H _ { 2 }$ ,依次对这五个等级赋值-1、-0.5、0、0.5、1。决策者对 $p _ { 1 }$ 、 ${ { p } _ { 2 } }$ 、 ${ p } _ { 3 }$ 、 $p _ { 4 }$ 这四项属性间的分布式偏好关系如表2所示。

表2多属性间的分布式偏好关系表  

<html><body><table><tr><td></td><td>P1</td><td>P2</td><td>P3</td><td>P4</td></tr><tr><td rowspan="2">P1</td><td rowspan="2">(H0,1)</td><td>(H_,0.4) (H,0.4)</td><td>(H,0.2) (H0) (H2)</td><td>(H,0.3) (H0.4) (H.2)</td></tr><tr><td>(H,0.2)</td><td>(Ω,0.1)</td><td>(Ω,0.1)</td></tr><tr><td>P</td><td></td><td>(H0,1)</td><td>(H,0.2) (H.5) (H,0.3)</td><td>(H,0.4) (H0.4) (Ω0.2)</td></tr><tr><td>P</td><td>-</td><td></td><td>(H0,1)</td><td>(H,0.4) (H,03) (Ω.)</td></tr><tr><td>P4</td><td>-</td><td>-</td><td>1</td><td>(H,1)</td></tr></table></body></html>

根据表2所示的多属性间的分布式偏好关系，利用式（3)

（4）求得的得分矩阵 $S _ { \mathrm { 1 } }$ 正规化的得分矩阵 $\bar { s }$ 如下所示：

$$
S _ { 1 } = \left[ \begin{array} { c c c c } { { 0 } } & { { \left[ 0 . 2 , 0 . 2 \right] } } & { { \left[ - 0 . 4 , - 0 . 2 5 \right] } } & { { \left[ 0 . 2 , 0 . 3 5 \right] } } \\ { { \left[ - 0 . 2 , - 0 . 2 \right] } } & { { 0 } } & { { \left[ - 0 . 3 , - 0 . 3 \right] } } & { { \left[ - 0 . 1 , 0 . 1 \right] } } \\ { { \left[ 0 . 2 5 , 0 . 4 \right] } } & { { \left[ 0 . 3 , 0 . 3 \right] } } & { { 0 } } & { { \left[ - 0 . 2 , 0 . 1 \right] } } \\ { { \left[ - 0 . 3 5 , - 0 . 2 \right] } } & { { \left[ - 0 . 1 , 0 . 1 \right] } } & { { \left[ - 0 . 1 , 0 . 2 \right] } } & { { 0 } } \end{array} \right]
$$

根据式（5）～（7）计算得决策者对 $p _ { 1 }$ 、 ${ { p } _ { 2 } }$ 、 ${ p } _ { 3 }$ 、 $p _ { 4 }$ 这四个属性的偏好度 $u _ { i }$ 分别为 $u _ { 1 } = 0 . 2 5 8$ ， $u _ { 2 } = 0 . 1 6 7$ ，$u _ { 3 } = 0 . 3 7 5 \ , u _ { 4 } = 0 . 2 ;$

b）将前一步所求的结果代入式（8）得到了多属性偏好方案的计算结果如下：

$$
\vec { S _ { 1 } } = ( 2 . 3 2 2 , 1 . 5 0 3 , 3 . 3 7 5 , 2 ) \quad , \qquad \vec { S _ { 2 } } = ( 2 . 3 2 2 , 1 . 6 7 , 3 , 1 . 8 )
$$

$$
\stackrel {  } { S _ { 3 } } = ( 2 . 5 8 , 1 . 5 0 3 , 3 . 3 7 5 , 1 . 8 ) , \stackrel {  } { S _ { 4 } } = ( 2 . 0 6 4 , 1 . 3 3 6 , 3 , 1 . 8 )
$$

c）并根据式（9）得到理想多属性偏好方案矢量为 $\stackrel {  } { S } = ( 2 . 5 8 , 1 . 3 3 6 , 3 . 3 7 5 , 2 ) :$ （20

d）利用式（10）计算一般多属性偏好方案矢量在理想多属性偏好方案矢量方向上的投影强度 $q _ { i }$ 分别为 $q _ { 1 } = 4 . 7 9$ ，（204号 $q _ { 2 } = 4 . 1 8 3 , q _ { 3 } = 4 . 8 8 2 , q _ { 4 } = 4 . 2 6 8$ ,通过归一化可得 $q _ { 1 } ^ { ' } = 0 . 2 6 4$ $\dot { q _ { 2 } } = 0 . 2 3 1 , \dot { q _ { 3 } } = 0 . 2 6 9 , \dot { q _ { 4 } } = 0 . 2 3 6 ;$ （20

e）对Step4 计算结果值按倒序的方式得到的最终排序结果为 $S _ { 3 } > S _ { 1 } > S _ { 4 } > S _ { 2 }$ ，四个旅游地的优先级排序情况为昆明、杭州、哈尔滨、北京。

通过将上述两种方法求得的结果进行对比可知所得排序结果比较接近，这说明了本文所提方法的有效性与可行性。

# 5 结束语

本文指出了现有的多属性决策方法存在的诸如属性权重计算过于主观、应用条件存在局限、过程相对复杂不易推广等缺点,从提高方法合理性的角度出发提出了一种基于矢量余弦投影的多属性偏好决策方法。该方法采用多等级成对比较方法来计算决策者对于各项属性的偏好度，将偏好度纳入到多属性问题的决策中来，克服传统方法只能实现单等级成对比较这一缺点，在一定程度上克服主观随意性，其次，采用理想点法来确定理想多属性偏好方案矢量，使得选取的评价标准更加科学合理，最后，采用矢量余弦法来计算构建的一般多属性偏好方案矢量在理想多属性偏好方案矢量方向上的投影强度，该方法操作简单，计算过程简洁，具有良好的可推广性，如用于工业产品的创新设计过程，这样能为企业带来一笔可观的经济收益。文章最后的算例分析结果表明了所提方法在处理多属性决策问题方面的有效性和可行性。

# 参考文献：

[1]徐泽水，达庆利．多属性决策的组合赋权方法研究[J]．中国管理科学, 2002 (2): 85-88.(Xu Zeshui,Da Qingli, Study on method of combination weighting[J]. Chinese Journal of Management Science,2002 (2): 85-88.)   
[2]陈伟，夏建华．综合主、客观权重信息的最优组合赋权方法[J].数学的 实践与认识,2007(1):17-22.(Chen Wei,Xia Jianhua,An optimal weights combination method considering both subjective and objective weight information [J].Mathematics in Practice and Theory, 2007(1): 17-22.)   
[3] 何大义，陈小玲，许加强．多属性群决策问题中基于最小叉熵的权重集 成方法[J].控制与决策,2017,32(02):378-384.(He Dayi,Chen Xiaoling, Xu Jiaqiang.Weight aggregation method based on principle of minimum cross-entropy in multiple attribute group decision-making [J]. Control and Decision,2017,32(2):378-384.)

[4]宋冬梅，刘春晓，沈晨，等．基于主客观赋权法的多目标多属性决策方

法[J].山东大学学报：工学版,2015,45(4):1-9.(Song Dongmei,Liu Chunxiao,Shen Chen,et al.Multiple objective and atribute decision making based on the subjective and objective weighting [J]. Journal of Shandong University: Engineering Science,2015,45 (4): 1-9.)   
[5]常志朋，程龙生，刘家树．基于马田系统与 TOPSIS 的区间数多属性决 策方法[J]．系统工程理论与实践,2014,34(1):168-175.(Chang Zhipeng, Cheng Longsheng,Liu Jiashu,Multiple attribute decision making method with intervals based on Mahalanobis-Taguchi system and TOPSIS method [J].Systems Engineering-Theory & Practice,2014,34(1):168-175.)   
[6] 潘显兵．区间数型多属性决策正交投影模型及其应用[J].数学的实践 与认识，2018,48 (2):134-141.(Pan Xianbing.A orthogonal projection model for muti-atribute decision making with intervals and its application [J].Mathematics in Practice and Theory,2018,48 (2): 134-141.)   
[7]赵海燕，马卫民，孙秉珍，等．考虑风险偏好的区间直觉模糊软集型多 属性决策方法[J].计算机应用研究,2018,35(2):453-458.(Zhao Haiyan, Ma Weimin,Sun Bingzhen,et al.Multi-tribute decision making method considering risk appetite based on interval-valued intuitionistic fuzzy soft set [J].Application Research of Computers,2018,35 (2): 453-458.)   
[8]于瑞华，成央金．直觉模糊多属性的意见集中排序法[J].运筹与管理, 2018,27(1):59-62.(Yu Ruihua,Cheng Yangjin,Attitudes concentrated order for multi-attribute decision making in intuitionistic fuzzy set [J]. Operations Research and Management Science,2018,27(1): 59-62.)   
[9]梅晓玲．基于相似度的动态直觉模糊多属性决策方法[J].统计与决策, 2016(15): 22-24.(Mei Xiaoling.Dynamic intuitionistic fuzzy multiple attribute decision-making method based on similarity [J]，Statistics & Decision,2016 (15): 22-24.)

[10] Xu Z,Yager R R.Dynamic intuitionistic fuzzy multi-attribute decision making [J].International Journal of Approximate Reasoning,2oo8,48(1): 246-262.

[11]冯向前，刘琦，魏翠萍．基于犹豫模糊二元语义的多属性决策方法[J]. 运筹与管理,2018,27(1):17-22.(Feng Xiangqian,Liu Qi,Wei Cuiping, Hesitant fuzzy 2-tuple linguistic multiple attribute decision making method [J].Operations Research and Management Science,2018,27(1): 17-22.)   
[12]张超，李德玉．犹豫模糊图及其在多属性决策中的应用[J].模式识别 与人工智能,2017,30(11):1012-1018.(Zhang Chao,Li Deyu,Hesitant fuzzy graph and its application to multi-attribute decision making [J]. Pattern Recognition and Artificial Intelligence,2017,30 (11): 1012-1018.)   
[13]刘琦，冯向前，张华荣．基于相似度的犹豫模糊语言多属性决策方法 [J].统计与决 策，2017(19):40-44.(Liu Qi,Feng Xiangqian,Zhang Huarong, Multiattribute decision-making method of hesitant fuzzy language based on similarity [J],Statistics& Decision,2017(19): 40-44.)   
[14] Xu Z, Zhang X. Hesitant fuzzy multi-atribute decision making based on TOPSIS with incomplete weight information [J]. Knowledge-Based Systems,2013,52 (6): 53-64.   
[15]付超，侯震．基于多等级方案成对比较的决策方法[J].控制与决策, 2015,30 (10): 1828-1834.(Fu Chao,Hou Zhen,Decision method based on pairwise comparison of alternatives on multiple grades [J],Mathematics in Practice and Theory,2015,30(10):1828-1834.)   
[16] Jing Ma,Wei Ma,Dong Xu,et al.A power restoration strategy for the distribution network based on the weighted ideal point method [J]. International Journal of Electrical Power and Energy Systems,2014,63.   
[17] Li Anda,He Zhen,Zhang Yang.Bi-objective variable selection for key quality characteristics selection based on a modified NSGA-II and the ideal point method [J]. Computers in Industry,2016,82.