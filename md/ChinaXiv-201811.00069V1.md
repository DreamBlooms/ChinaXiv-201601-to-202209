# “一带一路”地区滑坡灾害风险评估

裴艳茜1,²，邱海军1,2,3，胡胜¹²，杨冬冬1,2，曹明明'，邹强4(1西北大学城市与环境学院,陕西西安710127;2西北大学地表系统与灾害研究院,陕西西安710127;3陕西省地表系统与环境承载力重点实验室,陕西西安710127；4中国科学院山地灾害与地表过程重点实验室/中国科学院成都山地灾害与环境研究所,四川 成都 610041)

摘要：“一带一路”倡议是中国参与全球治理的重要切入点，对“一带一路"地区滑坡灾害风险评估与区划，可为沿线国家和地区的防灾减灾提供依据。首先选取坡度和地形起伏度两个指标，提取研究区滑坡灾害安全区域。其次，采用模糊层次分析法(FAHP)确定滑坡灾害风险评估体系并计算各因子综合权重,基于滑坡灾害风险评估模型定量评估“一带一路”地区滑坡灾害危险性、损失和风险。最后，运用滑坡灾害点和近百年“一带一路”地区滑坡灾害致死人数和经济损失空间分布分别验证评估的滑坡灾害危险性和损失。结果表明：(1)滑坡灾害安全区域主要分布在平原、盆地和沙漠等地区，仅有 $4 . 7 \%$ (56个)的滑坡灾害点分布在安全区域内，提取结果较为合理。（2）“一带一路”地区容易诱发滑坡灾害的条件为：坡度 $2 5 \ \sim 4 5$ ，地形起伏度大于 $9 0 0 \mathrm { ~ m ~ }$ ，距河网的距离小于 $5 0 0 \mathrm { ~ m ~ }$ ，多年平均降雨量介于 $4 0 0 \sim 8 0 0 ~ \mathrm { m m }$ ,地震密度 $3 \times 1 0 ^ { - 4 } \sim 2 \times 1 0 ^ { - 3 }$ 个： $\mathrm { k m } ^ { - 2 }$ ,工程地质岩组为中等硬质岩体、软质岩和土质岩体。非安全区域中，滑坡灾害以中、低危险性为主，危险性评估结果精度 $A U C$ 值为0.823。（3)“一带一路”地区容易造成潜在损失的滑坡灾害承灾体条件为：人口密度为 $8 0 \sim 1 6 0$ 人· $\mathrm { k m } ^ { - 2 }$ ，公路线密度为 $2 \times 1 0 ^ { - 1 } \sim 9 \times 1 0 ^ { - 1 } \ \mathrm { k m } \cdot \mathrm { k m } ^ { - 2 }$ ，夜间灯光指数为 $2 0 \sim$ 60。非安全区域中，滑坡灾害潜在损失普遍较低，损失区划结果与近百年滑坡灾害致死人数和经济损失空间分布具有很好的一致性。（4)“一带一路”非安全区域,滑坡灾害极低、低、中等、高和极高风险区面积所占比例分别为 $4 4 . 7 \% . 2 5 . 5 \% . 1 5 . 3 \% . 1 0 . 3 \% . 4 . 2 \%$ ，以极低和低风险为主。

关键词：滑坡；安全区域；FAHP；风险评估；“一带一路"

中图分类号：X43 文献标识码：A 文章编号

“一带一路”指"丝绸之路经济带”和"21 世纪海上丝绸之路”，是中国为推动经济全球化深人发展而提出的国际区域经济合作新模式[1]。但是“一带一路"沿线国家与地区自然环境差异大，滑坡灾害点多、面广，危害严重，加之沿线国家和地区多为发展中国家，经济欠发达，抗灾能力弱，频繁发生的滑坡灾害严重威胁着当地人民的生命财产安全，制约着当地社会经济发展。因此，如何科学地减轻滑坡灾害风险和防灾减灾是该地区所面临的重大现实问题。

从已有的研究来看国内外学者多采用数学方法,层次分析法[2-3]、泊松概率模型[4-5]、信息量模型[6]等对小区域滑坡灾害危险性、易损性和风险进行评估。对大区域、小比例尺范围滑坡灾害风险评估极少，主要是因为数据获取困难，数据处理耗时长、难度大，精度不好控制。此外研究者在用数学方法对多因子叠加分析时，往往只对各影响因子做简单的相加或相乘[7-8],却忽略了滑坡灾害的发生需要特定的地形条件。因此，在滑坡灾害风险评估之前，科学合理地划定研究区滑坡灾害的安全区域尤为重要，可以减少评估工作的盲目性，提高评估对象的准确度。

基于此，本文利用GIS技术提取和验证“一带一路”地区滑坡灾害的安全区域，采用模糊层次分析法构建“一带一路”地区滑坡灾害风险评估体系，并对各风险评估因子的权重进行赋值，结合滑坡灾害风险评估模型生成“一带一路”地区滑坡灾害风险等级区划图。最后利用ROC曲线对危险性评估结果作验证。其结果不仅可以为沿线国家加强滑坡灾害防治和管理提供依据，还可进一步加快中国与“一带一路”地区沿线国家防灾减灾的合作步伐[9]

# 1 研究区概况

“一带一路”倡议是一个开放、包容的国际区域经济合作网络，其空间范围正在不断扩展，涉及全球一半以上的人口,经济总量高达 $2 1 \times 1 0 ^ { 1 2 }$ USD,占全球经济的 $1 / 3 ^ { [ 1 , 1 0 ] }$ ；“一带一路"空间范围辐射亚洲、欧洲、非洲、大洋洲及全球其他区域(图1）。一条海上丝绸之路和六大经济廊道成为连接“一带一路”地区和沿线各国家之间的经济纽带，其中六大经济廊道包括中国一中亚一西亚经济走廊、中国一中南半岛经济走廊、中巴经济走廊、中蒙俄经济走廊、孟中印缅经济走廊和新亚欧大陆区等，陆上丝绸之路经过主要地形区依次为黄土高原、河西走廊、准噶尔盆地、图兰低地、伊朗高原、亚美尼亚高原、东欧平原、波德平原等。此外，“一带一路”地区是全球板块运动和地壳活动最为强烈的区域，地中海一喜马拉雅山火山地震带和环太平洋沿岸火山地震带均分布于此，因而导致该区域滑坡灾害频发，且沿线国家多为发展中国家，抵御滑坡灾害风险的能力极为脆弱,滑坡灾害往往造成重大人员伤亡和经济损失[11-13]。据统计,1900—-2015 年“一带一路”地区滑坡灾害共发生338次，造成 $2 . 2 4 \times 1 0 ^ { 4 }$ 人遇难,经济总损失高达24×10USD[14] O

# 2 数据来源与方法

# 2.1 数据来源

本文采用的数据主要包括工程地质岩组、数字高程模型（DEM）、河网、多年平均降雨量、 $> 5$ 级地震震中、人口密度、公路网、夜间灯光指数、滑坡灾害点、人口死亡、经济损失等（表1）。DEM取自美国地质调查局 $1 \ \mathrm { k m } \times 1 \ \mathrm { k m }$ 数据,由此生成坡度和地形起伏度数据;河网数据取自联合国环境规划署，预处理过程中对其做 $5 0 0 \mathrm { ~ m ~ }$ 缓冲，面转栅格得到;多年平均降雨量取自美国国家海洋和大气管理局的NCEP在分析数据（年降雨量），多年平均后在GIS中运用自然领域插值法得到；地震灾害点和公路网数据通过核密度分析法得到栅格数据;选取滑坡灾害点数据用来验证滑坡灾害危险性;死亡人口和经济损失数据用来验证滑坡灾害潜在损失；最终的评估结果均取研究区内所有栅格的平均值。

![](images/fa3f6d751e8455cff8e1382be1b808fe770617e0ded74cd85912fb02ae9331a3.jpg)  
审图号：GS(2016)2953号图1“一带一路"地理位置Fig.1Location of study area

# 2.2 研究方法

滑坡分布在坡度、地形起伏度较大的山地和丘陵地区，而地势平坦的平原、盆地等地形区对于滑坡灾害来说是相对安全的区域，称其为滑坡灾害“安全区”[15-16]。先前许多研究者并没有对滑坡灾害进行安全区域的提取，一方面会导致评估工作的盲目性，使工作量增加;另一方面会出现评估结果误划的现象，会把明显地势平坦不会发生滑坡的地区错误的划分到滑坡灾害危险性极高的等级上[17-18] 。因此，本文在进行“一带一路”地区滑坡灾害风险评估之前先对研究区域进行安全区域的提取，可降低评估工作的盲目性，对提高滑坡灾害风险评估的科学性和效率具有重要的作用。

滑坡灾害风险是指各类承灾体可能受到滑坡灾害过程袭击而造成的直接经济损失、人员伤亡和环境破坏等[19]。风险是危险性与易损性的乘积[20 -21],易损性是指承灾体遭受滑坡灾害时,所造成的潜在损失的程度[22],由于本文研究区域大且表征潜在损失程度的数据收集困难，因此本文风险就用危险性与潜在损失的乘积来表示[23]。其中,危险性聚焦于滑坡灾害发生的概率[19,24],基于地形地貌、气象水文、地质构造等各种因素及其相互组合的关系，通过模糊层次分析法完成评估；损失则聚焦于滑坡灾害发生时承灾体所遭受的潜在损失，基于社会损失、物质损失和经济损失等各种因子及其相互组合的关系，通过模糊层次分析法完成评估。

2.2.1滑坡灾害安全区提取与验证在“一带一路"地区滑坡灾害风险的评估之中，对于安全区域的提取原理、过程以及在GIS中的操作流程进行了验证[15-16]。基于DEM 提取坡度小于10 地形起伏度小于 $2 0 \mathrm { ~ m ~ }$ 的地区为安全区域。由于所用DEM的分辨率为 $1 ~ \mathrm { k m }$ ，精度较低，提取的过程中有些地区的地形因子会被平滑掉，致使提取的安全区域面积过大。为了使其更具科学合理性，对安全区域的矢量图层向内做 $1 ~ \mathrm { k m }$ 缓冲，将 $1 ~ \mathrm { k m }$ 缓冲带并入安全区域，得到最终的安全区域。结果显示，安全区域主要分布在欧洲东部的东欧平原；亚洲的西伯利亚平原，北西伯利亚低地、科雷马低地，西亚的美索不达米亚平原、内夫得沙漠,中亚的图兰低地、图尔盖低地、伊希姆平原，南亚的恒河平原、印度河平原、印度大沙漠，中国的华北平原、长江中下游平原、东北平原、塔里木盆地、塔克拉玛干沙漠、吐鲁番盆地、巴丹吉林沙漠;非洲的撒哈拉沙漠、刚果盆地、卡拉哈迪沙漠[25]等地区。能够很好的区分平原、高原、盆地和沙漠等地区，界线清楚，提取结果较为合理。

此外，由于受DEM精度、灾害点统计误差、投影坐标转换等因素的影响，无法确保滑坡灾害点完全不落入安全区域。因此，采用实际滑坡灾害点(1191个)对其做进一步的验证,在GIS的支持下，运用安全区图层对滑坡灾害点图层进行裁剪。结果显示仅有 $4 . 7 \%$ (56个)的滑坡灾害点分布在安全区域内（图2），可以认为本文提取的安全区域科学、合理。因此，下文重点只对“一带一路”地区非安全区域滑坡灾害危险性、损失和风险进行评估。

表1数据来源与说明  
Tab.1Data resource and description   

<html><body><table><tr><td></td><td>数据名称</td><td>时间</td><td>分辨率</td><td>单位</td><td>数据来源</td></tr><tr><td>自然地理数据</td><td>工程地质岩组</td><td>2012</td><td>0.5°x0.5°</td><td>一</td><td>地球与环境科学数据出版商／PANGAEA</td></tr><tr><td></td><td>DEM</td><td>1</td><td>1x1</td><td>km</td><td>美国地质调查局/USGS</td></tr><tr><td rowspan="8">社会经济数据</td><td>河网</td><td>2010</td><td>1</td><td>一</td><td>美国地质调查局／USGS</td></tr><tr><td>多年平均降雨量</td><td>1901—2013</td><td>1</td><td>一</td><td>美国国家海洋和大气管理局／NOAA</td></tr><tr><td>>5级地震震中</td><td>1970—2015</td><td>1</td><td>一</td><td>中国地震台网／CSN</td></tr><tr><td>滑坡灾害点</td><td>2003、2007—2009</td><td>1</td><td>1</td><td>热带测雨卫星／TRMM</td></tr><tr><td>人口密度</td><td>2010</td><td>0.5°×0.5°</td><td>人·km-²</td><td>社会经济数据和应用中心／SEDAC</td></tr><tr><td>公路网</td><td>1</td><td>1</td><td>一</td><td>社会经济数据和应用中心／SEDAC</td></tr><tr><td>夜间灯光指数</td><td>2013</td><td>0.5°x0.5°</td><td>一</td><td>美国国家海洋和大气局</td></tr><tr><td>死亡人口、经济损失</td><td>1900—2015</td><td>二</td><td>人、USD</td><td>国际灾害数据库/EM-DAT</td></tr></table></body></html>

2.2.2模糊层次分析法模糊层次分析法(FAHP)是一种有效、多目标、多标准的决策方法[2],有其独有的特点,适用于影响因子无法定量表示的决策中。首先引入模糊矩阵代替判断矩阵可以更好地反映构造矩阵与人们主观判断的一致性[26],其次是改进了比较不同因子之间相对重要性的方法，使矩阵构建更具合理性，最主要的是此方法适合大区域的研究。其原理是模糊综合评价法和层次分析法相结合的一种综合评价方法。将问题及因素构建为目标层、准则层、方案层，然后根据专家打分构造下层对上层影响的判断矩阵，进而求出下层因素对上层因素相对重要性的权重，然后根据各因素隶属度等级分层次进行模糊评估，最后得出总的评估结果[27]。主要步骤有4步：

（1）将影响因子分层，构造滑坡灾害风险评估体系滑坡灾害风险评估包括危险性评估和损失评估两方面的内容，危险性评估是滑坡灾害的自然属性，损失分析是滑坡灾害的社会属性，风险评估是自然属性与社会属性的结合[19,28]。基于此,本文构建了“目标层A一准则层B一次指标层C一指标层D”四级滑坡灾害风险评估体系，选取2个二级指标（危险性、损失）、6个三级指标(3个危险性指标、3个损失指标)和9个四级指标(6个危险性指标、3个损失指标)作为滑坡灾害风险评估指标(表2)进行权重计算。

# （2）构造模糊判断矩阵

矩阵中同层次不同指标相比关系值用0.1\~0.9的标度给出（表3）。

（3）构造模糊判断一致矩阵，计算各指标综合权重

![](images/1decad5bcebf5cafee0fc3491cfc099a7eebf3d523ca34cb824733c67b047ad9.jpg)  
图2滑坡灾害安全区域验证  
Fig.2Verification of security zone of landslide disasters

Tab.2Assessment system for risk of landslide disasters   

<html><body><table><tr><td></td><td></td><td></td><td>评价指标</td><td>1极低</td><td></td><td>中等</td><td>4高</td><td>V极高</td><td>权重</td><td>排序</td></tr><tr><td>评系</td><td>危险</td><td>G地貌</td><td>D坡度／°</td><td>7080</td><td>4~15,</td><td>15~25</td><td>25~35</td><td>35~45</td><td>0.204</td><td>1</td></tr><tr><td></td><td></td><td></td><td>D地形起伏 度／m</td><td>0~200</td><td>200~500</td><td>500~900</td><td>900~1700</td><td>>1 700</td><td>0.167</td><td>3</td></tr><tr><td></td><td></td><td>C水文 气象</td><td>D距河流的 距离／m</td><td>>2000</td><td>1 500~2000 1000~1 500</td><td></td><td>500~1000</td><td><500</td><td>0.191</td><td>2</td></tr><tr><td></td><td></td><td></td><td>D4多年平均 降雨量／mm</td><td><100 >1600</td><td>100~200 800~1600</td><td>200~400</td><td>400~600</td><td>600~800</td><td>0.138</td><td>6</td></tr><tr><td></td><td></td><td>C地质 构造</td><td>D5地震点密 度／个·km-2</td><td><2 ×10-6</td><td>2 ×10-6 ~1×10-5</td><td>~6×10-5 1 ×10-5</td><td>6×10-5 ~3×10-4</td><td>~2×10-3 3×10-4</td><td>0.154</td><td>4</td></tr><tr><td></td><td></td><td></td><td>D6岩性</td><td>极坚硬岩</td><td>硬质岩</td><td>中等硬质岩</td><td>软质岩</td><td>土质</td><td>0.146</td><td>5</td></tr><tr><td></td><td>损失体 系B</td><td>C4社会 损失</td><td>D人口密度 ／人·km-2</td><td><20</td><td>20~40</td><td>40~80</td><td>80~160</td><td>>160</td><td>0.39</td><td>1</td></tr><tr><td></td><td></td><td>C5物质 损失</td><td>Dg公路线密 度／km·km-2</td><td><3×10-3</td><td>3×10-~ 1 ×10-2</td><td>1×10-²~ 2 ×10-1</td><td>2×10-1~ 3×10-1</td><td>3×10-1~ 9×10-1</td><td>0.32</td><td>2</td></tr><tr><td></td><td></td><td>C6经济 损失</td><td>D,夜间灯光 指数</td><td><4</td><td>4~5</td><td>5~10</td><td>10~20</td><td>20~60</td><td>0.29</td><td>3</td></tr></table></body></html>

表2滑坡灾害风险评估体系  
表3模糊判断矩阵标度法及其说明  
Tab.3Fuzzy judgment matrix scale and its meaning   

<html><body><table><tr><td>标度</td><td>定义</td><td>说明</td></tr><tr><td>0.5</td><td>同等重要</td><td>两元素相比较，同等重要</td></tr><tr><td>0.6</td><td>稍微重要</td><td>两元素相比较，一元素比另一元素稍微 重要</td></tr><tr><td>0.7</td><td>明显重要</td><td>两元素相比较，一元素比另一元素明显 重要</td></tr><tr><td>0.8</td><td>重要得多</td><td>两元素相比较，一元素比另一元素重要 得多</td></tr><tr><td>0.9</td><td>极端重要</td><td>两元素相比较，一元素比另一元素极端 重要</td></tr><tr><td>0.1,0.2 0.3,0.4</td><td>反比较</td><td>若元素αi与元素αj相比较得到判断 rij,则元素αj与元素αi相比较得到的 判断为riu=1-rij</td></tr></table></body></html>

$* \ : a _ { i } \ : , a _ { j }$ 表示不同因子： $r _ { i j }$ 是 $a _ { i }$ 比 $a _ { j }$ 重要程度的度量

对判断矩阵 ${ \cal { R } } = \left( r _ { i j } \right) n ^ { \prime } n$ 按行求和，记 $r _ { i }$ 为：

$$
r _ { i } = \ \sum _ { k = 1 } ^ { n } \ r _ { i k }
$$

模糊一致矩阵各元素值为：

$$
r _ { i j } = \frac { \big ( r _ { i } - r _ { j } \big ) } { 2 n } + 0 . 5
$$

由上述所得模糊判断一致矩阵求各指标的权重，其公式为：

$$
w _ { i } = \frac { 1 } { n } - \frac { 1 } { 2 a } + \frac { \displaystyle \sum _ { j = 1 } ^ { n } r _ { i j } } { n a } , ( i = 1 , 2 , \cdots , n )
$$

式中：参数 $\mathbf { \Delta } _ { a }$ 满足 $a \geqslant ( n - 1 ) / 2$ 。模糊层次分析法的运用已经非常成熟[27,29],各指标权重计算参考文献[16,26-27],详细计算步骤不再一一列出,只给出最终的综合权重值（表2）。

（4）模糊判断一致矩阵一致性检验

根据矩阵间相容性指标公式(4)求出模糊一致矩阵与其特征矩阵的相容性指标 $I$ ，当相容性指标 $I$ $\leqslant 0 . 1$ 时,认为该模糊一致矩阵符合一致性。如果模糊一致矩阵不符合一致性，则需要对该模糊判断矩阵进行调整,使其符合一致性[30]

$$
I = \frac { 1 } { n ^ { 2 } } \sum _ { i = 1 } ^ { n } \sum _ { j = 1 } ^ { n } \mid a _ { i j } - b _ { i j } - 1 \mid
$$

经检验，文中构建的模糊判断矩阵对应的模糊判断一致矩阵与其特征矩阵之间的相容系数均小于0.1，可以认为，本文构造的模糊判断矩阵符合一致性。各指标分级阈值的确定主要是基于自然断点法，结合相关文献，将阈值调整至临近整数或者等间隔取值[31]。最终得出D层9个指标的综合权重、分级阈值及排序情况（表2）。

# 2.2.3滑坡灾害风险评估体系

（1）滑坡灾害危险性评估指标体系

基于“一带一路”地区滑坡灾害形成规律及其空间分布特征，从地形地貌、气象水文和地质构造因素三个维度，选取指标评估滑坡灾害危险性。地形地貌因素着眼于孕灾环境的客观性，从灾害发生的机理出发，滑坡属于重力地貌类型，坡度是基本的自然地理要素，也是影响滑坡发育的重要因素，对滑坡灾害的发生起着控制性的作用;地形起伏度，是反映地形特征的一个宏观性指标，用某一确定区域内最大高程和最小高程之差来表示[32]。气象水文因素包括降水和距河流的距离两个指标，降水是滑坡灾害发生的重要诱发因素，滑坡灾害的发生与降雨历时和降雨强度均有关联，水分下渗会减小土体的抗剪强度及土体与基岩的摩擦阻力，并增加土体重力，从而诱发滑坡灾害;地表水对滑坡灾害形成的影响主要表现在地表水活动对斜坡的侵蚀程度，采用灾害点距河流的距离简化表征[32-33]。地质构造因素用工程地质岩组和地震来表示。工程地质岩组是形成滑坡灾害的内在因素，决定坡体岩石的软硬程度、应力分布以及变形破坏特征，为滑坡灾害的发生提供物质基础。地震对滑坡灾害影响主要是地震动的往复运动对边坡造成的附加力破坏了边坡的平衡条件,从而导致了滑坡的发生[34]。故围绕地形地貌、气象水文和地质构造因素选取坡度、地形起伏度、多年平均降雨量、距河流的距离、地层岩性和地震点密度等6个指标(表2)评估研究区滑坡灾害危险性。

# (2)滑坡灾害损失评估指标体系

基于“一带一路”地区滑坡灾害的特点和滑坡灾害所造成的可能破坏对象，从潜在社会性损失、潜在物质性损失和潜在经济损失三个维度，分别选取人口密度、公路线密度和夜间灯光指数3个具体的指标(表2)评估滑坡灾害潜在损失。

潜在社会损失着眼于滑坡灾害对人类生命的影响。人既是承灾体也是致灾诱发因子；因此用人口密度来表示滑坡灾害所造成的潜在社会损失。潜在物质损失是指滑坡灾害发生时所造成的物质损毁情况，公路既是人类活动的一部分可以作为致灾体来反映修筑公路时，由于开挖坡脚造成的坡体失稳，继而造成的滑坡灾害危险性，也可以作为承灾体来反映滑坡灾害的潜在物质损毁情况。由于本文所选表示潜在损失的指标较少，同时为了避免风险评估体系中指标的重复性，因此选取公路线密度来反映滑坡灾害的潜在物质损失。潜在经济损失是指滑坡灾害发生对各类经济承灾体所造成的直接或间接的经济损失，GDP是评估某个区域社会经济发展的重要因素，但是GDP不能综合地反映区域发展的整体水平。夜间灯光数据是人类活动强度和范围的体现，可以反映区域发展的整体水平[35]。因此,本文采用夜间灯光指数表征滑坡灾害潜在经济损失情况

# 2.2.4滑坡灾害风险评估模型

（1）危险性评估指标分级标准

在GIS的支持下，对各危险性指标图层使用公式(5)进行叠加分析，得到研究区滑坡灾害多因子危险性等级评分图层[36],即危险性等级指数 $H$ 。再使用公式(6)对危险性评分图层做归一化处理，并选用自然断点法将 ${ \cal { H } } _ { G }$ 分为5个等级：极低危险性$( 0 \sim 0 . 1 1 )$ ，低危险性 $( 0 . \ 1 1 \sim 0 . \ 2 3 \ )$ ，中等危险性（20 $( 0 . 2 3 \sim 0 . 3 5 )$ ，高危险性 $( 0 . 3 5 \sim 0 . 5 1 )$ 和极高危险性 $( 0 . 5 1 \sim 1 )$ 。 ${ \cal { H } } _ { G }$ 值越大表明滑坡灾害危险性越高，反之则越小。之所以选用自然断点法是因为可以通过衡量各类的方差，做到类别间方差最大，类别内方差最小，从而得到最优的分类结果。

$$
H = \sum X _ { i } Y _ { i }
$$

$$
H _ { G } = \frac { H - M i n ( H ) } { M a x ( H ) - M i n ( H ) }
$$

（2）损失评估指标分级标准

使用公式（7）对各损失指标图层进行叠加分析，得到研究区滑坡灾害多因子损失等级评分图层，即损失等级指数 $D$ ,再使用公式(8)对损失图层做归一化处理，并选用自然断点法将 $D _ { G }$ 化分为5个等级：极低损失 $( 0 \sim 0 . 1 )$ ，低损失 $( 0 . 1 \sim 0 . 3 )$ ，中等损失 $( 0 . 3 \sim 0 . 5 )$ ，高损失 $( 0 . 5 \sim 0 . 7 )$ 和极高损失$( 0 . 7 \sim 1 )$ 。 $D _ { \scriptscriptstyle G }$ 值越大表明滑坡灾害造成的潜在损失越严重，反之则损失越低。

$$
D = \sum W _ { i } Y _ { i }
$$

$$
D _ { G } = \frac { D - M i n ( D ) } { M a x ( D ) - M i n ( D ) }
$$

（3）风险评估指标分级标准

采用公式(9)对滑坡灾害危险性图层和承灾体损失图层进行叠加分析，得到滑坡灾害风险等级评分图层，即风险等级指数 $R$ ;再使用公式(10)对风险图层进行归一化处理，并选用自然断点法将 $R _ { G }$ 化分为5个等级：极低风险 $( 0 \sim 0 . 0 7 )$ ，低风险（0.07$\sim 0 . 1 7 \$ ），中等风险 $( 0 . 1 7 \sim 0 . 3 )$ ，高风险 $\left( 0 . 3 1 \sim \right.$ 0.47），极高风险 $( 0 . 4 7 \sim 1 )$ 。 $R _ { G }$ 值越大表明滑坡灾害风险越高，反之则越低。

$$
\boldsymbol { R } = \boldsymbol { H } \times \boldsymbol { D }
$$

$$
R _ { G } = \frac { R - M i n ( R ) } { M a x ( R ) - M i n ( R ) }
$$

公式 $( 5 ) \sim ( 1 0 )$ 中： ${ \cal { H } } _ { G }$ 为归一化危险性等级指数、$D _ { \scriptscriptstyle { G } }$ 为归一化损失等级指数、 $R$ 为综合风险等级指数 $\ 、 X _ { i } 、 W _ { i }$ 分别为危险性和损失各指标的综合权重、$Y _ { i }$ 为各指标等级打分 $\mathbf { \nabla } \mathcal { M } a x$ 为结果取最大值 $\ 、 M i n$ 为结果取最小值。

# 3 结果分析

# 3.1滑坡灾害危险性评估结果

3.1.1单因子滑坡灾害危险性根据滑坡灾害危险性评估指标体系（表2）中各因子的分级阈值，在GIS 的支持下形成“一带一路”地区滑坡灾害单因子危险性图（图3）。结果表明，“一带一路”地区容易诱发滑坡灾害的条件为：坡度为 $2 5 \ \sim 4 5 ^ { \circ }$ ,地形起伏度大于 $9 0 0 \mathrm { ~ m ~ }$ ,距河网的距离小于 $5 0 0 \mathrm { ~ m ~ }$ ,多年平均降雨量介于 $4 0 0 \sim 8 0 0 ~ \mathrm { { m m } }$ ,地震密度为 $3 \times 1 0 ^ { - 4 } \sim 2$ $\times 1 0 ^ { - 3 }$ 个： $\mathrm { k m } ^ { - 2 }$ ,工程地质岩组为中等硬质岩体、软质岩和土质岩体。总体而言，地形起伏度、地震密度较大，松软岩石的地区滑坡灾害危险性较高；此外，地表水对斜坡体的侵蚀冲刷作用亦会加剧滑坡灾害的发生。表2中各因子的分级阈值是根据因子孕灾能力的大小来确定的，孕灾能力越强分级阈值越大，危险性等级越高；反之越小。

![](images/62db91be9c530d116a6a3918d2b163a99453307bb7b8f4e0ce36d14de26d3589.jpg)  
图3滑坡灾害单因子危险性等级图  
Fig.3Hazard level of single factorof landslide disasters

就危险性评估体系中各因子危险性分级阈值而言，坡度、降雨和工程地质岩组并未表现出对滑坡灾害完全正向或负向的贡献，而是在各因子特定范围内发挥作用。地形起伏度和地震点密度表现出与滑坡灾害危险性正向相关的关系，各因子分级阈值越大，危险性越高。距河流的距离与滑坡灾害危险性呈现负向相关的关系，即某空间位置距离河流的距离越小越容易诱发滑坡灾害。这可能是因为距河流越近的区域干扰较强，所以在同等情况的地理环境和地质构造因素下，发生滑坡灾害的概率更高。

综上所述，滑坡灾害的发生是多因素综合作用的结果，单因子危险性等级图层用于反映各因子对滑坡灾害贡献的整体性趋势，最终用以表征研究区滑坡灾害危险性，滑坡灾害危险性图层是由单个危险性因子图层结合各自的综合权重叠加得到。

3.1.2滑坡灾害危险性根据“一带一路"滑坡灾害危险性评估体系（表2），在GIS的支持下将6个因子图层结合各自的综合权重按照危险性评估分级标准(公式5、6)叠加，生成“一带一路"地区滑坡灾害危险性图（图4）。由图4可以看出，“一带一路”非安全区域中，滑坡灾害以中、低危险性( $8 0 . 3 \%$ ）为主。极高、高和中等危险性区域主要分布在中国西南山区、黄土高原、秦巴山地、江南丘陵、云贵高原、喜马拉雅山脉一带,南亚苏莱曼山脉、东南亚那加丘陵、若开山脉、长山山脉一带，西亚托罗斯山脉、伊朗高原、扎格罗斯山脉一带及环太平洋岛链，中亚哈萨克丘陵地区，欧洲阿尔卑斯山脉一带，非洲东非大裂谷和东非高原一带。“一带一路”非安全区域中，滑坡灾害危险性具体分布如表4。

# 3.2滑坡灾害损失评估结果

3.2.1单因子滑坡灾害损失根据滑坡灾害损失评估体系(表2)中各指标分级阈值,在GIS 的支持下生成“一带一路"地区滑坡灾害单因子损失图（图5）。结果表明，“一带一路”地区滑坡灾害容易造成潜在损失的承灾体条件为：人口密度为 $8 0 \sim 1 6 0$ 人· $\mathrm { k m } ^ { - 2 }$ ,公路线密度为 $0 . 2 \sim 0 . 9 \mathrm { k m } \cdot \mathrm { k m } ^ { - 2 }$ ,夜间灯光指数为 $2 0 \sim 6 0$ 。总体而言，单因子滑坡灾害极高、高损失区域主要分布在人口密度大、公路设施完善、区域综合发展水平较高的地区。需要说明的是，表2中各承灾体因子的分级阈值是根据承灾能力的

![](images/7457b4d41c761e9a5af4165d54950a3a800d5dc20995d2ae3cdd9223aa80b197.jpg)  
图4滑坡灾害危险性等级区划图  
Fig.4Hazards level oflandslides

# 表4“一带一路"地区滑坡灾害危险性空间分布

Tab.4Hazard of landslides distribution along the Silk Road Economic Belt   

<html><body><table><tr><td>危险性 等级</td><td>面积比 /%</td><td>经济走廊</td><td>国家</td></tr><tr><td>极低危险性</td><td>30</td><td>中蒙俄经济走廊</td><td>贝宁(南）伊拉克、里海、俄罗斯(北）、澳大利亚</td></tr><tr><td>低危险性</td><td>28.2</td><td>亚一西亚经济走廊</td><td>新亚欧大陆桥西端、中国一中摩洛哥、几内亚、科特迪瓦、加纳、尼日利亚、喀麦隆、突尼斯、塞拉利昂、中非、安 哥拉(东）南非(西)德国(北）匈牙利、乌克兰、英国(东南）奥地利(东北)、 叙利亚(东南）以色列、尼泊尔(南）蒙古(南）沙特阿拉伯、巴基斯坦(南)</td></tr><tr><td>中等危险性</td><td>22.1</td><td>南半岛经济走廊</td><td>孟中印缅经济走廊、中国一中摩洛哥、利比里亚、几内亚、科特迪瓦、加纳、多哥、贝宁(北）、尼日利亚、喀麦隆、 中非、加蓬(北)刚果(布)埃塞俄比亚、肯尼亚、乌干达、纳米比亚、莱索托、英 国(西北)，爱尔兰、法国、德国(南）、卢森堡、西班牙、斯洛伐克、罗马尼亚、克罗 地亚、芬兰、瑞典、叙利亚(西)阿富汗、不丹、老挝、蒙古(北)约旦、伊朗、也门、 缅甸、泰国、朝鲜、越南、印度、哈萨克斯坦、中国(西南山区、东南丘陵山区、台湾、</td></tr><tr><td>高危险性</td><td>13.9</td><td>路、新亚欧大陆桥西端</td><td>秦巴山区、黄土高原)俄罗斯(南) 中巴经济走廊、海上丝绸之喀麦隆(小部分地区)、加蓬(中)、刚果(金)、肯尼亚(小部分地区)乌干达、坦桑 尼亚、赞比亚、马拉维、莫桑比克、津巴布韦、马达加斯加、安哥拉(西)、南非 （东）斯威士兰、冰岛、比利时、葡萄牙、意大利、瑞士、捷克、奥地利(西南）、保加 利亚、塞尔维亚、波黑、阿尔巴尼亚、希腊、挪威、吉尔吉斯斯坦、亚美尼亚、黎巴 嫩、尼泊尔(北)塔吉克斯坦、巴基斯坦(北）、土耳其、印度尼西亚、韩国、日本、</td></tr><tr><td>极高危险性5.8</td><td></td><td>海上丝绸之路</td><td>菲律宾、中国(西南山区、东南丘陵山区、台湾、秦巴山区、黄土高原) 赤道几内亚、加蓬(南)卢旺达、布隆迪</td></tr></table></body></html>

![](images/d6202f20bc9e14741749b716ce58831d6653c2521b501afb6f4a397dd3c627f5.jpg)  
图5滑坡灾害单因子损失等级图  
Fig.5Vulnerability level of single factor of landslide disasters

大小来确定的，承灾体因子的承灾能力越强，分级阈值越大；反之越小。

就损失评估体系中各因子损失分级阈值而言，人口密度、公路线密度和夜间灯光指数三个指标均表现出与滑坡灾害潜在损失正向相关的关系。因为人口密度大且人员越集中的区域，一旦发生滑坡灾害，造成的人员伤亡情况会越严重；对于公路来说，它是滑坡灾害最直接的物质承灾体，密度越大，承灾面积越大，发生滑坡灾害造成物质损毁情况会越严重;夜间灯光指数是表征人类活动强度和范围的体现，因此灯光越亮，说明该区域经济发达、基础设施齐全、人员分布集中，一旦发生滑坡灾害，亦会造成严重的损失。

综上所述，单因子滑坡灾害损失等级图层反映了滑坡灾害发生时对于各自所造成的潜在损失情况，最终用以表征研究区滑坡灾害损失，滑坡灾害损失图层是由单个损失图层结合各自的综合权重叠加得到。

3.2.2滑坡灾害损失根据"一带一路"地区滑坡灾害损失评估体系（表2），在GIS的支持下将3个因子图层结合各自的综合权重，按照损失评估分级标准(公式7、8），生成“一带一路”地区滑坡灾害损失图(图6)。由图6可以看出，“一带一路"非安全区域中，滑坡灾害以极低和低损失 $( 7 4 . 4 \%$ )为主。滑坡损失呈现出中国东南和西南部、东南亚北部、南亚南部、欧洲西南部较高，非洲、欧洲北部、亚洲北部(蒙古和俄罗斯)、中亚、中国西北部、澳大利亚较低的空间分布特征。极高、高损失区域主要分布在人□密度大、经济条件好、公路设施齐全的国家和地区。“一带一路"非安全区域中，滑坡灾害潜在损失具体分布如表5。

# 3.3 滑坡灾害风险

基于滑坡灾害危险性和潜在损失，在GIS的支持下根据滑坡灾害风险评估指标分级标准（公式9、10），将危险性图层与损失图层等权重相乘并进行归一化处理，得到"一带一路”地区滑坡灾害风险图层，并按照自然断点法将风险等级指数分为极高、高、中等、低和极低5等级（图7）。从图7可以看出，“一带一路”非安全区域中,滑坡灾害以极低和低风险 $( 7 0 . 2 \%$ )为主。极高、高和中等风险区主要分布在东南亚长山山脉一带，中国黄土高原、云贵高原、喜马拉雅山脉一带，南亚东高止山脉、德干高原

![](images/b9d544b49d3d009bd615e031fa374eab8125cbb40d283fa4e152df24bb10eae9.jpg)  
图6“一带一路"地区滑坡灾害损失等级  
Fig.6Damage level of landslides along the Silk Road Economic Belt

# 表5“一带一路"地区滑坡灾害损失空间分布

Tab.5Damage of landslides distribution along the Silk Road Economic Belt   

<html><body><table><tr><td>损失等级</td><td>面积比例 /%</td><td>经济带</td><td>国家</td></tr><tr><td>极低损失</td><td>43.7</td><td>中蒙俄经济走廊 中国一中亚一西亚 经济走廊</td><td>吉尔吉斯斯坦、叙利亚(东）尼泊尔、不丹、蒙古、里海、伊朗、也门、塔吉克斯坦(东）、沙特 阿拉伯、印度尼西亚、马来西亚、哈萨克斯坦、中国(中、西部）俄罗斯、冰岛、芬兰、瑞典、 挪威、利比里亚、喀麦隆、赤道几内亚、中非、加蓬、刚果(布）刚果(金）坦桑尼亚、赞比 亚、莫桑比克、马达加斯加、安哥拉、纳米比亚</td></tr><tr><td>低损失</td><td>30.7</td><td>中国一中南半岛经济 走廊、中巴经济走廊</td><td>黎巴嫩、阿富汗、老挝、约旦、以色列、伊朗、塔吉克斯坦(中）缅甸、巴基斯坦(南）、泰国、 朝鲜、日本(北)印度尼西亚、菲律宾、英国(北）爱尔兰、西班牙、葡萄牙、乌克兰(东）、 克罗地亚(南）摩洛哥(东）塞拉利昂、几内亚、科特迪瓦、加纳、埃塞俄比亚、肯尼亚、乌 干达(北）津巴布韦、南非、莱索托、澳大利亚</td></tr><tr><td>中等损失</td><td>12.9</td><td>孟中印缅经济走廊</td><td>亚美尼亚、叙利亚(西)伊拉克、尼泊尔、伊朗、塔吉克斯坦(西)、沙特阿拉伯(小部分）、 土耳其、越南、印度、阿塞拜疆、中国(东南山区小部分地区）、白俄罗斯(小部分）法国、西 班牙、匈牙利、乌克兰(西)、罗马尼亚、保加利亚、摩尔多瓦、塞尔维亚、波黑、阿尔巴尼亚、 希腊、摩洛哥(西）多哥、贝宁、尼日利亚、马拉维、斯威士兰、韩国</td></tr><tr><td>高损失</td><td>9.4</td><td>丝绸之路</td><td>中巴经济走廊、海上巴基斯坦(北)、斯里兰卡、印度、日本、中国(东南丘陵山区、台湾、西南山区、秦巴山区、黄 土高原)英国(南）德国(南部小部分地区）意大利、瑞士、捷克、奥地利、斯洛伐克、克 罗地亚(北)突尼斯(北）乌干达(南）卢旺达、布隆迪(北)</td></tr><tr><td>极高损失</td><td>3.3</td><td>新亚欧大陆桥西端</td><td>法国(北部）、比利时、卢森堡、意大利</td></tr></table></body></html>

![](images/b2d683f1752b3a6f9e3eebeee343c88fd75eb96d2c6c96b9f20c22159d122765.jpg)  
图7“一带一路"地区滑坡灾害风险等级图  
Fig.7 Risk level of landslides along the Silk Road Economic Belt

一带,西亚伊朗高原和大高加索山脉一带，非洲东非高原、东非大裂谷一带，欧洲阿尔卑斯山脉和阿登高原一带等孕灾能力强，人口密度大、经济发达、公路

设施齐全的国家和地区。

“一带一路"非安全区域中,滑坡灾害风险具体 分布如表6。

# 表6“一带一路"地区滑坡灾害风险空间分布

Tab.6Risk of landslides distribution along the Silk Road Economic Belt   

<html><body><table><tr><td>风险等级</td><td>面积比例 /%</td><td>经济带</td><td>国家</td></tr><tr><td>极低风险</td><td>44.7</td><td>中蒙俄经济走廊</td><td>蒙古、里海、也门(东）、沙特阿拉伯、斯里兰卡(南）、哈萨克斯坦、中国(中、西部）、俄罗 斯、芬兰、中非、刚果(布)纳米比亚、澳大利亚</td></tr><tr><td>低风险</td><td>25.5</td><td>中国一中亚一西亚经 济走廊</td><td>吉尔吉斯斯坦、叙利亚(东）尼泊尔(北）不丹(北）约旦、以色列、伊朗(东）塔吉克斯 坦(东）巴基斯坦(南）朝鲜、印度尼西亚、菲律宾、中国(西南地区）冰岛、德国(北）、乌 克兰(东)希腊(南)瑞典(北)挪威、摩洛哥(东)突尼斯(南）几内亚、科特迪瓦(北) 喀麦隆、赤道几内亚、加蓬、刚果(金）肯尼亚、赞比亚(西南）莫桑比克(南）安哥拉、南 非</td></tr><tr><td>中等风险</td><td>15.3</td><td>孟中印缅经济走廊、 走廊、海上丝绸之路</td><td>阿富汗、尼泊尔(南)不丹(南)老挝、塔吉克斯坦(西）缅甸、泰国、土耳其、越南、中国 （东南丘陵山区、台湾、西南山区、秦巴山区、黄土高原）英国、爱尔兰、法国、西班牙、葡萄 中国—中南半岛经济牙、匈牙利、乌克兰(西)罗马尼亚、克罗地亚、瑞典(南)、摩洛哥(西)突尼斯(北）塞拉 利昂、利比里亚、科特迪瓦(南)、加纳、多哥、贝宁、尼日利亚、埃塞俄比亚、乌干达、坦桑尼 亚、赞比亚(东北)马拉维、莫桑比克(北)津巴布韦、马达加斯加、莱索托</td></tr><tr><td>高风险</td><td>10.3</td><td>欧大陆桥西端</td><td>亚美尼亚、叙利亚(西)黎巴嫩、伊拉克、格鲁吉亚、伊朗(西)、也门(西)巴基斯坦(北)、 中巴经济走廊、新亚斯里兰卡(北)、印度、阿塞拜疆、中国(东南丘陵山区、台湾、西南山区、秦巴山区、黄土高 原等小部分地区）德国(南部小部分地区）、比利时、卢森堡、意大利、捷克、奥地利、斯洛 伐克、保加利亚、塞尔维亚、波黑、阿尔巴尼亚、希腊(北）肯尼亚(西南一部分）斯威士兰</td></tr><tr><td>极高风险</td><td>4.2</td><td>海上丝绸之路</td><td>韩国、日本、瑞士、斯洛文尼亚、卢旺达、布隆迪</td></tr></table></body></html>

# 4讨论与结论

# 4.1讨论

（1）“一带一路”地区滑坡灾害危险性和潜在损失验证滑坡灾害风险是危险性与损失的乘积，危险性和损失评估结果的可靠性对于风险评估结果的科学合理性有着直接的影响，因而有必要对基于模糊层次分析法评估的滑坡灾害危险性和损失结果进行验证。

$\textcircled{1}$ 运用随机点和受试者工作特征曲线（Receiv-erOperatingCharacteristic Curve,ROC）曲线对危险性评估结果进行验证。ROC曲线是反映敏感性和特异性连续变量的综合指标[37],被广泛的应用于滑坡灾害危险性评估结果的验证中。AUC值是ROC曲线与横轴间面积的值,该值介于 $0 . 5 \sim 1$ 之间,值越大表明评估结果的精度越高[38]。非安全区域中,图8a是2003年、2007—2009 年，“一带一路”非安全区域滑坡灾害的分布情况，共有滑坡灾害点1135个，基于GIS空间分析工具 $$ 提取分析 $$ 提取至点的方法，提取滑坡灾害点的危险性等级情况。结果表明：极低、低、中等、高和极高危险性区域内分布的滑坡灾害点个数分别为8个( $0 . 7 \%$ ）、40个$( 3 . 5 \%$ ）、52个（ $( 4 . 6 \%$ ）、502个（ $4 4 . 2 \%$ )和533个中 $47 \%$ ）,滑坡灾害点 $( 9 1 . 2 \%$ )主要分布在极高和高的危险性等级区域内。图8b为滑坡灾害危险性评估结果的ROC曲线，可以看出基于模糊层次分析法评估的“一带一路”地区滑坡灾害危险性精度显示为0.823，表明运用此方法评估的滑坡灾害危险性值与实际值在 $9 5 \%$ 的置信度水平上无显著差异，结果较为理想。

$\textcircled{2}$ 运用“一带一路"地区1900—2015 年滑坡灾害造成的人口死亡和经济损失的空间分布，来验证本文评估的滑坡灾害潜在损失。图8c为滑坡灾害造成的死亡人口情况，可以看出滑坡灾害造成的死亡人口集中分布在中国、东南亚和南亚地区，死亡人口的空间分布从高到底依次是中国( $> 5 \ 0 0 0$ 人），东南亚 $( 2 ~ 0 0 0 ~ { \sim } 5 ~ 0 0 0$ 人），南亚、西亚( $( 7 0 0 \sim 2 \ 0 0 0$ 人），中亚、西欧( $1 0 0 \sim 7 0 0$ 人），非洲、东欧和北亚（ $< 1 0 0$ 人）;图8d是滑坡灾害造成的经济损失情况，可以看出中国、东南亚和南亚是经济损失较为严重的地区，经济损失空间分布从高到底依次是中国$( > 2 . 5 \times 1 0 ^ { 8 }$ USD）,东南亚 $( 1 . 6 \times 1 0 ^ { 8 } \sim 2 . 5 \times 1 0 ^ { 8 }$ USD）,南亚 $( 0 . 9 \times 1 0 ^ { 8 } \sim 1 . 6 \times 1 0 ^ { 8 }$ USD）,西亚和西欧 $( 0 . 3 \times 1 0 ^ { 8 } \sim 0 . 9 \times 1 0 ^ { 8 }$ USD）,非洲、东欧和北亚（ $< 0 . 3 \times 1 0 ^ { 8 }$ USD）。这与本文评估滑坡灾害潜在损失具有很好的一致性。

综上，基于模糊层次分析法评估的“一带一路”非安全区域滑坡灾害危险性和损失结果基本可信，继而可以说明本文评估的滑坡灾害风险区划结果科学、可信，结果可以为“一带一路”沿线国家防的灾

![](images/79f2625677a16f7aa2f3aac3d51ebea6167c9c63ae638a6dadb3a4b16612dbd5.jpg)  
图8“一带一路"地区滑坡灾害风险结果验证  
Fig.8Verification of risk of landslide disasters of“The Belt and Road Initiative"

减灾提供依据。

（2）滑坡灾害风险评估结果精度影响因素分析：

$\textcircled{1}$ 在进行滑坡灾害风险评估之前，提取研究区安全区域，并对其做了验证，结果表明本文提取的安全区域具有一定的科学性和合理性，但是仍然有$4 . 7 \%$ 滑坡灾害点落在安全区域内。首先，因为滑坡灾害的发生受多因子的共同作用，本文在安全区域的提取过程中，只考虑了坡度和地形起伏度两个因子，是否还有其他因子也能更好地识别安全区域,这需要在今后的工作和研究中进一步探讨。其次，由于获取DEM的分辨率为 $1 ~ \mathrm { k m }$ ，精度较粗，造成实际提取的安全区域面积有可能偏大，尽管对初步提取的安全区域边界向内做了 $1 ~ \mathrm { k m }$ 缓冲，但是缓冲区距离没有统一的标准。

$\textcircled{2}$ 本文选择3类6个致灾因子和3类3个承载体因子分别构建滑坡灾害危险性评估体系和损失评估体系进行“一带一路”地区滑坡灾害风险评估。

从评估结果来看，基本符合实际滑坡灾害点的分布情况，但是评估结果仍有细小的偏差。通过分析数据和研究方法，得出出现这种问题的原因主要有两点：首先本文研究区域较大，数据种类多且分辨率不一，在危险性、损失和风险评估时，考虑到统一数据分辨率，最终将所有数据分辨率统一到0.5，精度较粗，导致评估结果会有一定误差。其次由于受灾害点统计误差，投影、坐标转换等因素影响，无法确保滑坡灾害点完全落入极高、高危险性区域内，因此在极低、低危险性区域内仍会有少许滑坡灾害点的分布。综上，今后对大区域滑坡灾害风险评估时提高数据精度是首要考虑的问题。

# 4.2结论

（1）本文结合地形因子坡度和地形起伏度，基于GIS空间分析方法，提取研究区安全区域，并对其作了相关验证。结果表明，仅有 $4 . 7 \%$ (56个）的滑坡灾害点落在安全区域内，且安全区域能够很好的区分平原、盆地和沙漠等地区，界限清楚，提取结果

较为合理。

（2）本文以“一带一路”为研究区，基于“风险$\mathbf { \sigma } = \mathbf { \sigma }$ 危险性 $\times$ 损失”的风险评估模型,采用模糊层次分析法定量评估“一带一路”沿线地区滑坡灾害危险性、损失和风险,结果有望为“一带一路”沿线国家与地区滑坡灾害的防治提供参考。研究结果表明： $\textcircled{1}$ “一带一路”地区容易诱发滑坡灾害的条件为：坡度为 $2 5 \ \sim 4 5 ^ { \circ }$ ,地形起伏度大于 $9 0 0 \mathrm { ~ m ~ }$ ,距河网的距离小于 $5 0 0 \mathrm { ~ m ~ }$ ,多年平均降雨量介于 $4 0 0 \sim$ $8 0 0 ~ \mathrm { { m m } }$ ,地震密度为 $3 \times 1 0 ^ { - 4 } \sim 2 \times 1 0 ^ { - 3 }$ 个： $\mathrm { k m } ^ { - 2 }$ ，工程地质岩组为中等硬质岩体、软质岩和土质岩体。非安全区域中，滑坡灾害极高、高、中等、低和极低危险性区域所占面积比分别为 $5 . 8 \% . 1 3 . 9 \%$ 、22.$1 \%$ $, 2 8 . 2 \%$ ） $30 \%$ ,以中、低危险性 $( 8 0 . 3 \% )$ )为主，极高、高危险性区域主要分布在地形起伏度、地震密度较大,松软岩石等孕灾环境好的高原、山地和丘陵等地形区。用研究区1135个滑坡灾害点样本数据对其进行验证,共有 $\textbf { 1 0 3 5 }$ 个 $( 9 1 . 2 \%$ )滑坡灾害灾害点分布在极高、高危险性区域内，且危险性评估结果精度 $A U C$ 值为0.823。 $\textcircled{2}$ “一带一路”地区滑坡灾害容易造成潜在损失的承灾体条件为：人口密度为 $8 0 \sim 1 6 0$ 人· $\mathrm { k m } ^ { - 2 }$ ,公路线密度为 $0 . 2 \sim 0 . 9 { \mathrm { ~ k m } }$ ： $\mathrm { k m } ^ { - 2 }$ ,夜间灯光指数为 $2 0 \sim 6 0$ 。非安全区域中,滑坡灾害潜在损失普遍较低,极高、高、中等、低和极低损失区域所占面积比分别为 $3 . 3 \% . 9 . 4 \% . 1 2$ ：$9 \% . 3 0 . 7 \% . 4 3 . 7 \%$ 。极高、高损失区域主要分布在中国东南,西南,黄土高原,秦巴山地、东南亚北部、南亚、西亚西北部、欧洲西南部和非洲少许国家等人口密度大、公路设施完善、区域综合发展水平较高的地区。 $\textcircled{3}$ “一带一路”非安全区域中,滑坡灾害风险极低、低、中等、高和极高风险区面积占所占比例分别为 $4 4 . 7 \% . 2 5 . 5 \% . 1 5 . 3 \% . 1 0 . 3 \% . 4 . 2 \% ,$ 以极低、低风险 $( 7 0 . 2 \% )$ )为主。

综上，本文评估的滑坡灾害风险等级区划结果科学合理，可以为“一带一路”沿线国家与地区滑坡灾害的防治提供科学参考。

# 参考文献(References)

[1］刘卫东.“一带一路"战略的科学内涵与科学问题[J].地理科 学进展,2015,34（5）:538-544.[LIUWeidong.Scientificunderstandingof the Belt and Road Initiative of China and related research themes[J].Progress in Geography,2015,34（5）:538- 544.]

[2]GAO JM,SANG Y H.Identification and estimation of landslidedebris flow disaster risk in primary and middle school campuses in a mountainous area of southwest China[J].International Journal of Disaster Risk Reduction,2017,25(7) :60 -71.   
[3]KAWAGOE S,KAZAMA S,SARUKKALIGE P R. Assessment of snowmelt triggered landslide hazard and risk in Japan[J].Cold Regions Science and Technology,2009,58(3）:120 -129.   
[4］CUTTER S W.Social vulnerability to environmental hazards[J]. Social Science Quarterly,2003,84(2):243 -261.   
[5]GUZZETTI F,REICHENBACH P,CARDINALI M,et al. Probabilistic landslide hazard assessment at the basin scale[J].Geomorphology,2005,72(1/4）:272-299.   
[6]庄建琦,崔鹏,葛永刚,等.“5·12"汶川地震崩塌滑坡危险性 评价——以都汶公路沿线为例[J].岩石力学与工程学报, 2010,29（2）:3735-3742.[ZHUANG Jianqi,CUI Peng，GE Yonggang,et al. Risk assessment of collapse and landslides caused by $5 \cdot 1 2$ Wenchuan earthquake:A case study of DujiangyanWenchchuan highway[J].Chinese Journal of Rock Mechanicsand Engineering,2010,29(2）:3735-3742.]   
[7]KUMAR A,ASTHANA A K L,PRIYANKA R S,et al. Assessment of landslide hazards induced by extreme rainfall event in Jammu and Kashmir Himalaya,northwest India[J].Geomorphology,2017, 284(1) :72 -87.   
[8］VEGA JA,HIDALGO C A. Quantitative risk assessment of landslides triggered by earthquakes and rainfall based on direct costs of urban buildings[J].Geomorphology,2016,273（12）:217-235.   
[9］唐金荣,张涛,周平,等.“一带一路"矿产资源分布与投资环境 [J].地质通报,2015,34（10）:1918-1928.[TANG Jinrong, ZHANG Tao,ZHOU Ping,et al.An analysis of mineral resources distribution and investment climate in the“One Belt,One Road” countries[J].Geological Bulletin of China,2015,34（10）:1918- 1928.]   
[10］刘大文.“一带一路"地质调查工作刍议［J].中国地质,2015, 42（4）:819 - 827.[LIU Dawen.A tentative discussion on the “Belt and Road"geological surveyJ].Geology inChina,2015,42 (4):819 -827.]   
[11]QIU J. Landslide risks rise up agenda[J]. Nature,2014,511 (7509) :272.   
[12]PETLEY D.Global patterns of loss of life from landslides[J]. Geology,2012,40(10):927 -930.   
[13］崔鹏,胡凯衡,陈华勇,等.丝绸之路经济带自然灾害与重大工 程风险[J].科学通报,2018,63（11）:989-997.[CUI Pei,HU Kaiheng,CHEN Huayong,et al. Risksalong the Silk Road Economic Belt owing to natural hazards and construction of major projects[J]. Chin Sci Bull,2018,63(11):989 -997.]   
[14]NADIMF,KJEKSTAD O,PEDUZZI P,et al. Global landslide and avalanche hotspots[J].Landslides,2006,3(2）:159 -173.   
[15］曹璞源,胡胜,邱海军,等.基于模糊层次分析的西安市地质灾 害危险性评价［J].干旱区资源与环境,2017,31（8)：136- 142.[CAO Puyuan,HU Sheng,QIU Haijun,et al. Evaluation of geological hazards and its validation in Xi'an City based on FAHP [J]. Journal of Arid Land Resources and Environment,2017,31 （8):136 -142.]   
[16］杨冬冬,胡胜,邱海军,等.基于模糊层次分析法对“一带一路” 重要区域地质灾害危险性评价——以关中经济区为例[J].第 四纪研究,2017,37（3）:633-644.［YANG Dongdong,HU Sheng,QIU Haijun,et al. Danger assessment of geological disasters in an important region of"The Belt and Road"based on FAHP:A case study of Guanzhong Economic Region[J]. Quaternary sciences,2017,37(3）:633-644.]   
[17］高克昌，崔鹏,赵纯勇,等.基于地理信息系统和信息量模型的 滑坡危险性评价——以重庆万州为例[J].岩石力学与工程学 报,2006,25（5）:991-996.[GAO Kechang,CUI Peng,ZHAO Chunyong,et al.Landslide hazard evaluation of Wanzhou based on GIS information value method in the three gorgesreservoirJ]. Chinese Journal of Rock Mechanics and Engineering,2006,25 (5) :991 -996.]   
[18］胡胜,曹明明,李婷,等.基于AHP 和GIS 的陕西省地震次生地 质灾害危险性评价[J].第四纪研究,2014,34（2）：336－345. [HU Sheng,CAO Mingming,LI Ting,et al. Danger assessment of earthquake-induced geological disasters in Shaanxi Province based on AHP and GIS[J]. Quaternary sciences,2014,34（2）:336 - 345.]   
[19］殷坤龙.滑坡灾害风险分析[M].北京：科学出版社,2010. [YIN Kunlong.Landslide hazard risk evaluation[M].Beijing:Science Press,2010.]   
[20]ZHANG D H,ZHAO Y J,XUE D J,et al. Application of RS and GIS technology in disaster risk assessment of single landslide[J]. Earth & Environment,2011,39(1）:69-75.   
[21]FELL R.Landslide risk assessment and acceptable risk[J]. Canadian Geotechnical Journal,1994,31(2）:261-272.   
[22]KANUNGO D P,ARORA M K,GUPTA RP,et al. Landslide risk assessment using concepts of danger pixels and fuzzy set theory in Darjeeling Himalayas[J].Landslides,2008,5(4） :407 -416.   
[23］崔鹏.汶川地震山地灾害形成机理与风险控制[M].北京：科 学出版社,2011.[CUI Peng.Formation mechanism and risk control of mountain disasters in Wenchuan earthquake[M].Beijing : Science Press,2011.]   
[24］崔鹏,苏凤环,邹强,等.青藏高原山地灾害和气象灾害风险评 估与减灾对策[J].科学通报,2015,60(32）:3067-3077.［CUI Peng,SU Fenghuan,ZOU Qiang,et al.Risk assessment and disaster reduction strategies for mountainous and meteorological hazards in Tibetan Plateau[J]. Science Bulletin,2015,60（32）:3067 - 3077. ]   
[25］郑芷青.世界自然地理地图集［M].北京：星球地图出版社, 2009:3-109.[ZHENG Zhiqing.World atlas of natural geography [M]. Beijing:Star map press,2009:3 -109.]   
[26］张吉军.模糊层次分析法(FAHP)[J].模糊系统与数学,2000, 14（2）:80-88.[ZHANG Jijun.Fuzzy analytical hierarchy process [J].Fuzzy Systems and Mathematics,2000,14(2）:80 -88.]   
[27］张栋,范育青,辛程鹏.基于FAHP 的高原山地滑坡危险性评 价[J].环境工程,2014,32（10）:133－136.[ZHANG Dong, FAN Yuqing,XIN Chengpeng. Application of fuzzy analytic hierarchy process in hazard evaluation of landslide in the plateau mountains[J].Environmental Monitoring & Assessment,2014,32 (10) :133 -136.]   
[28］高华喜,殷坤龙.基于GIS 的滑坡灾害风险空间预测[J].自然 灾害学报,2011,20（1）:31-36.[GAO Huaxi,YIN Kunlong. GIS-based spatial prediction of landslide hazard risk[J].Journal of Natural Disasters,2011,20(1） :31-36.]   
[29］陈华友,赵佳宝.模糊判断矩阵的相容性研究［J].运筹与管 理,2004,13（1）:44-47.[CHEN Huayou,ZHAO Jiabao.Research on compatibility of fuzzy judgement matrices[J]. Operations Research and Management Science,2004,13(1） :44 -47.]   
[30］孟广文,刘铭.天津滨海新区自由贸易区建立与评价[J].地理 学报,2011,66(2）:223-234.[MENG Guangwen,LIU Ming.Evaluation on theestablishment offreetrade zones in Tianjin Binhai New Area[J]. Acta Geographica Sinica,2011,66（2）: 223- 234.]   
[31］杜悦悦,彭建,赵士权,等.西南山地滑坡灾害生态风险评 价——以大理白族自治州为例[J].地理学报,2016,71（9）： 1544 -1561.[DU Yueyue,PENG Jian,ZHAO Shiquan,et al. Ecological risk assessment of landslide disasters in mountainous areas of southwest China:A case study in Dali Bai Autonomous Prefecture[J].Acta Geographica Sinica,2016,71(9）:1544-1561.]   
[32］郭芳芳,杨农,孟晖,等.地形起伏度和坡度分析在区域滑坡灾 害评价中的应用[J].中国地质,2008,35(1）:131-143.［GUO Fangfang,YANG Nong,MENG Hui,etal.Application of the relief amplitude and slope analysis to regional landslide hazard assessments[J].Geology in China,2008,35（1）:131-143.]   
[33]BROOTHAERTS N,KISS E,POESEN J,et al. Spatial paterns, causes and consequences of landslides in the Gilgel Gibe catchment,SW Ethiopia[J].Catena,2012,97(5）:127-136.   
[34］王秀英,聂高众,王登伟.汶川地震诱发滑坡与地震动峰值加 速度对应关系研究[J].岩石力学与工程学报,2010,29(1)：82 -89.[WANG Xiuying,NIE Gaozhong,WANG Dengwei. Research on relationship between landslides and peak ground accelerations induced by Wenchuan earthquake[J]. Chinese Journal of Rock Mechanics and Engineering,2010,29(1）:82-89.]   
[35］赫胜彬,张靓.基于夜间灯光数据的中国区域发展评价[J].生 态经济,2015,31(12）:14-17.[HE Shengbin,ZHANG Jing.Evaluation of China regional development based on DMSP-OLS data [J].Ecological Economy,2015,31(12）:14 -17.]   
[36]GHESHLAGHI H A,FEIZIZADEH B.An integrated approach of analytical network process and fuzzy based spatial decision making systems applied to landslide risk mapping[J]. Journal of African Earth Sciences,2017,133(9):15 -24.   
[37]CONFORTI M,PASCALE S,ROBUSTELLI G,et al.Evaluation of prediction capability of theartificial neural networks for mapping landslide susceptibility in the Turbolo river catchment（northern Calabria,Italy)[J].Catena,2014,113（1）:236-250.   
[38]RJIR P,SCHNEIDER L C.Land-cover change model validation by an ROC method for the Ipswich watershed,Massachusetts,USA [J].Agriculture Ecosystems & Environment,20o1,85（1）:239 - 248.

# Risk assessment of landslides along the Silk Road Economic Belt

IYan-qian12，QIU Hai-jun1,23，HU Sheng1²，YANG Dong-dong12，CAO Ming-ming'，ZOU Qiang (1College of Urban and Environmental Science,Northwest University,Xi'an 71O127,Shaanxi,China;   
2Instituteof Earth Surface Systemand Hazards,Northwest University，Xi'an71Ol27,Shaanxi,China;   
3Shaanxi KeyLaboratoryofEarthSurface SystemandEnvironmental Carring Capacity,Xi'an7o127,Shaanxi,China;   
4Key Laboratoryof Mountain Hazardsand Earth Surface Proces/InstituteofMountain Hazards and Environment,Chinese Academy of Sciences(CAS）,Chengdu 610o41,Sichuan,China)

Abstract：“The Belt and Road”Initiative is an open and inclusive international economic cooperation network with an expanding spatial scope that covers Asia,Europe,Africa,Oceania and other regions of the world.It involves more than half of the world's population and creates a great economic aggregation of $2 1 \times 1 0 ^ { 1 2 }$ USD. However,countries onthe“Belt and Road”located in the Mediteranean-Himalaya volcanic seismic belt and the volcanic seismic belt along the Pacific Rim sufer from strongest global movement and crustal activity.The natural environment inthe region is very diffrent considering the serious damagecaused bylandslide hazards.Inaddition,most of the countries and regions along the line are developing countries with underdeveloped economy which weakens their abilities to resist disasters.Dueto the serious threatens brought byfrequent landslide disasters to the lives and property of local people,which does a great harm onrestricting local social and economic development.Therefore,how to scientificall establish thedisaster prevention and mitigation mechanism or system isa critical issue theregion is facing hat needs tobeaddressed.Basedonthis,taking thecharacteristicsoflandslidedisaster,thedistribution lawand hazards inducing environment into account,this paper combines the slopeand topographic relief to extract the safety area of the study.Basedonthe safetyarea,theFAHP is used toconfirm therisk assessment model of the landslide risk and to calculate the comprehensive weight of each factor.The risk of landslide in the countries along“the Belt and Road”Initiative is quantitatively evaluated and the relevant data is verified.The results are expected to provide a scientificreferenceforthe prevention and controlof landslide disasters in countries and regions along the“Belt and Road”Initiative.Firstly,the safety area is mainly located in the plain,basin and desert,etc.Only $4 . 7 \%$ （56）landslide fall within the safety area,which means the resultsare reasonable.Secondly,the conditions that are likely to induce landslides are : slopes between $2 5 ^ { \circ }$ and $4 5 ^ { \circ }$ ,topographic relief more than $9 0 0 \mathrm { ~ m ~ }$ ,distance from the river less than $5 0 0 \mathrm { ~ m ~ }$ ,average annual rainfall between $4 0 0 ~ \mathrm { { m m } }$ and $8 0 0 ~ \mathrm { { m m } }$ ,seismic density is $3 \times 1 0 ^ { - 4 } - 2 \times 1 0 ^ { - 3 }$ per $\mathrm { k m } ^ { 2 }$ ， the engineering geology rock masses being medium hard rocks or soft rocks or soil mass.In the non-safe area,landslides are mainly at medium and low hazard levels $( 8 0 . 3 \%$ ）,and the very high,high hazard areas are mainly distributed among plateau,mountainous landand hils,in which the topographicrelief and the densityof the earthquakearelargerandrocksare softer.The AUC valueof hazard is O.823.Thirdly,theconditions when the landslides are likely to create potential damage include the population density of $8 0 \sim 1 6 0$ person per $\mathrm { k m } ^ { 2 }$ ,road density of $0 . 2 \sim 0 . 9 \ \mathrm { k m } \ \mathrm { p e r } \ \mathrm { k m } ^ { 2 }$ and night light index of $2 0 \sim 6 0 .$ . In non-safe area,the potential damage of landslide disasters is generally lower.The high,very high damage areas are mainly distributed in China （Southeastern Hily Region, Taiwan,Southwest Mountain Area,Qinba Mountainand Loess Plateau）,north of Southeast Asia,South Asia,the northwest of West Asia,southwest of Europe and some countries in Africa where the population density is large,economic condition is well,and the highway facilities are welldeveloped.The resultsof the damage assssment are consistent with the spatial distributionofeconomic lossanddeath toll caused bythe landslide.Finaly,in thenon-safe area,the proportions are $4 4 . 7 \%$ ， $2 5 . 5 \%$ ， $1 5 . 3 \%$ ， $1 0 . 3 \%$ and $4 . 2 \%$ respectively for the five risk zones,namely theextremelylow risk zone,low risk zone,medium risk zone,high risk zoneand extremely high risk zone.Therefore,it is dominated by the extremely low risk zone and low risk zone（with a sum of $7 0 . 2 \%$ ).In summary,the results of risk classification oflandslide disaster evaluated in this paper are scientific and reasonable,which can provide a scientific reference for the prevention and control of landslide disasters in countries and regions along“the Belt and Road”Initiative.

Key Words:landslide；safe zone；FAHP；risk assessment；the Silk Road Economic Belt