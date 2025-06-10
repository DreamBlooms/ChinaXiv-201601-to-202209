# 1 图像信息技术在奶牛生产中的应用

2 孙雨坤李文茜 幺恩悦刘鑫 李 洋张永根\*(东北农业大学动物科学技术学院，哈尔滨 150030)

4摘要：奶牛养殖的高成本和低效率阻碍着国内奶业发展，图像信息技术可以帮助生产管理  
5 者更加客观、有效地评价奶牛健康状况和生产需要，减少动物应激，提高牧场智能化管理水  
6 平。本文综述了可见光相机、热成像相机和深度相机的成像原理，评价了奶牛生产中图像信  
7 息技术的应用方法和效果，整理了图像可视系统在体重测定、体况评分、动物体温监测、步  
8 态评分、采食量测定、卧床行为监测等项目中的研究进展，探讨可视系统在准确率、灵敏度、误差等方面的表现。该技术可以应用于牧场管理者对畜群的日常观察，为日后牧场全自动化建设做准备。

关键词：奶牛;图像信息技术;生产管理;应用中图分类号：S823

高成本、低效率是我国奶业竞争力不足的原因之一，国内奶牛生产平均饲料转化率为1.2，发达国家可以达到1.5，提高生产效率需要通过科学精细的管理方式[1-2]。发达国家更加关注动物福利在动物生产中的作用，考察的指标包括动物行为、生理状态、健康指标和生产性能[3]。准确、及时地反映畜群的生产状态有助于降低生产成本，提高饲料转化率，减少牛群发病率[4]。传统观察畜群方式是依靠经验丰富的养殖人员，以肉眼观察和触摸的方法对动物个体状态进行相应判断，为了克服传统方式中主观判断产生的误差，以及动物应激状态中行为的不确定性，在过去几十年里科学工作者通过不断改进图像信息技术，可以得到更加客观真实的数据资料。近些年，奶牛牧场中安装多功能照相机记录牧场全景图像，作用在于评测动物采食和行为活动，获得行为指数，有利于实时观测行为变化，确定奶牛生产体况，其灵敏度可以达到 $8 7 \% ^ { [ 5 ] }$ 。高灵敏度证明畜牧生产者可以更多考虑图像技术在生产管理中的应用，不仅费用较低，并且能够观察动物在自然状态下的生产情况，其数字化信息将给予管理者更加客观实时的生产数据和分析结果。本文探讨了图像信息技术的基本原理，列举生产管理与图像信息结合的试验方法和结果，提出对国内相关研究的看法和建议。

收稿日期：2017-11-03  
基金项目：国家奶牛产业技术体系(CARS-36)  
作者简介：孙雨坤(1991—)，男，内蒙古呼和浩特人，博士研究生，从事反刍动物营养研究。$\mathrm { E ^ { - } }$ mail: sun_yukun@126.com  
\*通信作者：张永根，教授，博士生导师，E-mail: zhangyonggen@sina.com

1照相机分类

动物图像检测和图像分类是图像识别的2个核心问题，当动物通过特定地点时系统会自动识别个体信息并进行拍照，图像会传入电脑，通过不同模型算法提取特征进行图像分类，最后确定识别结果(图1)[]。图像识别是图像信息数字化的第1步，而不同目的需要选用各自适合的相机进行图像采集。综合近些年的文献资料，在反刍动物生产中主要选用3种相机：

可见光相机、热成像相机和深度相机。

![](images/ab0ab9cf0255ed8f5d21ad213ac8d588af675975f498368cc6dcf0ee364da49a.jpg)  
图1照相装置示意图  
Fig.1Schematic overview of the photographing setup[6]

1.1可见光相机

可见光相机属于双维度型照相机，通过吸收可见光波长，以及日光照射使物体成像[7]，比如常见的监控摄像头。利用此类相机观察动物日常生产的例子较为常见，如在牧场内安装照相机，同时观察动物行为以及养殖人员的操作规范。在试验中可以根据不同颜色、形状和结构特点，从收集到的图像中选择适当的图片，再加上相应的算法就可以提取图像特征并量化其结果[5]。可见光相机能够提取目标物体的三原色(红、蓝、绿)，不同的图像处理可以将三原色信息转换成为灰度、色调、饱和度还有其他参数信息。在反刍动物生产中利用可见光相机可以对动物体重、体况评分、卧床率和跛行等进行观测[8]。

# 1.2热成像相机

热成像相机与可见光相机的成像原理类似，是将镜头的能量聚集在一系列感受器上产生图像(图2)。热成像相机通过接收和测量被测物体的热辐射来获得有效信息，其图像属于强度图像，每一个像素的强度值与摄入到光感电子元器件的热能有关，目标动物发出红外辐射，其温度越高，发射强度越高，则图像亮度更强。可见光相机的波长较短 $( 0 . 3 2 { \sim } 1 . 3 0 \mu \mathrm { m } )$ 而热成像相机可以探测到目标物体的波长为 $3 { \sim } 1 4 ~ { \mu } \mathrm { m } ^ { \left[ 9 \right] }$ 。热成像相机已经广泛应用于工业、农业、军事等领域，在牧场中用作评价动物能量需求、疾病健康监测以及动物日常行为观察。

但是最初报道表明，热成像相机的图像特征与肉牛脂肪和背膘厚的相关性较低(相关系数为0.47），因为视频中对有效画面的选择是手动的，而最新研究证明，在全自动热成像记录仪中，其相关系数达到 $0 . 9 4 ^ { [ 1 0 ] }$ 。

![](images/3a7bee0dee9430c865f7168a9d632c407f2459309be06ce60afc995c2d97ec7d.jpg)  
图2热成像相机成像原理

1.3 深度相机

得益于科技的日新月异，深度相机技术在过去十年得到了飞速发展，并普及于日常生活中。深度相机是许多可视系统的核心部件，比如飞行时间技术(TOF)和体感相机。TOF 是传感器发出经调制的近红外光，遇物体后反射，传感器通过计算光线发射和反射时间差或相位差，换算被拍摄景物的距离，以此产生深度信息(图3)，此外再结合传统的相机拍摄，就能将物体的三维轮廓以不同颜色代表不同距离的地形图方式呈现出来[1]。深度相机可以克服许多可见光相机与热成像相机的系统性缺陷，比如背景移除功能的缺失、无法自动提取有效特征、或者对光线的亮度都可能影响最后的结果。但是TOF 相机也会受限于截取视频的时间长度、图像中数据点的数量以及相对有限的视野。基于TOF 发展而来的体感相机，不需要进行校准就可以通过与软件相结合实时建立图像模型[12]。与二维图像相比深度图像信息可以获得三维立体信息，二维图像在提取信息时还需要获得特征点位，而体感相机则并不需要标记过多的特征点就可以实时获取图像的关键信息[13]。深度相机虽然对色彩分辨并不敏感，但是由于能够充分捕捉目标物体形状的细节，所以在奶牛生产中多用于以形状轮廓作为观察基础的技术指标，包括体况评分，体型外貌评分和跛行评分等。

![](images/078560badf60a6710a531059602b932607a1e477462a75b469bd5fef04dff9e7.jpg)  
Fig.2Imaging principle of thermal imaging camera[9]   
图3深度相机成像原理

# 2图像信息在生产中的应用

为了及时反映牧场中动物个体的体况，同时不影响畜群生产状态，牧场可以采用图像技术在群体中分辨出特殊情况的个体。在一些研究中动物体重、体况可以反映出不同的生理健康状况，利用图像采集技术推断出不同的生理指标用于指导生产。

# 2.1体重

动物体重是一项非常重要的生产指标，体重与其他生理和生产状态存在着密不可分的相关性，比如饲料转化率、动物采食的一致性、动物年龄、健康状况以及出栏需要等等。但是测定动物体重对工人来说是非常辛苦的工作，同时也会增大动物应激。图像采集技术早先在猪生产中应用较为广泛，从猪顶部位置获得图像信息，提取图像特征，包括面积、周长、偏心率、轴长和边界位置，之后进一步估测动物体重[14-15]。反刍动物可以通过顶部及侧面视角提取体况特征信息，比如臀部高度、体长、胸围，并结合多变量一般线性模型预测动物体重。Stajnko 等[16]利用近红外相机观测肉牛体重，通过侧面图像采集，可以准确从群体中捕获位于髋关节以后及其肩胛以下部分的个体特征，但是近红外相机与体重的相关系数变化范围较大，不同年龄段的相关系数从0.11到0.74 不等。Buranakarl等[17]对比了水牛体高、胸围、肩宽、髂骨宽、坐骨结节宽、体斜长等，采用立体照相机获取三维图像，通过计算得出该方法与动物体重的相关系数为0.81。而 Anglart[18]的试验中同样利用三维技术估测动物体重，在相机与体重的最高相关系数可以达到0.87。

# 2.2 体况评分

体况评分反映了奶牛对能量的利用情况，是反映动物生产力、动物健康状况和繁殖潜力的重要指标。通常情况下，牛场需要定期检查奶牛体况评分[19]，经验丰富的管理者通过眼观和触摸进行奶牛体况评分判定，其结果具有一定的主观性，而现在通过图像采集的方法可以客观、准确快速地评判体况。早先科研工作者利用可见光相机对畜群样本进行采样，需要手动确定奶牛体貌特征点(图4-A），之后将相机置于牛体止上方并捕捉画面确定样本特征位置，一般选用动物荐骨至臀部位置作为样本，其中尾根凹窝与臀部棱角是重要观测点(图4-B),当仅测定臀部棱角时，误差在0.50分范围内的体况评分估测值，准确率可以达到 $100 \%$ 误差在0.25分范围内的准确率可以达到 $9 2 . 7 9 \% ^ { [ 2 0 - 2 1 ] }$ 。但是该方法不能利用图像的全部信息，主要是通过提前设定特征位置，获取高清图像后提取相应位置信息并分析数据。

![](images/77eca781b7c08310d20f91f8456e9b74dd3da819be0c864eae2c80089c86b725.jpg)  
图4可见光相机拍摄图像及信息处理后的特征点位

Fig.4Image photographing by visible light camera and information processing feature points[20]

相比于可见光相机的部分信息处理方法，深度相机通过采集图像全部信息可以提高体况评分的准确率，因为该方法可以探测到动物体型的立体图像信息，对于形状(体型)的细微变化更加敏感。深度相机需要采集90\~120帧的图像，提取动物背部后段的相同区域图像，以确保被分析区域的一致性和相同的三维样本点数量，并选择最适公式进行校准。校准过程需要规范三维图像尺寸，将分析区域的三维表面进行叠加，找到一致的表面大小，所以排除了动物个体的形状尺寸变化对结果的影响。在确定的三维图像中建立坐标系，以荐骨连线为X轴，尾根中线为Y轴，X、Y轴的止交处为Z轴，以该坐标系为标准对图像进行校准(图5)[2-23]。Fischer 等[23]在比较了手动测定体况评分之后发现(标准误为0.210)，深度相机的方法更为准确(标准误为0.075)。在 Spoliansky 等[24]的结果中决定系数为0.75,标准差小于0.33，其试验利用简易的三维相机得到了较好的重复性，这一结果证明了深度相机可以广泛应用于大众牧场。

![](images/d7778d72ee2b48dd8f6ad1dc3d24e5dd1e7c03aa10350cedbe5bd39c8c3e6006.jpg)  
图5校准后的三维图像及其坐标轴  
Fig.5The calibrated 3D image and its axis[23]

# 2.3 健康状态

生产中及早发现动物疾病或异常行为可以有效提高动物生产效率，降低生产成本和动物死亡率。热成像技术可以直接探测动物体温，尽早发现个体表面温度的异常。比如，乳房炎是生产中的常见疾病之一，摄像头将捕捉到的乳房表面图像进行分析后可以判断其温度高低[25]。最近的研究发现，热成像照相机可以发现附着在牛体表面的寄生虫，比如虱子和苍蝇的虫卵在奶牛顶部的热图中会被发现[26]。虽然图像分析技术可以监测动物健康，但是通过体表温度观察动物健康还存在许多障碍，例如畜群体表的洁净程度、镜头与被测物体之间的距离等。

图像分析技术可以直观地发现现代牧场中奶牛的跛行，跛行加重了奶牛应激水平，反映了牧场管理的不足，严重影响了散养式牧场的生产效率。目前，牧场中应用跛行评分对奶牛跛行程度进行鉴定，评分标准为观察奶牛站立姿势和步态动作，由于蹄部疼痛奶牛会表现出站立不稳或在行进过程中出现步态异常的情况。为了分辨跛行步态，研究人员利用不同工具开发了自动跛行视觉系统。可见光相机可以预测并检验奶牛跛行，基于4个蹄部在图像中的不同距离，在不同方向上分离奶牛的四肢并确定中心点，标明前肢和后肢之后，预设水平方向和垂直方向上的坐标轴[27]。Pluk 等[6结合了压力传感器对奶牛荐骨位置的信息，电脑可以自动计算出行进中四肢起、落与地面的角度(图6)。利用可见光相机观察步态图像与跛行评分的相关系数达到了 $94 . 8 \%$ 。三维深度相机在监测奶牛跛行中也得到了较好的应用效果，Jabbar 等[14]的试验发现在深度相机对奶牛步态不对称的监测中，可以 $100 \%$ 监测到跛行牛，跛行评分准确率达到了 $9 5 \%$ 。该方法在获取图像后，系统自动删除背景，深度颜色的不同反映了背部不同位置的高度，经过一系列图像处理后，提取并匹配跛行特征数据信息(图 7)。

[38 该方法虽然对跛行牛的灵敏度为 $100 \%$ ，但是对正常牛群监测的误判达到了 $2 5 \%$ 。

![](images/72ea5cdf8bedbeb9147753145b5b387abe2236f55d83c97c1903fc858e8cde3b.jpg)  
图6图像检测及分析步态评分流程

![](images/3a52eab1a4b27a36e10d6aa7911e173181b73f1e6ac66208e933d22b1d18384a.jpg)  
Fig.6Image detection and analysis of gait scoring processes[6]   
图7图像检测及图像分类处理图  
Fig.7Image detection and image classification processing diagram[14]

2.4其他

反刍动物生产中的重要观测指标还包括采食、饮水、卧床等行为，这些观察内容反映了牧场对畜群的饲养管理水平以及动物福利水平，直接影响着产奶量、日增重等生产性能。对于动物采食量和饮水的检测，传统方式是牧场管理者仅依赖于日常观察判断动物的采食和饮水是否正常，凭借经验确定动物不同生长时期的给料量。图像分析技术可以帮助记录奶牛的采食行为，Porto 等[5]、Viola 等[28]把多功能照相机置于奶牛采食区域上方，并获取图像，利用Viola-Jones 算法将人脸图像识别技术用于计算奶牛采食量。在图像中只确定1头奶牛的的采食量，邻近的牛群将作为背景删除，该方法与传统方法相比，灵敏度为 $87 \%$

卧床率反映了卧床的舒适度和奶牛的健康程度，影响着牧场生产效率。Cangar 等[29]安装可见光相机置于卧床中心点顶部，根据动物背部几何图形建立坐标轴，计算背部面积和站立时的移动距离以区分站立和卧床行为，该方法的准确率为 $8 5 \%$ 。Porto 等[30]将可见光相机升级为全景相机，同样基于Viola-Jones 算法，可以使卧床观察准确率提升至 $92 \%$ 。Porto等[30]的方法对光照的要求并不高，无论日光照射还是灯光照射对其结果影响较小。

# ;83国内奶牛生产中对图像信息技术的应用

相较于国外成熟的牧场信息技术管理系统，我国图像信息技术在奶牛养殖中的应用尚处在起步阶段，相关研究还停留在实验室探索中。其主要研究方向包含了图像在遗传育种中体型外貌鉴定，体况评分选取和奶牛个体识别等几个方面，在不同试验中都得到了较好的试验效果。比如，黄君冉等[31基于Lab View 虚拟仪器软件开发平台和 IMAQVision 图像处理软件包开发了对奶牛体型外貌检测的图像识别软件，其准确率达到了 $90 \%$ ；类似的报道中，无论是二维或三维摄像头还是不同识别算法，在奶牛体型线性评定的图像提取特征中都有较好的应用前景[32-33]。另外，刘建飞[34]评价了图像信息技术在奶牛体况评分应用中的可行性，但是其准确率仅为 $5 7 \% { \sim } 6 2 \%$ ；在王龙[35的试验中，利用三维图像技术分析了奶牛体况评分情况，但其试验对奶牛特征的提取数量较少，影响了最后的试验准确性和稳定性。由于不同专业知识的限制，目前国内将图像信息技术与奶牛生产结合的工作仅在信息工程领域有所开展，而该技术在反刍动物营养专业的研究团队中却鲜有报道，所以造成了图像信息技术应用的单一化，其他生产中重要、但技术可行的生产指标仍然需要开展大量类似工作，例如图像信息管理系统在跛行评分、乳房评分、采食情况等方面在牧场中的应用方法和效果；同时在国内现有的研究中，关于图像和奶牛体况评分关系的研究尚不充分，在实际运用过程中的准确性和稳定性还有待提高。

# 4小结

图像视觉系统可以提高牧场管理水平，更加合理有效地分配有限的牧场资源，有利于畜群的健康监测和动物福利。目前，牧场应用图像视觉管理系统的照相机多为可见光相机，应用范围涵盖了动物行为观察、体况评分、采食量、卧床、步态评分等；热成像相机可以有效观察动物体温，而深度相机在奶牛体况评分中的应用较为准确。未来视觉系统需要克服环境变化对图像信息的判断，比如光照、测量距离的不同对结果准确率有较大影响。此外，根据牧场不同的实际情况，需要自动调整图像信息处理中的算法，比如后备牛在生长过程中的体态变化会有较大差异，同一算法并不能完全、准确地计算全部生长周期中的体况评分、体重等结果。未来，图像视觉系统可以根据图像信息结果进行自动转群、投喂、淘汰、围产管理、健康评估、舒适度建设等，为实现牧场全自动化管理提供技术支持。

参考文献：

[1]李胜利.当前国内外奶业形势分析及中国奶业竞争力提升[J].新疆畜牧业,2017(1):42-44.[2]李胜利,曹志军,刘玉满,等.2014 年中国奶业回顾与展望[J].中国畜牧杂志,2013,51(2):33-37.[3]COSTA A,ISMAYILOVA G,BORGONOVO F,et al.Image-processing technique to measure pig

activityinresponsetoclimaticvariationinapigbarn[J].Animal Production Science,2013,54(8):1075-1083.   
[4]NASIRAHMADI A,HENSEL O,EDWARDS S A,et al.A new approach for categorizing pig lying behaviour based on a Delaunay triangulation method[J].Animal,2016,11(1):131-139. [5]PORTO S M C,ARCIDIACONO C,ANGUZZA U,et al.The automatic detection of dairy cow feeding andstanding behavioursin free-stall barnsbya computer vision-based system[J].Biosystems Engineering,2015,133:46-55.   
[6]PLUK A,BAHR C,POURSABERI A,et al.Automatic measurement of touch and release angles of the fetlock joint for lameness detection in dairy catle using vision techniques[J].Journal of Dairy Science,2012,95(4):1738-1748.   
[7]MENDOZA F,DEJMEK P,AGUILERA J M.Calibrated color measurements of agricultural foods using image analysis[J].Postharvest Biology and Technology,2006,41(3):285-295.   
[8]BERCOVICH A,EDAN Y,ALCHANATIS V,et al.Development of an automatic cow body condition scoring using body shape signature and Fourier descriptors[J].Journal of Dairy Science,2013,96(12):8047-8059.   
[9]MATZNER S,CULLINAN V I,DUBERSTEIN C A.Two-dimensional thermal video analysis of offshore bird and bat flight[J].Ecological Informatics,2015,30:20-28.   
[10]HALACHMI 1,KLOPCIC M,POLAK P,et al.Automatic assessment of dairy cattle body condition scoreusingthermalimaging[J].ComputersandElectronics in Agriculture,2013,99:35-40.   
[11]NASIRAHMADI A,EDWARDS S A,STURM B.Implementation of machine vision for detecting behaviour of cattle and pigs[J].Livestock Science,2017,202:25-38.   
[12]HAN J G,SHAO L,XU D,et al.Enhanced computer Vision with Microsoft Kinect sensor:a review[J].IEEE Transactions on Cybernetics,2013,43(5):1318-1334.   
[13]JABBAR K A,HANSEN M F,SMITH M L,et al.Early and non-intrusive lameness detection in dairy cows using 3-dimensional video[J].Biosystems Engineering,2017,153:63-69.   
[14]KONGSRO J.Estimation of pig weight using a Microsoft Kinect prototype imaging system[J].Computers and Electronics in Agriculture,2014,109:32-35.   
[15]WANG Y,YANG W,WINTER P,et al.Walk-through weighing of pigs using machine vision and an artificial neural network[J].Biosystems Engineering,2008,100(1):117-125. [16]STAJNKOD,BRUSM,HOCEVARM.Estimat1onofbullliveweightthrough thermographicallymeasuredbodydimensions[J].Computersand Electronics in Agriculture,2008,61(2):233-240.   
[17]BURANAKARL C,INDRAMANGALA J,KOOBKAEW K,et al.Estimation of body weight and body surface area in swamp bualoes using visual image analysis[J].Journal of Buffalo Science,2012,1(1):13-20.   
[18]ANGLART D.Automatic estimation of body weight and body condition score in dairy cows using 3D imaging technique[D].Master Thesis.Uppsala:Swedish University of Agricultural Sciences,2010:19-20.   
[19]葛汝方,陈青,霍永久,等.不同代谢蛋白质水平饲粮对8-10 月龄后备奶牛生长发育、血液 生化指标和体况评分的影响[J].动物营养学报,2015,27(3):910-917.   
[20]AZZARO G,CACCAMO M,FERGUSON J D,et al.Objective estimation of body condition scorebymodelingcowbodyshapefromdigitalimages[J].JournalofDairy Science,2011,94(4):2126-2137.   
[21]BEWLEY J M,PEACOCK A M,LEWIS O,et al.Potential for estimation of body condition scores in dairy catle from digital images[J].Journal of Dairy Science,2008,91(9):3439-3453. [22]GUO H,MA X D,MA Q,et al.LSSA_CAU:an interactive 3d point clouds analysis software for body measurement of livestock with similar forms of cows or pigs[J].Computers and Electronics in Agriculture,2017,138:60-68.   
[23]FISCHER A,LUGINBUHL T,DELATTRE L,et al.Rear shape in 3 dimensions summarized by principal component analysis is a good predictor of body condition score in Holstein dairy cows[J].Journal of Dairy Science,2015,98(7):4465-4476.   
[24]SPOLIANSKY R,EDAN Y,PARMET Y,et al.Development of automatic body condition scoringusingalow-cost3-dimensionalKinectcamera[J].JournalofDairy Science,2016,99(9):7714-7725.   
[25]HOVINEN M,SIIVONEN J,TAPONEN S,et al.Detection of clinical mastitis with the help of a thermal camera[J].Journal of Dairy Science,2008,91(12):4592-4528.   
[26]CORTIVO P D,DIAS E,BARCELLOS JO J,et al.Use of thermographic images to detect external parasite load in catle[J].Computers and Electronics in Agriculture,2016,127:413-417. [27]SONG X Y,TOON L,ERIK V,et al.Automatic detection of lamenessindairy

catle--Vision-based trackway analysis in cow's locomotion[J].Computersand Electronics in Agriculture,2008,64(1):39-44.

[28]VIOLA P,JONES M J.Robust real-time face detection[J].International Journal of Computer Vision,2004,57(2):137-154.   
[29]CANGAR O,LEROY T,GUARINO M,et al.Automatic real-time monitoring of locomotion and posture behaviour of pregnant cows prior to calving using online image analysis[J].Computers and Electronics in Agriculture,2008,64(1):53-60.   
[30]PORTO S M C,ARCIDIACONO C,ANGUZZA U,et al.A computer vision-based system for the automatic detection of lying behaviour of dairy cows in free-stall barns[J].Biosystems Engineering,2013,115(2):184-194.   
[31]黄君冉,钱东平,王文娣,等.基于图像处理技术的奶牛体型线性评定系统[J].农业机械学 报,2007,38(4):111-113,117.   
[32]郭浩,王鹏,马钦,等.基于深度图像的奶牛体型评定指标获取技术[J].农业机械学 报,2013,44(S1):273-276,229.   
[33]朱坤华,李骞,武书彦.基于三维视觉的荷斯坦奶牛中遗传育种个体的最优选择[J].科技通 报,2017,33(2):52-55.   
[34]刘建飞.图像识别技术在奶牛体况评分中的应用研究[D].硕士学位论文.济南:山东大 学,2012:49-50.   
[35]王龙.机器视觉在奶牛体况评定中的应用[D].硕士学位论文.上海:东华大学,2014:53-55. Application of Image Information Technology in Dairy Cow Production   
SUN Yukun LI Wenxi YAO Enyue LIU Xin LI Yang ZHANG Yonggen\* (College of Animal Science and Technology, Northeast Agriculture University, Harbin 150030, China)   
Abstract: High cost and low effciency hinder the development of dairy industry. Image information technology can objectively and availably evaluate the requirement of dairy nutrition and the level of health, reduces animal stress and improves the intelligent management in farms. This review described the image-forming principle of the visible light camera, thermal imager camera and depth sensor camera with evaluation of method and efficiency in dairy cow production, and summarized the researches in the application of image vision system in body weight

measurement， body condition scoring， body temperature monitoring，gait scoring， feed intake measurement and lying behavior monitoring, and so on. The performance of developed systems was reviewed in terms of sensitivity,accuracy and error rate. The technology can support daily observation for administrator on herds，which can be used as an important step towards the development of an automated system. Key words: dairy cow; image information technology; production management; application