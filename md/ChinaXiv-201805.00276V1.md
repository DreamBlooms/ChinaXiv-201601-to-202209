# 基于UML类图的模糊时空数据建模

陈旭，严 丽²，马宗民²，李卫军1

(1．东北大学 计算机科学与工程学院，沈阳 110819;2.南京航空航天大学 计算机科学与技术学院，南京 211106)

摘要：模糊性广泛存在于时空应用领域，现有的时空数据模型缺乏描述和表达模糊时空对象内在机制和语义关系的能力。通过研究模糊时空数据语义，给出了模糊时空数据模型的形式化定义，在此基础上对 UML 类图进行扩展，提出一种模糊时空UML数据模型，并用例子说明本文所提模糊时空数据模型的可用性。

关键词：模糊时空数据；UML类图模型；建模 中图分类号：TP doi:10.3969/j.issn.1001-3695.2017.08.0875

# Fuzzy spatiotemporal data modeling with UML class diagram

Chen Xu1, Yan Li2,Ma Zongmin2,Li Weijun1 (1.SchoolOfComputerScience&Engineing,Nrtheastern UnversityShenyangl10819,China,2.CollgeOfComputer Science& Technology,Nanjing University OfAeronautics & Astronautics,Nanjing 21ool6,China)

Abstract: Abstract:Fuzzness widelyexists in many spatio-temporal applications.The existing spatio-temporal datamodels lacktheabilitytodescribeandrepresentthe intermal mechanisms orsemanticrelationoffuzzyspatio-temporalobjects.After investigatingthesemanticsoffuzzyspatio-temporaldata,aformaldefinitionaboutfuzzyspatio-temporaldatamodelisproposed. Onthis basis,the UMLdatamodel is extended toexpress fuzzytemporalandspatialdata.Finally,the potentialusefulnessof our proposed method is demonstrated with an example.)

KeyWords:fuzzy spatio-temporal data; UML class diagram model; modeling

# 0 引言

人类生活在随时间动态变化的空间世界中，现实世界中几乎每个对象、事件或现象都与时间和空间相关联，由此产生了覆盖面巨大的时空应用领域。时空应用除了典型的城市交通、地籍与生态管理之外[1]，近年来还进一步延伸到生物、医学、水文与气象、刑侦、智能家居、网络通信与大数据[2等众多应用领域。计算机技术在时空应用领域的广泛应用，特别是全球定位系统（GPS）、全球移动通信系统（GSM)、蓝牙技术和射频识别（RFID）等技术的广泛使用，导致了大量时空数据的出现，如何有效地表示和处理时空数据变得越来越重要，已经成为当前国内外学者广泛关注的热点研究问题[3]。

时空数据模型是实现时空数据管理的基础，时空数据的有效处理需要建立在时空数据库模型的基础之上[4]。传统的时空数据库采用的数据库模型主要包括：关系数据库模型，面向对象数据库模型以及对象-关系数据库模型[5]。此外，由于时空实体具有复杂的结构和复杂的空间拓扑关系，为了充分建模时空数据的语义，研究者还提出了一些时空概念数据模型，例如时空实体-关系模型[和时空UML类图模型[7]。

需要指出的是，虽然已有多种时空数据模型被相继开发出来，但其所具有的时空数据表示与处理能力还不能充分满足实际应用的需求。现有的时空数据模型通常假设时空实体具有精确的边界及精确的状态描述，并且时空实体的位置及相互关系均可以准确地测度和定义，但是这些假设在实际应用中通常难以完全得到满足。由于误差和连续运动的离散化处理等方面的原因，时空实体的空间和时态信息以及它们之间的各种关系通常包含模糊性，模糊性被认为是时空应用领域一个固有的特征[8]。

为了表示和处理模糊时空数据，文献[9]重点讨论了模糊空间实体及模糊拓扑关系，提出了在模糊面向对象数据库中表示模糊空间数据的方法，并通过气象应用例子给出了几种简单的查询形式及执行过程。从对象建模的角度出发，文献[10]提出一种基于UML类图的模糊时空概念数据模型。与文献[9]类似，文献[10]重点关注的是模糊空间实体及模糊拓扑关系，没有充分考虑模糊时态信息，并且所提出的模糊时空UML数据模型不支持模糊时空实体之间复杂语义关系的建模。为了适应Web环境下模糊时空数据处理的需要，文献[11]提出一种模糊时空XML数据模型，用于同时表示模糊空间及模糊时态数据，并给出了基于该模型的几种简单节点操作和拓扑关系操作的定义。

UML（unified modelinglanguage，统一建模语言）[l2]是一种被广泛接受和使用的面向对象的建模语言，已在很多领域（包括时空应用领域）得到广泛的应用[7,13]。本文在充分分析模糊时空数据语义的基础上，通过对传统UML类图模型进行扩展，提出一种模糊时空UML数据模型，并用例子说明本文所提模糊时空数据模型的可用性。

实际上，为了表示和处理模糊数据，多种类型的模糊数据模型已经被开发出来，包括：模糊关系数据库模型[14]、模糊面向对象数据库模型[15]、模糊UML类图模型[16]和模糊XML 模型[14]。但现有各类模糊数据模型只能表示实体一般属性上的模糊值，不能表达时空属性上的模糊性。此外，已有的模糊时空数据模型没有充分考虑模糊时态信息，同时也不支持模糊时空实体之间复杂语义关系的建模。与已有模型相比，本文提出的模糊时空UML模型同时考虑了模糊时态和空间信息，详细给出了模糊时空实体、模糊时空类以及属性的表示形式，同时加强了模糊时空实体之间复杂语义关系的建模能力，包括模糊泛化关系、模糊聚合关系和模糊关联关系。

# 1 模糊时空数据表示

# 1.1时空实体

空间域中随时间发生变化的实体被称作时空实体。一个时空实体具有实体标志，并且包含了描述其特征的属性。时空实体的属性可分为：时态属性，空间属性和非时空的普通属性。依据时空实体标志是否改变，可以识别出两种类型的时空实体的时空变化：实体级时空变化和属性级时空变化。其中，实体级时空变化涉及时空实体的标志变化，如分裂、合并等；属性级时空变化不涉及时空实体的标志变化，但其时态属性、空间属性和普通属性可能会发生变化。空间属性的变化又分成基于位置、形状变化和位置/形状都发生变化3种形式。本文探讨时空实体的属性级时空变化。

# 1.2模糊时空实体及属性

时空实体包含时态属性、空间属性以及普通属性。在现实应用中，这些属性由于数据获取或者处理方式等方面的原因，可能包含模糊性，包含模糊属性的时空实体被称作模糊时空实体。例如，“高速移动热带气旋"是一个模糊时空实体，因为它包含了模糊属性“高速移动”。根据时空实体包含的属性类别，模糊时空实体可能包括：模糊空间属性、模糊时态属性和模糊普通属性。

# 1.2.1模糊空间属性

模糊空间属性主要涉及模糊空间数据和模糊空间关系两部分内容[17]，其中模糊空间数据又分为模糊点、模糊线和模糊域。

a)模糊点。模糊点是指在三维空间中坐标存在模糊性的点，即位置不确定的点。形式上，一个模糊点表示为 $\tilde { A } _ { \mathrm { s p } } ( x , y , z , \delta )$ 其中 $x , y , z$ 分别是模糊点在三维空间中的坐标， $\delta$ 表示该点位于坐标 $( x , y , z )$ 的可能性 $( 0 \leq \delta \leq 1 )$ )。例如，模糊点 $\tilde { A } _ { \mathrm { s p } } ( 4 , 6 , 3 , 0 . 4 )$ （204号表示一个点位于坐标 $( 4 , 6 , 3 )$ 的可能性为0.4。

b)模糊线。模糊线表示两个可能端点间一组点的集合。模糊线形式上表示为 $\tilde { A _ { \mathrm { s l } } } ( x _ { 1 } , y _ { 1 } , z _ { 1 } , \delta _ { 1 } , x _ { 2 } , y _ { 2 } , z _ { 2 } , \delta _ { 2 } )$ ，其中 $( x _ { 1 } , y _ { 1 } , z _ { 1 } )$ （204号和 $( x _ { 2 } , y _ { 2 } , z _ { 2 } )$ 分别是两个端点在三维空间中的坐标， $\delta _ { 1 }$ 和 $\delta _ { 2 }$ 表示两个端点位于坐标 $( x _ { 1 } , y _ { 1 } , z _ { 1 } )$ 和 $( x _ { 2 } , y _ { 2 } , z _ { 2 } )$ 的隶属度 $( 0 \leq \delta _ { 1 } \leq 1$ ，0$\le \delta \ o _ { 2 } \le 1 \dot { \bf \Phi } .$ ）

c）模糊域。模糊域是指边界存在模糊性的区域，本文用MBR(Minimum Bounding Rectangle)[18]表示边界不确定的区域。模糊域形式上表示为 $\tilde { A } _ { \mathrm { s r } } ( x _ { \mathrm { m i n } } , y _ { \mathrm { m i n } } , \delta _ { \mathrm { m i n } } , x _ { \mathrm { m a x } } , y _ { \mathrm { m a x } } , \delta _ { \mathrm { m a x } } )$ ，其中 $\scriptstyle \left( x _ { \mathrm { m i n } } , \right.$ $y _ { \mathrm { m i n } } )$ 和 $( x _ { \mathrm { m a x } } , y _ { \mathrm { m a x } } )$ 分别表示模糊域映射到 $x$ 轴和 $y$ 轴上的最小和最大坐标， $\delta _ { \mathrm { m i n } }$ 和 $\delta _ { \mathrm { m a x } }$ 表示点位于坐标 $( x _ { \mathrm { m i n } } , y _ { \mathrm { m i n } } )$ 和 $( x _ { \mathrm { m a x } } , y _ { \mathrm { m a x } } )$ 的隶属度（ $0 \leq \delta _ { \operatorname* { m i n } } \leq 1$ ， $0 \leq \delta _ { \mathrm { m a x } } \leq 1 _ { . }$ ）

![](images/53ba94553cc410e0a70605e44013c8408e3fcf415d94b0825e3c2cf1f9237da6.jpg)  
图1给出了上述3种模糊空间数据的图形化说明。  
图1模糊空间数据  
图2模糊空间关系

空间数据的模糊性直接导致了空间关系的模糊性。设 $O _ { 1 }$ 和$O _ { 2 }$ 是两个模糊时空实体， $O _ { 1 }$ 和 $O _ { 2 }$ 间的模糊空间拓扑关系表示为 $\tilde { A } _ { \mathrm { s \_ t o p o l o g y } } ( O _ { 1 } , O _ { 2 } , \psi )$ ，其中y∈(f-disjoint,f-meet, $f$ overlap, $f -$ equal, $f -$ contain)，即 $\psi$ 可以取模糊分离、模糊相接、模糊重叠、模糊相等和模糊包含。

图2给出了5种模糊空间关系语义的图形化说明，其中黑色和灰色的椭圆分别代表两个模糊时空实体。

：0 8 O   
Fuzzy Disjoint FuzzyMeet Fuzzy Overlap （(a) (b) (c） 。 Fuzzy Equal Fuzzy Contain (d) (e)

# 1.2.2模糊时态属性

模糊时态属性包括模糊时态数据和模糊时态关系，其中模糊时态数据又分为模糊时间点（例如：“三点十分左右"）和模糊时间区间（例如：清晨）两种形式[6,19-21]。

a）模糊时间点。模糊时间点是时空实体发生的时间（更准确地说是时刻）具有模糊性。 $\tilde { A } _ { \mathrm { t p } } ( t , \delta )$ 表示一个模糊时间点，其中 $t$ 表示时间点， $\delta$ 表示时间点为 $t$ 的可能性 $( 0 \leq \delta \leq 1 )$ ）

b）模糊时间区间。模糊时间区间由两个分别表示起止时间的时间点组成，其中至少有一个时间点为模糊时间点。形式上，$\tilde { A } _ { \mathrm { t i } } ( t _ { \mathrm { s } } , \delta _ { \mathrm { s } } , t _ { \mathrm { e } } , \delta _ { \mathrm { e } } )$ 用于表示一个模糊时间区间，其中 $t _ { \mathrm { s } }$ 和 $t _ { \mathrm { e } }$ 分别表示模糊时间区间的开始时间和结束时间，而 $\delta _ { \mathrm { s } }$ 和 $\delta _ { \mathrm { e } }$ 分别表示开始时间为 $t _ { \mathrm { s } }$ 、结束时间为 $t _ { \mathrm { e } }$ 的模糊度 $( 0 \leq \delta _ { \mathrm { s } } \leq 1 , 0 \leq \delta _ { \mathrm { e } } \leq 1 )$ 。

时间区间上的模糊性导致了时态拓扑关系的模糊性。设 $t _ { 1 }$ 和 $t _ { 2 }$ 是两个模糊时间区间，两者之间的模糊时态拓扑关系表示为 $\tilde { A } _ { \mathrm { t \_ t o p o l o g y } } ( t _ { 1 } , ~ t _ { 2 } , ~ \tau )$ ，其中 $\tau \in$ (f-before, $f$ after, $f$ equal, $f$ meet, $f ^ { \natural }$ overlap)，即τ可以取模糊先于、模糊之后、模糊相等、模糊相接和模糊重叠。

![](images/3e326fcc5b3a2cb206068977fdf996495116f212d87ef38d7673ae6912817a5b.jpg)  
图3给出了5种模糊时态关系语义的图形化说明。  
图3模糊时间拓扑关系

# 1.2.3模糊普通属性

普通属性是时空实体中除空间属性和时态属性之外的其他非时空属性，如时空实体的移动速度等。以模糊时空类高速移动的热带气旋为例，其“速度”就为模糊特征属性。时空实体中可取模糊值的普通属性被称作模糊普通属性。形式上，一个模糊普通属性用 $\tilde { A _ { \mathrm { c } } }$ 来表示。

# 1.3模糊时空实体语义关系

现实世界中的时空实体并非孤立存在，时空实体之间除了时态拓扑和空间拓扑关系之外，通常还存在复杂的语义关联，如泛化关系、聚合关系和关联关系。对于模糊时空实体而言，由于时空实体的模糊性，导致了模糊时空实体之间可能存在着模糊泛化关系、模糊聚合关系和模糊关联关系。

# 1）模糊时空泛化关系

时空泛化关系用于表示时空实体之间存在的分类关系，即超类/子类关系。例如：热带气旋是超强台风、强台风和台风的泛化。

如果参与时空泛化关系的时空实体是模糊时空实体，则时空泛化关系为模糊时空泛化关系，表示的是模糊超类/子类关系，例如：“高速移动热带气旋”与“超强台风”之间的关系。

# 2）模糊时空聚合关系

时空聚合关系用于表示时空实体之间存在的整体与部分关系，其中代表组成部分的时空实体可不依赖代表整体部分的时空实体独立存在。例如：热带气旋由风眼、眼壁和螺旋雨带聚合而成，热带气旋与风眼、眼壁和螺旋雨带之间就是整体与部分的关系。

与模糊时空泛化关系类似，如果参与时空聚合关系的时空实体是模糊时空实体，则时空聚合关系为模糊时空聚合关系，表示的是模糊整体与部分关系。例如：“超强台风”由风眼、眼壁和螺旋雨带构成。

# 3）模糊时空关联关系

关联关系用于关联两个时空实体，表示一个时空实体的实

例与另一个时空实体的实例相关联。例如：副热带高压与热带气旋的关联关系。

当模糊时空实体相关联的时候，就会构成模糊时空关联关系，用于表示模糊时空类之间存在的不确定联系。

# 1.4模糊时空数据模型

模糊时空实体的表示和处理需要模糊时空数据模型的支持。为了表示上面讨论的模糊时空实体上存在的多种形式的模糊数据(时空的和普通的)，下面给出一个抽象的模糊时空数据模型。

定义1一个抽象的模糊时空数据模型可以表示为一个三元组 $\widetilde { M } \ = ( \tilde { A } , \ \tilde { C } , \ \tilde { R } )$ ，其中：

a $\tilde { A } { = } ( \tilde { A } _ { \mathrm { s p } } , \tilde { A } _ { \mathrm { s l } } , \tilde { A } _ { \mathrm { s r } } , \tilde { A } _ { \mathrm { s } _ { - } \mathrm { t o p o l o g y } } , \tilde { A } _ { \mathrm { t p } } , \tilde { A } _ { \mathrm { t i } } , \tilde { A } _ { \mathrm { t - } \mathrm { t o p o l o g y } } , \tilde { A } _ { \mathrm { c } } )$ 是一个模糊属性集合，其中： $\tilde { A } _ { \mathrm { s p } } { = } ( x , y , z , \delta )$ 表示模糊点， $\tilde { A } _ { \mathrm { s l } } { = } ( x _ { 1 } , y _ { 1 } , z _ { 1 } , \delta _ { 1 } , x _ { 2 }$ $y _ { 2 } , z _ { 2 } , \delta _ { 2 } )$ 表示模糊线， $\tilde { A } _ { \mathrm { s r } } = ( x _ { \operatorname* { m i n } } , y _ { \operatorname* { m i n } } , \delta _ { \operatorname* { m i n } } , x _ { \operatorname* { m a x } } , y _ { \operatorname* { m a x } } , \delta _ { \operatorname* { m a x } } )$ 表示模糊域， $\tilde { A } _ { \mathrm { s \_ t o p o l o g y } } { = } ( O _ { 1 } , O _ { 2 } , \psi )$ 表示模糊空间拓扑关系 $\scriptstyle ( y \in ( f )$ disjoint,$f$ meet,f-overlap,f-equal, $f$ contain); $\tilde { A } _ { \mathrm { t p } } { = } ( t , \delta )$ 表示一个模糊时间点， $\tilde { A } _ { \mathrm { t i } } { = } ( t _ { \mathrm { s } } , \delta _ { \mathrm { s } } , t _ { \mathrm { e } } , \delta _ { \mathrm { e } } )$ 表示一个模糊时间区间， $\tilde { A } _ { \mathrm { t \_ t o p l o g y } } { = } ( t _ { 1 } , t _ { 2 } , \tau )$ 表示模糊时态拓扑关系( $\tau { \in } ( f \mathrm { . }$ before, $f .$ after, $f$ equal, $f$ meet, $f -$ overlap)); $\tilde { A _ { \mathrm { c } } }$ 表示模糊普通属性。

$\mathfrak { b } ) \tilde { C } \ = ( \tilde { C } _ { 1 } , \ \tilde { C } _ { 2 } , . . . , \tilde { C } _ { \mathrm { k } } )$ 是一个模糊时空实体集合。此外， $\tilde { O } ( \tilde { C } _ { \mathrm { i } } )$ 表示类 $\tilde { C } _ { \mathrm { i } }$ 包含的模糊时空实体实例集合， $\tilde { A } ( \tilde { C } \mathrm { i } )$ 表示构成类 $\tilde { C } _ { \mathrm { i } }$ 的模糊属性集合（包括时空的和普通属性）。

$\mathrm { c } ) \tilde { R } { = } ( \tilde { R } \mathrm { A } , \ \tilde { R } \mathrm { c } , \ \tilde { R } \mathrm { p } )$ 是一个模糊时空语义关系集合，其中RA表示模糊时空关联关系集合， $\tilde { R } _ { } \mathrm { c }$ 表示模糊时空泛化关系集合，${ \tilde { R } } _ { \mathrm { P } }$ 表示模糊时空聚合关系集合。

# 2 模糊时空UML类图模型

对于上述模糊时空抽象数据模型，通过扩展UML类图模型实现模糊时空实体的数据建模。其中，（模糊）时空实体由UML类图中的类来表示，（模糊）时空实体的空间属性、时态属性和普通属性用UML类中的属性来表示，（模糊）时空实体之间的语义关系由UML类之间的语义关系来表示。

# 2.1模糊时空类的表示

在UML类图模型中，模糊时空实体被建模成模糊时空类，模糊时空实体包含的属性（包括：模糊空间属性、模糊时态属性和模糊普通属性）则称为模糊时空类的属性。

模糊时空类的模糊性体现在两个方面：

a)模糊时空类包含模糊属性（空间属性、时间属性和/或特征属性)，类的实例一一时空对象在模糊属性上的值可以是模糊值；

b)时空对象（精确或模糊）于模糊时空类之间存在不确定的隶属关系。

遵循与文献[22]类似的方法，本文使用虚线矩形框表示模糊时空类，并且在模糊时空类中增加一个属性域为[0,1]的特殊属性 $\mu$ 来标志上面第二个方面的模糊性。对于上述第一个方面的模糊性，文献[22]中提出的在模糊属性前加关键字“Fuzzy的方法不能被直接使用，因为模糊时空类中的模糊属性可能是模糊空间属性或模糊时态属性，应该分别处理。根据空间属性的不同形式，下面给出模糊时空属性在模糊时空类中的表示方法。

# 1）模糊空间属性表示

由1.2节可知，模糊空间属性主要包括表示模糊点、模糊线和模糊区域三种形式，除此之外还有一种形式，即：模糊空间属性表示模糊点、模糊线或模糊区域当前未知。为了显式表示这四种类型的模糊空间属性，本文在模糊时空类中通过使用虚线矩形框加特定字母的形式进行标志，如图4(a)所示。其中：字母“s”表示模糊时空属性中未知的空间属性；字母“P”表示模糊空间属性为模糊点的空间属性；字母“L”表示模糊空间属性为模糊线的空间属性；字母“R”表示模糊空间属性为模糊域的空间属性。这些标志在使用上是将它们置于相应空间属性的后面，从而可在模糊时空类中表示不同类别的模糊空间属性。

图4(b)给出了一个模糊地籍时空类Cadastral，其中表示河流形状的river模糊空间属性用模糊线“L”标志，表示耕地形状的cultivatedland 模糊空间属性既可用模糊点“P”也可以用模糊域“R”标志，而unusedland由于不清楚未使用地块的形状，用未知的“s”进行标志。

_”_ P R 一 1 (a) Cadastral   
I-river 望   
-cultivated land [PCR]   
!-unused land LS 厂 (b)

# 2）模糊时态属性表示

模糊时态属性主要包括表示模糊时间点和模糊时间区间两种形式，除此之外还有一种形式，即：模糊时态属性表示模糊时间点或模糊时间区间当前未知。为了显式表示这三种类型的模糊时态属性，本文在模糊时空类中通过使用虚线圆加特定字母的形式进行标志，如图5(a)所示。其中：字母“t”表示模糊时空属性中未知的时间属性；字母“P”表示模糊时空属性为模糊时间点的时间属性；字母“I”表示模糊时空属性为模糊时间区间的时间属性。这些标志在使用上是将它们置于相应时态属性的后面，从而可在模糊时空类中表示不同类别的模糊时态属性。

图5(b)给出了一个模糊时空类Typhoon，其中表示热带气旋开始时间的starttime模糊时间属性用模糊时间点“P"标志，表示热带气旋运行时间的runningtime 模糊时间属性用模糊时间区间“I”标志，而failure time由于不清楚具体的消亡时间是某一个时间点还是某一段时间区间，所以用不明确的模糊时间“t”进行标志。

![](images/164212ab78978ff3534d8de7f05986082a9739e3d3a9464efc1f60ae8ceb5a0e.jpg)  
图4模糊空间属性表示  
图5模糊时间属性表示  
图6模糊时空类的表示

3）模糊普通属性表示

模糊普通属性是模糊时空属性中除时间和空间属性之外的其他一般属性。模糊时空类中的模糊普通属性可以采用文献[22]中给出的方法，即在模糊特征属性前加入关键字“Fuzzy”进行标志。

图6给出了一个描述副热带高压的模糊时空类SubtropicalHigh，其中用于表示副热带高压西伸脊点指数的普通属性Westextendingpoint可以取模糊值，在其前面加入关键字“Fuzzy”。此外，模糊时空类 SubtropicalHigh 中包含一个附加的特殊属性 $\mu$ ，可用以表示时空对象属于模糊时空类的隶属度。

Subtropical High 1   
-Area   
-Location variation ofthe ridge line 1   
-FuzzyWest-extendingpoint 1 一

# 2.2模糊时空类语义关系的表示

模糊时空实体之间的语义关系可用UML类图中模糊时空类之间的语义关系进行表示。下面就模糊时空关联、模糊时空泛化以及模糊时空聚合关系，给出它们在UML类图中的表示形式。

# 1)模糊时空类泛化关系的表示

两个时空类之间的泛化关系表示一个时空类是对另一个时空类具有更一般化描述的时空类，其中前者被称作时空超类，后者被称作时空子类。如果时空子类或时空超类为模糊时空类，则它们之间的关系是模糊时空泛化关系。在UML类图中，本文使用虚线三角形表示一个模糊时空泛化关系

图7给出一个模糊时空泛化关系，其中Super typhoon 是一个带有模糊时态属性和模糊普通属性的模糊时空类，Severetyphoon是一个包含模糊性的精确时空类，The typhoon是一个带有模糊空间属性和模糊普通属性的模糊时空类，这三个时空类与时空类TropicalCyclone之间存在模糊泛化关系。

![](images/194b8bcd927ad709d902047df760cd00ad050b989f07a6bfbc2d084a5bf360de.jpg)  
图7模糊时空泛化关系

# 2）模糊时空类聚合关系的表示

时空聚合关系表示一个时空类由一组时空类组成，其中前者称作聚合体，后者称作组成体。当代表组成体的时空类中存在模糊时空类时，相应的时空聚合关系为模糊时空聚合关系。在UML类图中，本文使用虚线菱形表示一个模糊时空聚合关系。

图8给出了一个模糊时空集合关系，其中时空类热带气旋TropicalCyclone与模糊时空类风眼TCeye、时空类眼壁TCeyewall和模糊时空类螺旋雨带 Spiral rainband之间的整体与部分关系为一个模糊时空聚合关系。

![](images/1f6728f3f917ca4186be11d091e55e1e7f77d443409c6ae7a76f9fda9813aa65.jpg)  
图8模糊时空聚合关系  
图9模糊时空关联关系

# 3）模糊时空类关联关系的表示

时空类之间存在着时空关联关系。当时空关联所连接的时空类中存在模糊时空类时，相应的时空关联关系为模糊时空关联。在UML类图中，本文使用虚线表示一个模糊时空关联关系

图9给出一个模糊时空关联关系，其中模糊时空SubtropicalHigh 和模糊时空类TropicalCyclone之间存在着模糊关联关系influence，即副热带高压可能在影响着热带气旋，并且该关联关系是一个1对 $n$ 的关联关系，表明一个副热带高压有可能影响多个热带气旋。

Subtropical High   
i-Area 1 Tropical Cyclone   
-locationvariationoftheridgeline >!-Serial number   
l-Intensityforgrade5With.3degree influence i-Fuzzy speed   
j-Fuzzy west-extendingpoint 1-Morning_ 国 1I

通过上面的介绍不难看出：模糊时空UML类图模型与经典UML类图模型具有相同的抽象结构，前者使用的建模构造子是对后者使用的建模构造子表达能力的扩展；一个模糊时空UML类图模型在没有不确定信息及时空信息出现时，完全可以转变成一个经典UML类图模型。

为了表示基于UML的模糊时空数据模型的可用性，下一节用一个气象现象的实例进行说明。

# 3 模糊时空UML类图模型的使用

本章给出一个例子，用以说明模糊时空UML类图模型在建模时空应用中的使用。在气象学中，副热带高压会对热带气旋产生影响，而热带气旋主要包括超强台风、强台风和台风三种形式，并且超强台风又由风眼、眼壁和螺旋雨带三个部分组成。上述这些气象现象随时间推移会发生状态(包括空间状态)的变化，因而属于时空实体。此外，这些时空实体在其内部时空属性或普通属性上可能包含模糊性，在其外部时空实体之间可能存在模糊关系。

根据本文之前提出的模糊时空类、模糊时空属性和模糊时空关系，建立了图10所示的模糊时空UML数据模型。该模型包含了8个时空类，其中：时空类 SubtropicalHigh中的属性Area、时空类Thetyphoon中的属性Location、时空类TC eye中的属性Location均为表示模糊时空数据的模糊空间属性；时空类Supertyphoon中的属性Morning、时空类TCeye中的属性Time、时空类Spiralrainband中的属性Time均为表示模糊时空数据的模糊时间属性。此外，时空类 SubtropicalHigh 中的属性 west-extendingpoint、时空类 Super typhoon 中的属性speed，时空类Thetyphoon中的属性speed以及时空类Spiralrain band中的属性RMW为模糊普通属性。

上述8个时空类之间语义关联关系如图10所示。其中：SubtropicalHigh与TropicalCyclone 之间存在模糊时空关联关系influence；Tropical Cyclone 与 Super typhoon、Severe typhoon和 The typhoon之间存在一个模糊泛化关系；Super typhoon 与TC eye、TC eyewall 和 Spiral rain band 之间存在一个模糊聚合关系。

图10所示的模糊时空UML数据模型能较好地反映出，在副热带高压时空类SubtropicalHigh的影响下，热带气旋时空类TropicalCyclone 的模糊时空数据的构成情况[23]。

![](images/b46913fbec19a68e922f73ec57b2cd6d08fd8918c0eca249da52d0a6e07fa85d.jpg)  
图10模糊UML时空数据模型

# 4 结束语

本文以时空数据为中心，讨论了模糊时空数据的语义，主要包括模糊时空实体、模糊时空属性和模糊时空语义关系。在此基础上，通过对UML类图模型进行扩展，提出了基于UML类图的模糊时空数据模型。该时空数据模型考虑了信息的模糊性，同时加强了对模糊时空语义关系的描述，从而为模糊时空数据的操作和处理奠定了模型支撑基础。

时空数据具有较高的复杂性，使用UML类图可以清晰地表达出时空对象之间的关系。本文提出的模糊时空UML类图模型，能够从概念抽象级别上直观描述时空实体的模糊时空状态以及时空实体间复杂的语义关系。应当说，模糊时空UML类图模型的优势不在模糊时空运算方面。因此，未来研究工作将集中在如何把模糊时空UML数据模型映射成模糊时空数据库，进而进行相应的模糊时空计算与存储(例如查询处理)，更好地满足时空应用领域进行智能时空分析的应用需求。此外，未来研究工作将通过更多的应用实例和实验手段，对所提模糊时空UML数据模型的合理性和有效性进行对比分析。

# 参考文献：

[1]Tan C,Yan S.Spatiotemporal data organization and application research [C]/ Proc of International Archives of the Photogrammetry,Remote Sensing & Spatial Information Sciences.2017.   
[2]Chen B Y,et al.,Spatiotemporal data model for network time geographic analysis in the era of big data [J].International Journal of Geographical Information Science,2016.30(6):1041-1071.   
[3]Körner C,May M,Wrobel S.Spatiotemporal modeling and analysis: introduction and overview[J].Kinstliche Intelligenz,2012,26(3): 215-221.   
[4]Wang X, Zhou X,Lu S. Spatiotemporal data modelling and management: a survey [C]//Proc of the 36th International Conference on Technology of Object-Oriented Languages and Systems.2000.   
[5]Pelekis N,et al.Literature review of spatio-temporal database models [J]. Knowledge Engineering Review,2004,19 (3): 235-274.   
[6] Tryfona N,Jensen C，Conceptual data modeling for spatiotemporal applications [J]. GeoInformatica,1999,3 (3): 245-268.   
[7]Price R, Srinivasan B, Ramamohanarao K. Extending the unified modeling language to support spatiotemporal applications $[ \mathrm { C } ] / \AA$ Proc of the 32nd International Conference on Technology of Object-Oriented Languages. 1999.   
[8]Ribaric S，Hrkac T.A model of fuzzy spatio-temporal knowledge representation and reasoning based on high-level Petri nets [J]. Information Systems,2012,37(3): 238-256.   
[9]Sozer A,et al. Modeling and querying fuzzy spatiotemporal databases [J]. Information Sciences,2008,178 (19): 3665-3682.   
[10] Yazici A,Zhu Q W,Sun N. Semantic data modeling of spatiotemporal database applications [J]. International Journal of Intelligent Systems,2001. 16 (7): 881-904.   
[11] Bai L,Yan L,Ma Z M. Determining topological relationship of fuzzy spatiotemporal data integrated with XML twig pattern [J].Applied Intelligence,2012,39 (1): 75-100.   
[12] Rumbaugh J,Jacobson I, Booch G. Unified modeling language reference manual [M].2nd ed. Beijing: Pearson Higher Education, 2004.   
[13] Price R,Christian N T. Extended spatiotemporal UML motivations, requirements,and constructs.2000.   
[14] Ma Z,Yan L.Modeling fuzzy data with XML:a survey. Fuzzy Sets and Systems, 2015.   
[15] Yan L,Ma Z,Zhang F.Algebraic operations in fuzzy object-oriented databases [J]. Information Systems Frontiers,2014,16 (4): 543-556.   
[16] Chen X,et al.Reengineering fuzzy spatiotemporal UML data model into fuzzy spatiotemporal XML model. IEEE Access,2017.   
[17] Salamat N, Zahzah E H. Fuzzy spatio-temporal relations analysis [C]// Proc of the 7th International Conference on Information Technology: New Generations.2010:301-306.   
[18] Papadias D,et al. Topological relations in the world of minimum bounding rectangles:a study with R-trees [J].ACM SIGMODRecord,1995,24 (2): 92-103.   
[19] Ben-Zvi J. The time relational model [M].1982.   
[20] Snodgrass R,Ahn I.A taxonomy of time databases [M].1985.   
[21] Pfoser D，Jensen C S.Capturing the uncertainty of moving-object representations [C]//Advances in Spatial Databases.1999:111-131.   
[22]Ma Z,Yan L.Fuzzy XML data modeling with the UML and relational data models [J].Data& Knowledge Engineering,2007,63(3): 972-996.   
[23]http://agora. ex. nii.ac.jp/digital-typhoon/year/wnp/20oo. html.en [EB/OL].