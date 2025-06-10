# 专家识谱平台的设计与实现

雷国洪1，徐洋²，牛晨辉23，田海俊¹，张彦霞²，崔辰州²，赵永恒²(1.三峡大学，湖北宜昌 443002；2.中国科学院国家天文台，北京100012；3.华中师范大学，湖北 武汉430079)

摘要：在利用LAMOST巡天数据进行特殊天体搜寻或样本构建时，以及在处理LAMOST不断累积的低信噪比光谱时，通常需要耗费科学家大量的时间完成人工识谱。针对这样的问题，我们设计并实现了一套专家识谱平台。该平台是集光谱可视化、光谱分析、多波段图像融合、多种数据挖掘算法等功能于一体的科学与科普教研平台。利用该平台，天文学家进行天体搜寻、样本构建等科学研究将会变得相对容易；通过该平台，高校教师可以开展各种有天文特色的教研活动；借助群体力量，该平台将能逐步消化LAMOST不断积累的标注为“UNKNOWN"的未知光谱数据。

关键词：LAMOST;人工识谱;数据挖掘;天文教学中图分类号：TP302文献标识码：A文章编号：

# 1.引言

我国自主研发的大型光谱巡天望远镜LAMOST自2012年正式巡天以来，已经获取了700 余万条光谱。这些光谱为科学研究提供了丰富的数据基础，科学家们已经利用LAMOST数据取得了一系列高质量的研究成果，发表学术文章论文近百篇。LAMOST为我国在天文学领域跻身世界先进行列做出了重要贡献。

从科学成果上看，LAMOST的大样本数据优势吸引了众多的科学家，一大批科学成果集中在特殊天体的搜寻或特殊样本的构建上，比如，李海宁等人开展的贫金属星样本的搜寻；吴学兵等人开展的类星体样本构建[2}；霍志英等人开展的M31/33附近类星体的搜寻[3]；任娟娟等人开展的白矮一主序双星的搜寻[4]；赵景昆等人[5]、张悦扬等人，Rebassa-Mansergas等人开展的DA型白矮星样本的识别及相关科学研究；侯文等人开展的Am 星的样本构建；司建敏等人、纪伟等人[7开展的碳星候选体搜寻；杨帆等人开展的RR天琴座变星及氢的巴尔莫线系分布统计；石志鑫等人开展的双峰窄发射线星系及AGNs样本的搜寻；杨海峰等人开展的 $\cdot$ 型星系搜寻；林建峥等人开展的Be星搜寻；沈世银等人开展的星系对样本证认[8等等。LAMOST的样本太大，启动这些研究工作往往需要首先设定一套复杂的判别条件并依靠各种数据挖掘算法或统计方法挑选出目标候选体，然后基于人工识谱和多波段测光信息综合来证认候选体。机器筛选得到的候选体依然动辄数千、数万甚至数十万，人工判别工作量巨大。

从数据质量分布上看，LAMOST发布的700多万条光谱中(以LAMOSTDR4为例)，如图1所示，除了600万条较亮的恒星能被pipeline自动处理给出结果外，11.8万条星系和4万多条类星体，由于信噪比低，pipeline 自动处理效果不好，有很大一部分纯粹是靠人工一条条识谱确定的。还需要重点关注的是，5年巡天观测已经积累了62万余条标注为“UNKNOWN"(未知光谱)的待识别光谱，这些天体大多数是因为自身太暗获取的光谱信噪比太低，传统的算法无法处理；也可能有极少数奇异的天体，由于谱型太奇怪，传统的算法无法识别，如毛晓燕等人提出了基于加权滤波的低信噪比LAMOST光纤光谱信号降噪[9]相关算法。随着巡天观测的不断深入，这些未知光谱会越积累越多。如何处理这些低质量的数据，是现代统计学和数据挖掘技术面临的一个挑战。

围绕LAMOST天文光谱的处理，在LAMOST项目组的带动下，一批数据挖掘专家团队纷纷加入了光谱处理的研究课题中，并取得了显著的成果。然而，即使数据挖掘专家能对这些低信噪比光谱给出类别或参数估算值，天文学家依然会抱着质疑的态度放弃使用这些数据。这些光谱只有经过人工识别后，才能提升其使用可信度。但是如此巨量的数据仅靠少数专家利用有限的时间、有限的精力完成人工处理是不可能的。

为了改善这种状况，我们提出构建基于数据挖掘的专家识谱平台，利用先进的IT技术及数据挖掘技术整合常见算法，研发一套集光谱数据管理、可视化与分析为一体的科学与科普教研专家识谱系统。

# 2．目标分析及结构设计

按照天文学家及天文教育工作者的设想，专家识谱平台应满足以下四个方面要求：

（1）集成多种可视化与分析工具、数据挖掘算法，使天文学家甚至普通学生搜寻特殊天体、作出新发现变得更加容易；（2）围绕低信噪比光谱，开展数据挖掘算法研究，利用机器尽可能多地挖掘有价值信息，减少人工识谱难度；（3）支持团队协作工作模式，辅助天文教育工作者在天文教学过程中开展特殊天体搜寻、人工识谱等教研活动，实现有天文特色的研究型素质教育；（4）能像国际星系动物园（GalaxyZoo）Raddick J，LintottC J，SchawinskiK， et al. Galaxy Zoo: an experiment in public scienceparticipation[J]. Advances in Atmospheric Sciences， 2007， 39: 892.项目一样，通过发动公众力量，完成需要大量人工干预的天文光谱数据的处理工作，逐步消化LAMOST巡天不断产出的未知光谱。

Fig.2 The architecture of expert platform for spectral inspection

从上述业务需求出发，我们设计了一套专家识谱平台。如图2所示，该平台主要包括三个组成部分：数据挖掘层（Data-mining Layer）、数据节点层(Data Node Layer)、专家识谱层(Expert Layer)。

（1）数据挖掘层：针对LAMOST低信噪比光谱，开展各种数据挖掘算法的研究，并利用这些算法最大限度地挖掘LAMOST低信噪比光谱的科学价值。主要涉及LAMOST低信噪比光谱的分类问题、恒星光谱的特征提取问题（给出部分恒星的大气物理参数的参考值）、低信噪比星系及类星体的红移测量问题。数据挖掘成果上传至数据节点层，由服务器管理。

（2）数据节点层：管理用户上传的数据。从文件类型上看，主要包括用于存储元数据的数据库文件和存储光谱数据的fits文件；从数据访问权限上看，包括对所有注册用户可见的公共数据（PublicDB）、组内成员可见的组内数据（GroupDB），以及用户私有的个人数据（MyDB）三个数据层次。该层的数据封装后通过ODBC或JDBC与专家层交互。

（3）专家识谱层：建立多平台的客户端，比如Web客户端、桌面应用程序端、手机APP等实现对光谱数据的在线可视化与分析。可视化主要指星表数据的可视化、fits光谱图像的实时交互可视化、对应的多波段数据融合可视化；数据分析主要包括红移或视向速度的实时计算、光谱的便捷式模版匹配、谱线的标示、数据查询以及用户Feedback 等功能。

数据挖掘层接口相对松散，数据挖掘的算法允许用户围绕具体的科学目标自己定制，只要求输出结果为平台兼容的数据格式，平台将会逐步集成多种常见数据挖掘算法，譬如，用于测光红移、光谱分类、光谱特征提取等特定需求的神经网络、支持向量机、主成分分析等算法。这部分体现平台的高级功能，目前只是预留了大部分接口，后期根据用户需求逐步实现。本文不做重点描述。

数据节点层和专家识谱层耦合性较强，我们选择在轻量级J2EE Spring框架下实现，其中数据库选用天文上较为常用的MySQL数据库，利用ORM插件实现星表数据的动态管理，光谱数据分析与可视化界面通过Javascript、图表处理显示组件、Mallet小波降噪等插件来实现。数据节点层和专家识谱层是识谱平台的基本模块，本文将重点讲述。

# 3．功能分析与实现

本节主要讲述数据节点层和专家识谱层的功能分解与实现，其中数据节点层的数据管理，主要利用数据库技术和网络技术来实现；专家识谱层中一维光谱数据的在线可视化与分析，主要通过Java图表处理相关技术来实现。专家识谱平台目前主要设计了八项功能：用户管理、数据访问权限管理、数据上传、数据检索与下载、多波段信息融合、一维光谱数据的可视化与数据分析、专家信息反馈与知识库管理、虚拟天文台服务等。

# 3. 1. 用户管理

平台系统完全模拟真实科学研究团队的协作模式，将用户划分为四个层次：系统管理员、群管理员、专家用户、匿名用户。

（1）匿名用户（Anonymous）：浏览开放信息，了解或学习相关知识，比如学习（Learning）模块、FAQ以及公开的数据，没有导入数据权限。（2）专家用户（Expert）：可以上传自己的私有数据（包括光谱数据和星表数据），利用可视化工具识别、标识光谱，将处理结果写入数据库。（3）群管理员（GroupAdmin）：群管理员拥有创建新用户、添加组员和删除组员的权限，群管理员自动成为新组成员。（4）系统管理员（SystemAdmin）：除具有群管理员、专家用户权限外，系统管理员可以创建群组并决定某用户是群管理员还是普通用户，同时还负责为用户分配最大可用存储空间。

# 3.2. 数据访问权限管理

根据科学研究的实际需求，平台将数据划分为三个层次：个人数据（MyDB）、群组数据（GroupDB）、公共数据（PublicDB），如图3所示。

（1）MyDB：用户自己上传的数据表，该数据为私有数据，仅上传者自己可见。（2）GroupDB：群内共享的数据表，该数据由数据上传者提交群内共享申请，由群管理员审核决定数据是否对群内所有成员可见。（3）PublicDB：可被所有注册用户访问的数据表，该数据由群管理员提交申请，由系统管理员审核决定数据是否让所有用户可见。

# 3.3. 数据上传

平台的数据类型主要分为两类：星表数据和一维光谱数据。其数据上传界面如图4所示。

Fig.4TheuploadUIofCSVcatalogandFITS spectrum files

（1）星表数据：系统主要支持CSV文件格式。用户上传CSV文件数据入库，系统在MyDB 中生成对应数据表。CSV文件的第一行被自动识别为数据表的字段名，CSV文件名默认为数据表名称（用户也可以自己指定表名称）。

（2）光谱数据：系统主要支持FITS文件。主要通过两种方式获取FITS文件：像LAMOST、SDSS这样的大型巡天，通常都已经将数据发布在网上，用户只需要在上传的星表数据中提供mjd、plateID、fiberID等唯一标识光谱的信息，系统会自动为用户定位相应的FITS文件；像兴隆“2.16”、丽江“2.4"等望远镜产出的小样本光谱数据，用户需要自己将FITS文件打包上传至平台。

# 3.4. 数据检索和下载

这里的数据检索有两层含义。首先是星表文件的检索；其次是所选择星表的内容和用户feedbacks记录的检索。如图5所示，如果管理的星表较多，可能需要匹配表名、关键字、数据源等条件来检索出用户想要的星表。

用户可能不熟悉数据库查询语言。为此，系统提供了动态生成常见检索条件表达式及其按照“与”、“或”关系组合形成复杂树形逻辑结构检索条件的功能，如图6所示。对查询结果，全选或部分选中左侧的复选框，点击右侧的下载“Download"按钮，可以打包下载数据，如图7所示。

# 3.5. 多波段信息融合

在科学研究过程中，科学家除了查看天体的某条光谱数据外，通常还需要综合多波段的图像或光谱信息，以便准确判断天体类型或测量大体的物理参数。为此，平台提供接口融合 SDSS、2MASS等巡天望远镜的测光图像数据。查询界面如图8所示，查询结果如图

9所示。

图9.多波段查询示例：利用 SDSS的SkyServer工具Szalay A S，Gray J，Thakar AR，etal. The SDSS skyserver: public access to the sloan digital sky serverdata[C]// Proceedings of the 2002 ACM SIGMOD international conferenceon Management ofdata.，并根据传入的RA和DEC 自动定位测光图像

Fig.9 An example of Multi-band query: the SDSS Skyserver automatically targets the photometric image with the input parameters, i.e. RA and DEC

# 3. 6. 光谱数据可视化与数据分析

该部分包括光谱的局部缩放、谱线标注、等值宽度测量、小波滤波降噪、170多种光谱的模版匹配、红移自动测量、图像保存、打印等基本操作。人机交互操作完全通过浏览器来实现光谱可视化，不需要额外安装任何插件。显示界面如图10所示。

通常利用批处理程序pipeline 对巡天获取的光谱进行自动模版匹配，基于最佳匹配进行类型判断和参数测量。然而，pipeline 对低信噪比光谱的处理效果不好，因此LAMOST产出了相当一部分未知光谱，这些光谱不应该被遗忘。

平台提供全面的恒星、星系以及类星体模版，用以帮助用户实现人机交互式模版匹配。用户挑选模版，通过蒙罩技术剔除光谱上不可靠部分，完成粗略匹配后，系统将自动寻求最佳匹配位置，并自动计算天体物理参数（红移或视向速度等）。

图10.FITS光谱的可视化与数据分析，蓝色曲线为LAMOST观测光谱，黑色曲线为QSO光谱模版，红色 虚线为 $\mathrm { H } \alpha$ 发射线，该发射线及整个模版光谱可跟随鼠标自由移动，以寻求模版与观测光谱的最佳匹配 Fig.10 The display and analysis ofa fits spectrum,the blue curve is the LAMOSTobserved spectrum,the black curve is a QSO spectrum template,the red dashed line marks the location of Hα emisson line, which and the whole template are movable along with the cursor

# 3. 7. 专家信息反馈与知识库

对于每条光谱，专家可以通过光谱可视化与分析模块完成人工处理，并将处理结果反馈至数据库。GroupDB和PublicDB中的每一条光谱，可能会被多个用户分析处理，平台将记录每位用户的分析结果，并形成列表，供科学家参考。经过长时间运行后，系统将收集形成一系列专家知识库。

# 3.8. 虚拟天文台（VO）服务

国际虚拟天文台联盟一直致力于将全球范围内的研究资源无缝透明地连接在一起，形成数据密集型网络化天文研究平台。经过十几年的发展，已经拥有了丰富的数据资源、服务资源，包括由从高能伽玛射线一直到射电的全波段数据信息，并且基于这些数据，研发出了很多优秀的软件工具，比如 Topcat、AladinBonnarelF，Fernique P,Bienaymé O， et al. The ALADIN interactive sky atlas: a reference toolfor identification of astronomical sources[J]. Astronomy &Astrophysics Supplement， 2000，143:33-40.、NEDHelou G， Madore B F,Bicay M D, et al. The NASA/IPAC extragalactic database[C]//Proceedings on the 6th Workshop of the Advanced School of Astronomyof the Ettore Majorana Centre. 1991: 89-106.、SkyServerSzalay A S，GrayJ， Thakar A R， et al. The SDSS skyserver: public access to the sloandigital sky server data[C]// Proceedings of the 2002 ACM SIGMODinternational conference on Management of data.、SciServer等。我们的平台将通过后台脚本，实现与这些服务或数据的对接。

# 4.应用案例

本节以几节高校天文选修课的主要教学环节设计为例来展示专家识谱平台的使用功效：

(1）课前，我们将任娟娟等人[7-8挑选的318颗白矮一主序双星样本与一些普通恒星的样本数据混合并导入平台，同时按照学号为学生批量注册账号，并设为同一Group 成员。

(2）在学生初步了解《恒星的一生》这一章节后，教师又专门介绍了一些奇特的恒星系统及其科学意义，在平台上给学生演示了各种白矮主序一双星的测光图像、光谱特征，最后分组交叉分发“白矮一主序双星搜寻”任务。

(3）在接下来的第二课时，为调动学生的积极性，特意为学生安排了一次天文观测活动“辇道增七”，用普通的科普望远镜看它是一黄一蓝的双星，该双星与学生要搜寻的白矮一主序双星很像，但存在一些本质上的区别；在高倍望远镜下，黄色的辇道增七A本身还是一个联星，蓝色的辇道增七B是一颗快速自转的Be星。

(4）要求每个学生至少人工识谱 50条不同的光谱，并在一个月之后提交一份简单的研究报告。

Fig.12 The photometry image of white dwarf-main sequence binary star candidates (left)and their spectrum of

LAMOST (right)

图12.中的两幅图像都截取于专家识谱测试平台，在我们的平台上，学生仅需要三到五次鼠标点击即可获取类似的图像。普通学生通过左边天体的图像可以很好地判断是否属于双星候选体，如果要进一步确定，需要分析右边的光谱图像，光谱图像是系统直接读取FITS 文件实时动态展示的，支持互动式操作。右边蓝色曲线是LAMOST的实测光谱，经过小波滤波处理（仅需一次鼠标点击），消除了大部分噪声信号，使光谱变得光滑，而黑色曲线是经过两次鼠标点击后从系统调取的白矮星光谱模版。通过蓝色和黑色曲线对比，学生不难发现，蓝色曲线在波长大约6500埃之后的红端，与模版的谱型匹配的不好，这主要是因为该光谱的红端部分由其伴星（左图偏红的矮星）贡献，光谱的红端部分可以用矮星的模版很好地匹配。

识谱平台记录每位同学的识谱结果，教师（Group 管理员）很容易检索出那些被多个学生同时确认为白矮一主序双星的记录。被不同学生确认的次数越多，该天体属于白矮一主序双星的概率就越大。通过这样的研究型教学活动，我们发现学生对浩瀚宇宙中那些肉眼看不见但客观存在的东西非常感兴趣，通过兴趣诱导、平时或期末成绩鼓励，大部分学生都能积极参与，共同努力将绝大多数的白矮一主序双星找出来。教师还可以将那些非常疑似的白矮一主序双星提取出来，分配给物理学院的学生或对天文学真正感兴趣的学生，利用学校每年开展的大学生科技立项活动或本科毕业设计的机会，让学生进一步研究哪些双星属于共包层后双星候选体。

除了上述的应用案例外，目前该平台还可以很好地应用于类星体的人工搜寻（譬如图10所示）、星系对搜寻、碳星搜寻等科学目标上，既可通过个人方式来完成，也可支持团队协助模式进行，由于篇幅限制，这里就不再赘述。

# 5.总结与展望

本文概述从LAMOST光谱数据处理的需求出发，基于先进的IT技术研发一套专家识谱平台,以网站形式对外发布服务，帮助科学家提高人工识谱效率，帮助天文教育工作者丰富教学形式，帮助LAMOST消化未知光谱。

目前该平台还需要继续集成多种数据挖掘算法，我们正致力与国际知名的一维光谱可视化软件 SPLAT-VOSkoda P，Draper P W，Neves M C，et al． Spectroscopicanalysis in the virtual observatory environment with SPLAT-VO[J].Astronomy and Computing，2014,7-8 ：108-120.的作者合作，使 SPLAT-VO成为专家识谱平台的主要客户端之一。希望经过不断地完善，使该平台成为我国大科学工程LAMOST不可或缺的光谱数据处理平台，并使之成为天文光谱科普教育的首选平台。

# 参考文献

[1] LiHN, Zhao G， Christlieb N，et al. Test observations that search for metal-poor stars with the Guoshoujing Telescope (LAMOST)[J]. Resarch in Astronomy and Astrophysics , 2010,10 (8): 753-760.   
[2] Wu X B,Chen Z Y, Jia Z D,et al. A very bright ( $( \dot { 1 } = 1 6 . 4 4 )$ quasar in the 'redshift desert' discovered by the Guoshoujing Telescope (LAMOST)[J]. Resarch in Astronomy and Astrophysics,2010,10 (8）:737-744.   
[3] Huo Z Y, Liu X W, Xiang M S, et al. The LAMOST survey of background quasars in the vicinity of the Andromeda and Triangulum galaxies - II. results from the commissioning observations and the pilot surveys[J]. The Astronomical Journal, 2013,145 (6) : 159- 167.   
[4] Ren JJ,Luo A L,Li Y B,et al. White dwarf - main sequence binaries identified from the LAMOST pilot survey[J]. The Astronomical Journal, 2013,146 (4） : 82-93.   
[5] Zhao J K,Luo A L, Oswalt T D, et al. 72 DA white dwarfs identified in the LAMOST pilot survey[J]. The Astronomical Journal,2013,145 (6) : 169-187.   
[6] Hou W,Luo A L, Yang HF, et al. A large sample of Am candidates from LAMOST Data Release 1[J]. Monthly Notices of the Royal Astronomical Society,2015,449 (2） : 1401. 1407.   
[7] Ji W. Carbon star candidates identified from LAMOST DR2[C]//中国天文学会 2015 年 学术年会摘要集.2015:67.   
[8] Shen S Y, Maria A F, Chen L, et al. A sample galaxy pairs identified from the LAMOST spectral survey and the Sloan Digital Sk y Survey[J]. Resarch in Astronomy and Astrophysics,2016 (3） : 63-72.   
[9]毛晓艳,张博,叶中付.基于加权滤波的低信噪比LAMOST光纤光谱信号降噪[J].天文研 究与技术，2015,12(4): 447-454. Mao Xiaoyan, Zhang Bo, Ye Zhongfu. Using weighted filtering to denoise low-SNR spectra observed through the LAMOST fiber optics[J]. Astronomy Research and Technology 2015,12(4): 447-454.   
[10] Raddick J,Lintott C J, Schawinski K, et al. Galaxy Zoo: an experiment in public science participation[J]. Advances in Atmospheric Sciences, $2 0 0 7 , 3 9 : 8 9 2$   
[11] Szalay A S, Gray J, Thakar A R, et al. The SDSS skyserver: public access to the sloan digital sky server data[C]// Proceedings of the 2002 ACM SIGMOD international conference on Management of data. 2002: 570-581.   
[12] Bonnarel F,Fernique P, Bienaymé O, et al. The ALADIN interactive sky atlas: a reference tool for identification of astronomical sources[J]. Astronomy & Astrophysics Supplement,2000, 143: 33-40.   
[13] Helou G, Madore BF, Bicay MD, et al. The NASA/IPAC extragalactic database[C]// Proceedings on the 6th Workshop of the Advanced School of Astronomy of the Ettore Majorana Centre. 1991: 89-106.   
[14] Skoda P, Draper P W, Neves M C, et al. Spectroscopic analysis in the virtual observatory environment with SPLAT-VO[J]. Astronomy and Computing, 2014,7-8 : 108- 120.

# Expert Platform for the Spectral Inspection

Lei Guohong', Xu Yang², Niu Chenhui2,3, Tian Haijun', Zhang Yanxia², Cui Chenzhou², Zhao Yongheng²

(1．China Three Gorges University, Yichang, 443002,China; 2. National Astronomical Observatories, Chinese Academy of Sciences,Beijing 100012,China ；3.Central China Normal University,Wuhan,430079,China)

Abstract: An expert platform for spectral inspection is designed and implemented for the LAMOST survey in this paper. The platform is useful for 1) searching for objects with particular spectra； and 2) identifying accumulating spectra with low signal-to-noise ratio. It is a comprehensive science- and teaching-aimed platform，which has the capability of spectral visualization,analysis, multi-band image matching,etc.Based on this platform,astronomers can build the samples with particular spectrum easily,and teachers can carry out a variety of spectrum-based teaching and research activities.Finally, the accumulating number of LAMOST UNKNOWN objects can be gradually minimized with the help of world-wide astronomers using this platform. Key words: LAMOST; Visual Inspection; DATA Mining; Astronomical teaching 麻烦来冬在第8页横线下面加 http://andromeda. star. bris.ac.uk/topcat/tutorial/topcat-tagung. pdf