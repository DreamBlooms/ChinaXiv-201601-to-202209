# DOI: 10.5846/stxb201607221487

齐建超,刘慧平,伊尧国.应用自组织映射方法的北京市2005—2013年土地利用时空演变分析.生态学报,2017,37（19)：6346-6354.QiJC,Lidal(19):6346-6354.

# 应用自组织映射方法的北京市2005一2013年土地利用时空演变分析

齐建超1,2,3，刘慧平1,2,3，\*，伊尧国1,2,3,4

1遥感科学国家重点实验室，北京100875  
2环境遥感与数字城市北京市重点实验室，北京100875  
3北京师范大学地理学与遥感科学学院，北京100875  
4天津城建大学地质与测绘学院，天津300384

摘要;时间序列土地利用时空演变规律分析是当前的研究热点之一,通过应用自组织映射神经网络方法进行多时间序列土地利用变化时空一体化表达与演变规律分析,探索区域土地利用变化模式。基于北京市 2005、2007、2009、2011、2013年5期土地利用遥感分类数据,构建自组织映射神经网络并利用其聚类和降维可视化功能对5个年份的土地利用数据同时进行训练输出,发现建设用地、耕地、林地、牧草地、园地的聚集模式，并通过对输出神经元进行二次聚类以及土地利用变化轨迹分析,获得北京市郊区5个监测时相土地利用变化的时空演变特征。结果揭示出北京市郊区2005—2013年土地利用变化具有明显的耕地型向建设用地型发展的平原区演变特征，以及向林地型发展的山区演变特征，且各区的发展具有时间上的顺序性；总体上形成6类土地利用演变轨迹。

关键词：自组织映射(SOM);土地利用变化;多时间序列;时空分析;轨迹分析

# Land use spatial-temporal evolution analysis using a self-organizing map in Beijing，2005—2013

QI Jianchao1,2.3，LIU Huiping1,2,3\*，YIYaoguo1,2,34

1 State Key Laboratory of Remote Sensing Science,Beijing Normal University，Beijing 10o875,China   
2BeijingKeyLaboratoryofEnvironmentalRemoteSensingandDigitalCity，BeijingNormalUniversity，BeijingOo875,China   
3School ofGeography andRS,BeijingNormal University，Beijing1Oo875,China   
4School of Geologyand Geomatics，Tianjin Chengjian University，Tianjin 30o384，China

Abstract:Multiple timeseries land usingspatial-temporal evolutionanalysis isanimportant researcharea.In this study, we investigated the spatial-temporal integrated expression of multiple time series landuse change.A self-organizing map (SOM）neural network wasused to explore regional land usechange modes and to analyze what has driven these changes. Remote sensing data for five land use classification data periods（2005，2007，2009，2011，and2013）for Beijing were usedto train the network，andtheoutputsidentified theaggregation modes forbuilding land，farmland，forest land, grasland，and gardens byusing the clustering，dimension-reducing，and visual functions ofthe SOM.Then weconducted second-step clustering to produce the neuronand buildthe landusechange trajectories thatareneeded to analyze he spatial-temporal features of Beijing suburban land usechanges during thefive monitoring periods.Theresults revealed hat there were two land usechanges intheBeijing suburbs between 2Oo5and2013.One wasthedevelopment of buildings on farmland locatedon the plainsandthe other was the development of forest land in mountainousareas.Furthermore, development in each district had its own time sequences.This meant that we eventually obtained six land use change trajectories in total.

Key Words:self-organizing map(SOM）；land use change；multiple time series；spatial-temporal analysis；trajectory analysis

土地利用的时空演变是指各种土地利用类型的空间分布随时间的变化,随着时间序列数据的增加,其演变分析的难度和复杂度也在增加,而常用来分析高维时空数据的自组织映射方法可同时处理多时间序列数据,为多时间序列土地利用时空演变规律与发展模式分析提供便捷,为土地利用空间布局的合理优化提供支持。

当前关于土地利用变化的研究已取得了很多成果,杨国安等[1]运用分形模型通过对比两个时期北京市各土地利用类型的分数维及不稳定指数来研究北京市土地利用的空间格局变化;侍昊等[2]、Long Hualou等[3」、FanQ等[4]均是基于多期数据相邻两期的两两对比的方式,通过计算土地利用变化动态度、转移矩阵等方法来定量的分析说明土地利用变化状况;Liu H等[5]、黄勇等[6]容芳芳等[]运用变化轨迹分析方法研究土地利用空间格局的变化规律。土地利用变化的时空分析包括时间和空间两个方面,当前的研究虽然多是从时空角度来分析,但对二者的结合并不是很完善,针对空间研究其分布模式,针对时间多以时间切片的形式进行分析。当前对于土地利用空间分布模式的研究已比较成熟,而对于时间序列数据的处理多是基于单期或两期数据之间的比较,对于超过两个监测时相的多时间序列土地利用变化数据的时空一体化表达和对比分析还有待于更进一步地深人研究。同时当前土地利用变化轨迹多采用图谱的表达方法，即用轨迹代码的方式来表示一种地类向另一种地类的变化,这种表达方式难以直接对轨迹进行定量的分析和可视化表达。

自组织映射(SOM)是一种采用非监督式学习对输人样本数据进行训练,并将输入空间的高维数据在低维(通常是二维)进行离散化表示的人工神经网络。该理论最早是由芬兰赫尔辛基理工大学Kohonen[8]于1982 年提出的,自组织映射方法与其他人工神经网络方法的不同之处在于它使用了一个邻近函数来保持输入空间的拓扑性质,从而可以直接在其输出面板上进行二次聚类以及轨迹构建。SOM作为一种神经网络聚类算法常被用来探索空间对象的聚集模式[9-i1];另外 SOM作为一种降维和可视化的工具也常被用来表达和分析识别潜在的模式[2-15]。在当前研究中,SOM 的聚类和可视化的双重功能多是结合起来运用,并常被各领域用来分析处理高维时空数据,比如 SOM已被广泛的应用于社会经济变化[16-18]、流行病[19]、犯罪[20]、航线[21]气象[2]等领域的时空演变和轨迹分析以及可视化研究中。但到目前为止,将 SOM方法应用到土地利用时空演变分析中的研究还比较缺乏。国外像Aribas-Bel等[23-24]已开始尝试运用 SOM方法来研究城市扩张及城市的空间结构,而国内焦利民等[25]也开始尝试运用 SOM方法来对中国主要城市的扩展特征进行对比分析,但还处在较为初级的阶段,多是利用SOM输出面板来表达能反映城市扩展特征的各指标的分布聚集状况和差异,而对于多时间序列数据的对比以及变化轨迹的分析和表达还需要更进一步的深入研究。

本文基于北京市 2005、2007、2009、2011、2013 年5期土地利用数据,运用 SOM 的神经网络聚类功能将 5个时间序列数据同时输入网络进行训练,得到不同时间序列数据在时间和空间上具有可对比性的输出聚类结果,并将此结果在SOM输出面板以及地理空间中进行可视化表达与对比分析,并借助 SOM的拓扑保持特性在其输出面板上构建变化轨迹，从而可以直接定量的分析和直观的表达轨迹的变化方向。因此本研究通过应用SOM方法为多时间序列土地利用变化的时空一体化表达和对比分析提供了一种新的尝试和探索视角，并基于此来深入分析和揭示北京市郊区2005—2013年间各区土地利用变化的时空模式和发展规律。

# 1研究区与研究数据

本文研究区为北京市郊区的14个区,包括朝阳区、海淀区、丰台区、石景山区、顺义区、通州区、大兴区、房山区、昌平区、门头沟区、怀柔区、密云区、延庆区、平谷区。研究数据为北京市 2005、2007、2009、2011、2013 年5期由 SPOT遥感影像解译获得的土地利用分类数据（图1），其中除2005年采用 SPOT4全色波段影像和多光谱波段影像的融合结果作为数据源,其余均是以SPOT5多光谱波段影像为数据源,空间分辨率为 $1 0 \mathrm { m }$ ，分类精度均在 $8 2 \%$ 以上。研究数据来自课题组20 年来承担的北京市农村经济研究中心的长期土地利用监测项目,考虑到遥感数据源的一致性以及从2005年开始的精细监测,本文选用2005年以后的5个监测时相进行研究。由于长期土地利用监测项目的连续性、一致性,土地利用分类标准采用1984年全国农业区划委员会制定的《土地利用现状调查技术规程》中的8大类,结合遥感数据分类特点最终将地类划分为7类;建设用地（将居民点及工矿用地、交通用地合并称作建设用地）、耕地、林地、牧草地、园地、水域和未利用土地。

![](images/ea69296223cb5c5bd1dbe72c907572457bd3234d263d61b6a50c033d42ed9e8d.jpg)  
图1北京市2005—2013年土地利用分类数据Fig.1Land use classification data of Beijing，2oo5-2013

# 2研究方法

本文的总体技术流程如图2所示,主要包括 SOM的网络构建、二次聚类以及土地利用变化轨迹分析等方面的工作。

# 2.1 SOM方法

SOM的网络是一个两层网络，由输入层与输出层(又称竞争层)构成,其中输入层用于接收输入的训练样本,而输出层的神经元一般是按照二维阵列排列,两层各个神经元之间实现双向连接,SOM网络通过寻找最优的权值向量即最佳匹配神经元来对输入模式集合进行分类。SOM算法的步骤为：初始化各权值向量,即对

http://www.ecologica.cn

输出层各权值向量赋小随机数并进行归一化；寻找输入数据的获胜神经元；调整优胜邻域内的权值向量；重复寻找输入数据的获胜神经元及以后的步骤，直到迭代终止条件被满足。

实验中SOM算法是基于Matlab编程实现，对于SOM输出面板尺寸参数的确定，由于需要对变化的轨迹进行绘制和可视化，所以将SOM输出面板的尺寸设置的足够大，从而尽量使得每一个输入节点在输出的面板空间中都有只对应于它的单一获胜节点。本文的输入数据为北京市5个年份14个区的7种地类属性即输入数据共有 $5 \mathrm { a } \times 1 4$ 区 $= 7 0$ 条，结合前人研究经验及多次实验，设置SOM输出面板的尺寸为 $2 0 \times 2 0 = 4 0 0$ ,即输出有400个神经元，要远大于输入的节点数，SOM的网络训练迭代次数设置为10000次，以保证训练结果的稳定，从而获得各特征变量的成分平面图以及最佳匹配神经元的位置。

# 2.1.1 SOM输出成分平面图

![](images/9ad09092eb6c0eba9024cc8e26aeae5d1e4412586e98ee0ea69aa205900dcdb7.jpg)  
图2总体技术流程图  
Fig.2Overal flow chart of this study

量,将这7种地类属性看作是7个特征变量,经过网络训练后,输出神经元的权值向量即为此7种特征变量构成。根据各输出神经元的位置对每一特征变量的值进行显示,得到各特征变量的成分平面图,可直观的发现各特征变量值的聚集状况。 A

图3所示为经过网络训练后在SOM输出面板上7个地类属性各自的分布与聚集状况,每张图代表一种地类,颜色越深表示该地类的比例越高、越集中。可以发现在SOM输出面板上建设用地、耕地、林地、牧草地、园地的分布比较聚集,而水域和未利用土地的分布比较杂乱。其中建设用地比例的高值聚集在 SOM 输出面板的右上角（图3a）,耕地比例的高值聚集在左上角（图3b),林地比例的高值聚集于右下角（图3c）,牧草地比例高值聚集于左下角(图3d),而园地比例的高值聚集在左边（图3e)。由此可以看出经过 SOM网络训练后的输入数据在输入空间中的模式在输出空间中得以识别和表达。

# 2.1.2最佳匹配神经元

通过计算欧氏距离寻找距输入数据最近的输出神经元作为其最佳匹配神经元,根据输入数据在 SOM 输出面板上最佳匹配神经元的位置,将各年份输入数据在输出面板上进行表示(图4)。结合图3中的成分平面图进行对比分析,可以从整体上发现在本研究的所有时相内朝阳区、海淀区、石景山区、丰台区主要聚集在建设用地比例较高的区域,大兴区、通州区、顺义区一般聚集在耕地比例较高的区域,延庆区、密云区、怀柔区、门头沟区等主要聚集在林地比例较高的区域，而平谷区主要在园地比例相对较高的区域。

# 2.2 二次聚类

将输出的400 个神经元,按其权值向量进行二次聚类,二次聚类采用 $\mathbf { k }$ -means算法，经多次试验确定聚类为7类时具有很好的解释性,并将其分别在 SOM输出空间以及地理空间中进行可视化。图5中 SOM 输出面板的区域划分代表着二次聚类的结果;图6中的折线图表示每个聚类结果的7个属性值,也即7种地类的面积比例,根据该比例确定各聚类的土地利用结构类型,其中林地过渡型I和Ⅱ表示其林地比例相对于林地型为低,但仍占主要优势比例,林地过渡型Ⅱ中建设用地及耕地也占有不小的比例;图7是分别将5个年份的聚类结果在地理空间上进行可视化,并以多图的形式来表现不同年份之间的变化。由于是将不同年份各区域的土地利用数据同时作为输入数据进行网络训练,所以在输出的结果中,不同时期、不同区域的聚类结果具有可对比性。在图5、图6、图7中所表示的内容均对应着共同的7个聚类,以便于进行时空对比分析。如图6所示,各聚类的差异主要表现在建设用地、耕地、林地方面的差异,其次是牧草地和园地,水域和未利用土地的贡献较小。

![](images/05cb904107b0f5f63f43f4df3e77b097cf40a5a551e5aa7ca5d08a403f91f46f.jpg)  
图3SOM输出成分平面图  
Fig.3Output component planes of SOM

# 2.3轨迹分析

根据不同时期各区输入数据的最佳匹配神经元在SOM输出面板中的位置,将各区在不同时期对应的输出点位依次连接起来,从而在低维空间即SOM输出面板上构建各区的土地利用变化轨迹,并对变化轨迹进行聚类分析,此时将每个区的各个年份的土地利用结构比例数据按照时间顺序依次排列组成一个向量,以此来表示该区的变化轨迹并将其作为轨迹聚类的数据输入。根据轨迹聚类结果研究区域土地利用的发展模式，同时将其在SOM输出空间及地理空间上进行可视化。

http://www.ecologica.cn

# 3北京市土地利用时空演变分析

土地利用时空演变分析包括空间和时间两个方面，土地利用空间聚集模式可以通过结合SOM输出面板中各地类属性的聚集状况和各年份输入数据最佳匹配神经元的位置来表达说明；而根据输出神经元二次聚类结果可获取各年份的土地利用空间分布模式，并通过多时间序列数据的对比以及变化轨迹的构建、分析与可视化来说明土地利用的时空变化模式。

# 3.1土地利用空间聚集模式

首先结合最佳匹配神经元的位置以及SOM输出成分平面图中各地类属性值的分布，可以直观地发现不同年份各区的聚集状况，见2.1.2节。根据二次聚类结果可以定量的确定各年份不同区土地利用结构的相似聚集情况，如图7。可以发现在本研究时段内，北京市郊区主要向两个方向发展，一是东南平原地区向建设用地型的发展模式,表现为耕地型聚类的减少及建设用地/耕地型聚类的增加；一是西北山区向林地型的发展模式，表现为林地过渡型Ⅱ聚类的减少及林地型聚类的增加。

# 3.2土地利用时空变化模式

# 3.2.1 空间模式演变分析

(1)东南平原地区向建设用地型发展模式。由图7可以看出顺义区、通州区、大兴区由2005年和2007年的耕地型转变为建设用地/耕地型,其中顺义区转变较早（2009年），通州区和大兴区转变较晚(2013年）。该转变主要是耕地比例的减少以及建设用地、林地及牧草地的增加，这说明顺义区、通州区、大兴区具有作为城市发展新区的特征。平原区的朝阳区、丰台区始终属于建设用地型，位于山区过渡带的海淀区、石景山区始终属于建设用地过渡型，该类型的林地比例明显要高。

通州区 通州区 丰台区 朝阳区朝阳区丰台区枢 通州区 新 返★十+ 真 期阳 石景山区海淀区  
顺来区 顺来 石景山区众 ☆订 驱 海 景山区学 名  
顺来区 海深 E高 景山区☆ ★ 會 区 房山区 L Q区 房中区 ★ 区 O平谷区 房山区房  
平谷 B 来 密云区★ 中 + +区 密区  
中 密 中 快沟区2005年★2007年2009年●2011年2013年

![](images/753d2856816fbc81c93de59b99a6faaa2648237b84848157bde37bb7e8199a64.jpg)  
图4SOM最佳匹配神经元  
Fig.4Best matching unit of SOM   
图5二次聚类 SOM面板区域划分  
Fig. 5 Regional division of SOM output plane by secondstep clustering

(2)西北山区向林地型发展模式。由图7可以看出房山区、昌平区、平谷区由 2005 年的林地过渡型Ⅱ转变为林地过渡型I,延庆区、密云区由 2005 年的林地过渡型I转变为林地型,怀柔区、门头沟区始终属于林地型。该转变主要是林地用地比例的逐渐增加,而耕地等其他地类的比例有所减少,说明这5个区均具有以林地增长为主导的土地利用变化趋势。

总的来说,从2005年到 2013年,平谷区、房山区、昌平区、延庆区和密云区的土地利用变化表现为从林地过渡型Ⅱ到林地过渡型I再到林地型的变化模式,顺义区、通州区、大兴区的土地利用变化表现为从耕地型向建设用地/耕地型的变化模式,而怀柔区、门头沟区始终属于林地型,海淀区、石景山区始终属于建设用地过渡型,朝阳区、丰台区始终属于建设用地型。

# 3.2.2 土地利用变化轨迹

对于14个区所对应的14条轨迹线,通过聚类来分析轨迹方向的相似性,本文采用 $\mathbf { k }$ -means算法经多次试验确定将14条轨迹聚为6类时具有很好的解释性，分别是朝阳区、丰台区为一类,海淀区、石景山区为一类，顺义区、通州区、大兴区为一类，昌平区、房山区为一类，平谷区为一类，怀柔区、门头沟区、延庆区、密云区为一类。各个区的土地利用变化轨迹如图8所示，其中左图轨迹线的颜色与右图各区的颜色一一对应，即相同的颜色表示相同的轨迹聚类。

根据图8左图的轨迹聚类图可以发现朝阳区、丰台区、海淀区、石景山区的变化轨迹均有向SOM输出面板右上角的延伸趋势,说明该区域更趋向于高建设用地比例的土地利用格局发展，即更趋向于中心城区发展；顺义区、通州区、大兴区趋向于向朝阳区、丰台区、海淀区、石景山区的方向发展并紧随其后,表现为向建设用地型发展的过渡阶段;怀柔区、门头沟区、延庆区、密云区的变化轨迹均有向 SOM输出面板右下角的延伸趋势,说明这些区域更趋向于向林地比例高的土地利用格局发展,即更倾向于向生态涵养功能的发展;昌平区和房山区的轨迹方向介于海淀区、石景山区与密云区、延庆区等之间,而平谷区则始终在园地用地比例较高的区域徘徊。结合图5所示二次聚类结果的SOM面板,可更加直观地揭示各区的土地利用变化模式。而且轨迹线不仅可以表现二次聚类类别间的变化,还可以表现某一类别中的变化,像朝阳区、丰台区在建设用地型中仍然向着建设用地比例更高的方向发展。

![](images/b3d1aa8324b00d4278f166c52bcf6f4d3154c72ebcfd8f064096203641d0abd0.jpg)  
图6二次聚类结果的土地利用类型比例

![](images/13223fe9c6ddd2d9205ad8a1ee3c8805556805a554bec138c850126e0fa14fb1.jpg)  
Fig.6Percent of different land use type in second-step clustering result   
图7不同年份的聚类结果在地理空间中的可视化  
Fig.7Geospatial visualization of clusteringresult in different years

![](images/4988787698e5e10d5c57741de58fe7f06abd4568c5c5e2788d60019d39d1c8ed.jpg)  
图8土地利用变化轨迹与可视化  
Fig.8Land use change trajectories and visualization

# 4总结与讨论

SOM方法是一种非常有效的可视化数据挖掘方法,可将高维数据映射到二维的平面上,从而更加直观的表现和识别潜在的模式。本研究运用 SOM方法来探索分析北京市区级土地利用的时空演变模式,通过设置足够大尺寸的 SOM输出面板,借助 SOM的拓扑保持特性将多时间序列数据同时输人SOM 网络进行训练输出,从而实现土地利用变化的时空一体化表达和对比分析,为当前土地利用变化研究中存在的对多期数据处理多是基于单期或相邻两期两两对比[-4]的问题提供了一种新的解决思路。

聚类与轨迹分析结果与2006年出台的北京市"十一五"功能区域发展规划基本一致,通过对 SOM输出神经元进行二次聚类及在其输出面板上构建的土地利用变化轨迹，可以发现一些更为精细的结果,像朝阳区、丰台区、海淀区、石景山区均为城市功能拓展区,但相比与海淀区和石景山区,朝阳区和丰台区更趋近于中心城区的发展;此外,房山区与昌平区虽然被规划为城市发展新区,当前仍以林地为主导用地类型,且林地的用地比例有一定的增长趋势,但从轨迹方向上来看也有一定的朝海淀区与石景山区的发展趋势;而对于顺义区、通州区和大兴区,在其区域发展过程中顺义区的转变发生较早。综上可知,北京市在2005—2013 年间土地利用变化的特点主要表现为建设用地和林地的逐年增长以及耕地的逐年减少,说明了城市在向外扩展过程中各地类之间此消彼长的结构变化关系及建设用地对农用地的侵占状况。因此运用本方法可以很好的发现区域土地利用变化的时空模式,同时也为更多时间序列的土地利用变化数据的时空一体化表达和对比分析提供了一种可供选择的更加直观便捷的探索方法。

本研究的输人数据为70条,设置的输出神经元个数为400个,但当研究区域更大或者对输人的空间单元尺度划分更细时,输入数据的数量会大大增加,此时输出神经元的数量也需要相应增多,也即需要更大的SOM 输出面板的尺寸,这样 SOM 网络训练过程中的计算量就会大大增加,这就需要考虑 SOM 的算法效率问题。

# 参考文献（References）:

[1］杨国安，甘国辉.基于分形理论的北京市土地利用空间格局变化研究.系统工程理论与实践，2004,24（10)：131-137.[2］侍昊，薛建辉，马婉丽.1991—2006年无锡市土地利用变化动态度及转换参数分析.南京林业大学学报：自然科学版，2012，36（6)：63-68.[3]LngHangGiX,HeliGKoiocoicdrigrsofdusehageiuathgtziveaocf

http://www.ecologica.cn

China.Journal of Environmental Management，2007,83(3）：351-364.  
[4]FanQD,DingS.Landscapepatechangesatacountyscale：acasestudyFengqu,HenanProvince,Chinafrom19to2.Catena,2016，137：152-160.  
[5] LiuHP,ZhouQM.Developingrbangrowthpredictiosfromspatialindicatorsasednulti-mporalimages.Computers，EnviotadUrban Systems，2005，29(5）:580-594.  
[6] 黄勇，王凤友，蔡体久，汪东川，王倩倩，陈文刚.环渤海地区景观格局动态变化轨迹分析.水土保持学报，2015,29（2)：314-319.  
[7] 容芳芳，塔西甫拉提·特依拜，田源，张飞.于田绿洲土地利用/覆盖变化轨迹分析.水土保持研究，2010,17（3)：259-263.  
[8] Kohonen T.Self-organized formationof topologicallycorrct feature maps.Biological Cybernetics，1982,43（1）：59-69.  
[9] 焦利民，刘耀林，任周桥.基于自组织神经网络的空间点群聚类及其应用分析.武汉大学学报：信息科学版，2008，32（2)：168-171.  
[10] 焦利民，洪晓峰，刘耀林.空间和属性双重约束下的自组织空间聚类研究.武汉大学学报：信息科学版，2011,36(7)：862-866.  
[11] GhaseminezhadMH,KaraiAAoveseforganingap（SO）euraletorkfordiscretegroupsofdatacusteingAliedSftuting，2011,11(4):3771-3778.  
[12] Ren JH,ChenJC,Wang N.Visualanalysisof SOM network in fault diagnosis.Physics Procedia,2011,22：333-338.  
[13] LambPF,MndA,retRobsVisualigagesilowrdyodatioitenttysofftosuingel-organizing maps（SOM).Gait & Posture，2011,34(4）：485-489.  
[14] VariniC，DegenardA，NatkemperTW.VisualexploratoryanalysisofDCE-RIdatainbreastcancerbydimensioaldatareduction：acomparative study.Biomedical Signal Processing and Control,2OO6,1(1）：56-63.  
[15] 廖广兰，李巍华，史铁林，陈勇辉.基于自组织映射的齿轮箱状态监测可视化研究.机械工程学报，2003，39（12)：99-102.  
[16] ChenN，RibeiroB，VieiraA，ChenA.ClusteringandVisualiationofbankruptcytrajectoryusingself-organiingmap.ExpertSystesithApplications，2013，40(1）：385-393.  
[17] LeeACD,RinerC.Visualizingurbansocialchangewithseforganingmaps：Trontoneigbouods，996-2O6.HabitatInteatioal,2015,45:92-98.  
[18] SkupinA，HagelmanR.Visualizingdemographic trajectories withself-organizingmaps.Geolnformatica,2Oo5,9（2）：159-179.  
[19] AugustijnE，uria-illSeforgaapsrochtxligspatiopaldiusioatsteaoalJoaalGeographics，2013，12:60-60.  
[20]Andrdercceoexploring spatiotemporal patterns.Computer Graphics Forum,2010,29(3）:913-922.  
[21]YaJilJVisualatangisatialeacsifogagapsvtdanga&i,2009，36(3):466-486.  
[2]HuvaRgvlacofgoasyiralapreureiflllJournal of Climatology，2015，35(4）：624-633.  
2]rraselD,aHultisialbasprluro：efoagaoacouters，tUrban Systems，2011,35(4):263-275.  
[24] Arribas-elD，SchmidtCRSelf-oganingmapsandteUSurbanspatialtructurenviroentandPaingB-Plaing&Desig01,4(2):362-371.0  
[25] 焦利民，吴苏.利用自组织网络分析190—2010年中国主要城市扩展特征.武汉大学学报：信息科学版，2014，39（12）：1435-1440,1471-1471.