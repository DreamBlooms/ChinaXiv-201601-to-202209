# 基于虚拟天文馆对全天相机姿态的精确测量

李小波¹，刘煜¹，崔辰州²，宋腾飞¹，王晶星¹，樊建康」

1.中国科学院云南天文台，昆明650216；2.中国科学院国家天文台，北京100012)

摘要全天相机已广泛地使用在气象、天文等领域．在监测云量、夜天光、流星等应用中，均需要准确掌握相机的姿态参数，特别是在安装和运维中造成的偏差．本研究旨在开发一套基于虚拟天文馆的像场测量方法，通过比较参考恒星的虚拟坐标及其像点的实测坐标，高精度测量相机的姿态参数．使用中国科学院云南天文台安置于四川无名山观测站的全天相机，分析于2016至2017年获得的4组全天图像，采集了容量分别为\~10、 ${ \sim } 5 0$ ，\~200 的恒星样本，通过 Stelarium虚拟天文馆获得了恒星的地平坐标，对全天相机像场的天顶位置、测者子午线方向等基本参数进行了精确的测量．主要结果为：(1)开发了一种基于虚拟天文馆计算恒星地平坐标功能的测量方法，使姿态测量建立在容量较大的参考恒星上．该方法准确度高，对设备配置的依赖性低，具有较强的可移植性.(2)采用网格法对图像天顶的定位达到了亚像素的精度，有望满足高定位精度监测的需要.(3)全天相机姿态精度的首要指标是光轴的竖直性，光轴偏离天顶会对投影的轴对称性造成不可忽略的影响.(4)维护作业对圆形像场几何参数的改变甚微，但可能会改变指向和旋转角，并需要重新测量.(5)生成了符合制图惯例的可视化产品，为监测数据的深入分析奠定了基础.

关键词 全天相机；虚拟天文馆；视场；天顶；云量监测   
中图分类号：P111.33   
文献标识码 A   
文章编号:XXXXXXXXXXXXX

# \*基金项目

国家自然科学基金(11533009,11503084,11873090,11873092)，西部之光一带一路中沙天文合作团队基金，云南省创新团队基金联合资助.

# 作者简介

李小波，男，博士，研究方向：天文选址和太阳物理．E-mail: lixiaobo@ynao.ac.cn

# 通讯作者

刘煜，男，博士，研究方向：天文选址和太阳物理.E-mail:lyu@ynao.ac.cn

# Accurate measurement of all-sky camera's attitude based on virtual planetarium

LI Xiaobo1,LIU ${ \mathrm { Y u } ^ { 1 } }$ , CUI Chenzhou², SONG Tengfei1,WANG Jingxing1 ,FAN Jiankang'

1.Yunnan Observatories,Chinese Academyof Sciences,Kunming 65ooll,China   
2.National Astronomical Observatories,Chinese Academy of Sciences,Beijing lOool2,China

AbstractAll-sky cameras have been widely used in meteorology,astronomy and other fields.In the monitoring of cloud cover, night skylight, meteorsand other applications,it is necessary toacurately measurecameras'atitude, especially the deviations caused during installation and maintenance.The purpose of this studyis to developa method to measure camera's atitude parameters with high precision,by comparing the polar coordinates ofreference stars' image points and the stars'horizon coordinates computed by avirtual planetarium,and generate visualization products with errors corrected. Using the all-skycamera developed by the Yunnan Observatories of the Chinese Academy of Sciences and deployed in Sichuan's Wumingshan observation station,weanalyze four sets of all-sky images obtained in October 2O16 and June 2O17, select star samples with capacities of ${ \sim } 1 0 , { \sim } 5 0$ ,and ${ \sim } 2 0 0$ ,obtain their coordinates through the Stellarium planetarium,and accuratelyacquire the atitude parameters such as the zenith position and rotation angle of the image field.Main results are: (1) We developed a method that is based on virtual planetarium's function to compute stelar coordinates,and guaranteed the accuracy of the measurement with alarge capacity of reference star samples.The method does notrelyon the camera's specs and therefore is transplantable.(2)According to thecamera's atitude on 2016-10-20,its image field's radius and center coordinates are 0.4289 and (O.7590,0.5048)respectively (in the unit length of the image's Y direction, the same below); the zenith's coordinates are: $( 0 . 7 5 1 1 8 { \scriptstyle \pm 0 . 0 0 0 2 0 }$ ， $0 . 4 9 5 7 2 { \scriptstyle \pm 0 . 0 0 0 2 2 } )$ ; the angle between the zenith and the optic axis is $2 . 3 6 ^ { \circ }$ ; the rotation angle is $1 5 2 . 7 1 { \scriptstyle \pm 1 . 5 8 }$ (3) Maintenance operations have little $( \leq 0 . 2 8 \% )$ influence upon the geometric parameters of the round-shaped image field, but might cause the optical axis to deviate from the zenith,which willhave an non-negligible efect on the axial symmetry of the camera's projection.Each maintenance willalso change the camera's rotation angle which needs to be re-determined afterwards.(4) Produced visualization products conforming to industry norms,thus cements data's reliability for further investigations.

Keywordsall-sky camera; virtual planetarium; field of view; zenith; monitoring of cloud cover;

# 1引言

全天相机是利用朝向天顶的鱼眼镜头获取全天空图像的照相机．全天相机已获得广泛的应用，主要在以下领域．(1)地基遥感全天空云量自动化监测[1,2]．在数字图像处理软件中，利用经验或理论确定的阈值判别云或蓝天，然后进一步对云进行分类和计量．大多数算法3都是基于瑞利散射或饱和度对从三原色计算出的某指标进行判断[46]．其他计量云量的方法有：比较天空辐射亮度、比较两个或多个窄波段的辐射值、比较白昼实测和虚拟天空[7]、比较夜间实测和虚拟星场、神经网络[8]、超像素分割等．对于薄云、临近太阳的天区、特殊天气情况、夜间云量、临近地平线的云量的判断仍是难点．对云高和云状的自动监测仪器仍需进一步实验研究.(2)监测天文址点的夜天光和云量[10,I1]，在我国的天文界，全天云量相机已应用于丽江天文观测站[12]、SONG 项目青海观测站[13]、西部天文选址[14,15]等.(3)用于监测流星的全天相机网络[16].(4)对舰船进行天文导航定位[17,18].

在以上各方面的应用中，均需要准确掌握像场的参数．较高标准是：准确获得物一像的投影关系，能够将图像中的特征点还原为天球上的坐标，这对于监测和定位航空器、流星等小尺度物体至关重要．较低标准是：掌握图像中的实际方向和天顶位置，以确定特征物的方位．对于任何用途的全天相机图像，起码要知道其东南西北方向.

理想情况下，全天相机的光轴指向天顶，视场中心与天顶重合；图像的纵轴与测者子午线重合．但是，实际的全天相机不能达到这个标准．首先，相机一般安置于高山、沙漠、建筑物顶端等，由于条件所限，施工时无法像安装大型天文观测设备那样对方位进行准确的校准，难免产生不能忽略的安装偏差．其次，全天相机大多是无人值守的，恶劣天气、野生动物等外力都有可能使相机偏离其初始安装姿态．再次，对相机的维修、改造、清洁等作业也会改变其姿态.

所以，在处理全天相机图像的工作中，就需要依据参照物对图像进行矫正，获得其旋转角、天顶位置等基本参数．不仅需要对新安装的相机初光获得的图像进行精细测量，在日常运行中也要不定期再次测量并更新参数.如此方能生成可靠的可视化产品，为监测工作提供有效的服务．另外，准确测量像场也是矫正镜头畸变、进行坐标变换、进而实现上述"较高标准"的起点，

恒星是全天相机视场中最可靠的参照物，而虚拟天文馆大大简化了对星表的检索和计算工作，在图形化界面中可以快速完成检索恒星和测量坐标的操作，正好可以用于对全天相机姿态的测量．同时，虚拟天文馆具有直观的用户界面，往往可以离线工作，对计算机配置要求相对较低，相比于虚拟天文台[19-21]，更符合野外观测站的实际条件.

基于上述需求和条件，本研究拟达到四方面的目标:(1)开发一套基于虚拟天文馆的像场测量方法，通过比较特征恒星的地平坐标及其像点在像平面上的极坐标，高精度测量相机的姿态，并探索在自动化、可移植化等方面深入开发该方法.(2)基于一台典型全天相机的实际监测数据，通过像场测量其姿态：确定图像中天顶的位置，及其与像场中心的距离，达到亚像素的精度；测量测者子午线的方位；测量相机像场的基本几何参数.(3)在某次重大维护之前和之后分别测量上述参量，了解维护工作对相机姿态的影响.(4)矫正姿态偏差并生成符合规范的可视化产品．下面介绍本研究的研究资料、数据压缩方法和研究结果.

![](images/0742a8bd9afdf27e51a84ecad11d42476a664b06fd3613642258cd5fd88ef4a4.jpg)  
图1无名山全天相机于2017年6月5日日初时拍摄的一帧图像Fig.1 An image taken by theWumingshan all-sky camera at the dawn on June 5,2017.

# 2 研究资料

本研究使用的全天相机架设于四川稻城县的无名山二号观测站．无名山是中国科学院云南天文台选址与日冕观测团组在西部天文选址科考工作中发掘出来的优秀天文址点[15.223.24]．该相机由光学、采集、控制、和保护系统组成.其中，光学系统基于一枚适马(Sigma)牌焦距 $4 . 5 \mathrm { m m }$ 、光圈2.8的鱼眼镜头，视野略大于 $1 8 0 ^ { \circ }$ ；采集系统基于一台佳能(Canon)牌 EOS-60D 单镜头反光相机；控制软件和数据库安装于一台研祥牌工业控制计算机，根据日月的高度、月相、天光亮度调整感光度和曝光时间；光学和采集系统被封装于一个能抵御恶劣天气的机箱中，镜头透过透明半球罩指向天顶，形成圆形的像场(图1).图2展示了位于机柜顶部的天窗的基本结构，该半球罩半径为 $1 0 \mathrm { c m }$ ，镜头前端高出半球球心 $5 \mathrm { c m }$ ，视野达到地平线以下．在半球罩的周围安装了用于除霜露的电热装置.自 2015年11月初光以来，该设备对无名山的天空进行了连续稳定的监测．观测人员对半球罩进行例行清洁，研发人员不定期对相机进行检修、更换零件、升级部件等操作.

![](images/b2f61dc7df0b668c7740bd3e5ee8c15782e65bceec2702570b5293fe8a22e721.jpg)  
图2无名山二号点全天相机的设计图(左)和实际外观(右)  
g.2Thedesign(left)andactualoutlook (right)oftheal-skycameradeployed inMt.WumingshanNo.2observationstation.

Stellarium[25]1是由Fabien Chareau等人开发的一种开源虚拟天象模拟软件．基本星表包含 60万余颗恒星，附加星表包含177万余颗恒星，可还原大气层的光影效果，并叠加赤道式和地平式坐标网格，满足本研究的需要.基于无名山二号观测站的经纬度(纬度 $: 2 9 ^ { \circ } 6 ^ { \prime } 2 4 . 5 9 ^ { \prime \prime }$ 、经度： $1 0 0 ^ { \circ } 6 ^ { \prime } 3 2 . 0 7 ^ { \prime \prime } ;$ 、海拔 $( 4 8 0 0 \mathrm { m } )$ 、以及指定的时间，即可获得该时该地的星图，并查找某恒星的地平坐标值等参数．图3显示了其用户界面，在左上角列出了某选定恒星(HIP21502)的详细参数，包括在指定观测条件下的地平坐标．为了便于显示和打印，已经对星图做了色调反转处理，下同.

拟分析无名山全天相机于2016年10月和2017年06月获得的4组全天彩色图像．其中，夜间两组共两帧，均在良好的气象条件下拍摄，用于分析星场；昼夜数据两组共11帧，用于测量像场.数据的基本参数列于表1.于2017年05月底曾对相机的安装位置和伺服系统进行调整，像场发生了变化．因此，使用这两个月的数据比较维护前后的相机姿态，

![](images/00ca6bd52a40e8f1e950e8d29dc431f56a2970c33c041a7ed929663af8fabd90.jpg)  
图3Stellarium 虚拟天文馆的用户界面 Fig.3 User interface of the Stellarium Virtual Observatory.

# 3测量像场的几何参数

该全天相机指向天顶拍摄，获得近似等角投影的全天空半球像，天空物点的纬度和方位角对应着像点的极距和极角．在像场的边缘，部分天际线被山峦、监测设备等物遮挡.我们采用标记边缘点的方法测量圆形像场的中心、半径等几何参数.

# 3.1选取监测数据

无名山全天相机于2016-10-05日和2017-06-05日均进行了连续的监测，使用两种时间和空间分辨率分别采集了285 和352帧图片．经观察，在晴天太阳或满月升起/落下的时刻，入射光线的天顶角约为 $9 0 ^ { \circ }$ ，视场边缘的山峦和镜头的边框均被照亮，太阳光也没有直射镜头而产生炫光，像场边缘较为较明亮、而像场外基本黑暗，便于对视场边缘进行定位，例如图1.我们选取了两组共计11帧图片，分别编号为D1-d和D3-d.

# 3.2测量方法和结果

将像场的边缘点进行椭圆拟合，得到其长短轴长、中心坐标、偏心率等几何参数，并计算它们在每组图像中的均值．在后续计算中将基于这些参数对图像进行分析．在图1中，白色椭圆是拟合的像场边缘.

对D1-d和D3-d组数据的测量结果列于表2.长半轴和短半轴的差异仅为半轴的千分之二，像场可近似为圆 形，所测长、短半轴长度的均值即为圆半径

如前所述，在D1-d和D3-d的观测日期之间，曾对全天相机进行了深入维护．若以图片Y方向的分辨率为单位对半径、中心X、Y坐标分别进行归一化处理，可得D1-d和D3-d的上述三量的归一化数值分别为[0.4289.0.7590,0.5048]和[0.4295,0.7611,0.5044]，二者的差异分别为 $[ 0 . 1 4 \%$ $0 . 2 8 \%$ ， $- 0 . 0 7 \%$ 1.由此可知，常规的维护作业对像场基本几何参数的改变是微小的，至少在云量分析中可以忽略.

# 4 测量天顶位置

# 4.1 测量原理

鱼眼镜头成像最显著的光学畸变就是圆形像场中的桶形像差．假设鱼眼镜头的桶形像差是轴对称的，并姑且忽略像场中心与天顶的偏差，那么，投影中桶形像差只对像点的极距有非线性的影响，并不改变极角，任意两个恒星像点对天顶投影点形成的张角是不受桶形像差影响的，应当与天球上的实际张角相同．依据这个原理，首先，选取若干枚恒星，在图像上测量其坐标，同时，使用虚拟天文馆得到其地平经纬度．然后在天顶区域构建一个网格，逐格点计算各恒星像点对格点所形成的张角，并与虚拟值进行比较．当实测张角与虚拟张角最为接近，即二者的差异在网格局部区域的二阶曲率为正时，则可判定该格点对应着天顶

在选取恒星时，应当本着以下三个原则:(1)低星等．该全大相机使用的是商业CCD而不是星敏感器，只对低星等恒星才能准确响应.(2)孤立．相比于天文望远镜，全天相机的像元分辨率是相当低的，定位精度约为 $4 ^ { \prime }$ ，不能有效区分星团、双星、或数密度大的天区．挑选孤立、与背景有较高反差的恒星，便于识别.(3)中等纬度．高地平纬度的恒星与天顶的角距离较近，在计算极角时对测量误差较为敏感；而低地平纬度恒星光程较长且成像受镜头像差影响较大，二者均不宜选作本实验的样本，

基于上述分析，我们使用小(\~10)、中(\~50)、大(\~200)三个容量的恒星样本，分别测量了天顶位置．下面，首先以小容量样本介绍计算步骤，然后介绍三个恒星样本的计算结果.

# 4.2选取恒星样本

2016-10-20日无名山气象条件较为理想，全天相机工作正常，获得了时序稳定、图像清晰的时间序列．在日落 $( 1 8 { : } 3 9 ^ { 2 } )$ 与月亮升起(22:41)之间，天空中没有强光源干扰，各天区的星空均较为清晰，满足本研究的需要．经挑选，采用于21:21:00 获取的图片(图4左)作为本研究的样本，记为D2-n(表1).

按照前文所述的原则，选取了9枚恒星，它们的地平纬度在30— ${ \cdot 6 0 } ^ { \circ }$ 左右，地平经度分布较为分散，记为样本 S2-9.采用二维高斯拟合测量其坐标，以下称为实测星场．图5中，在局部放大的反转图像上，方片标记了样本像点的位置．同时，在 Stellarium 虚拟天象软件中，获得恒星样本在D2-n拍照参数下的地平坐标值，以下称之为虚拟星场．表3列出了样本 S2-9在图像正交坐标系中的实测坐标、HIP(Hipparcos catalogue[2)编号、及其地平经纬度．图6在地平坐标中绘制了样本的位置．中心十字为天顶；箭头标记正北方向；刻度标记地平纬度，单位为度.

![](images/7e1cdec4388bbeee465be13f0a0aba3e73c115cd990dbe931fa26c262bfac312.jpg)  
图4(左）样本 D2-n,2016-10-20日 21:21:00 全天相机获取的夜间图像.(右)旋转后的实测星图. left:)Sample d2-n,the night skycaptured by theal-skycameraon 21:21:00of 2016-10-20.(right:)Rotated sta

![](images/5ac2a635472fb2bdb797b8998a2d83f8c553876fbdb740feb1494c7d6b053850.jpg)  
图5恒星样本S2-9像点的分布，用方片标记 5Distribution of stellar sample S2-9's image points (marked with spades).

![](images/e6c68e900a2e15167324df5775b39cbeb72c70843ae40f72ce38b0afde64b4eb.jpg)  
图6在地平坐标系中绘制的恒星样本S2-9(星号)的分布 Fig.6Star sample S2-9 (marked with asterisks) as plotted in a horizon coordinate system.

# 4.3计算天顶位置

从时间序列中初步确定天顶位于HIP109056和HIP107975 的中点附近．在虚拟和实测星场中分别测量这两颗恒星的坐标，记于表3的末两行．以它们的中点为中心选取一个边长约为 $4 ^ { \circ }$ 的方形区域，记为天顶候选区域Z，在图5中用箭头原点处的灰色矩形标记.

在区域Z构建一个网格，以对天顶进行精确的定位．在其所有格点中，样本恒星对格点张角的实测值与虚拟值最为接近的，就是天顶点．首先，对区域Z中的每一个网格点 $( \mathbf { x } , \mathbf { y } )$ ，计算第i和i-1颗恒星像点对其所形成的张角 $\theta ( \mathbf { x } , \mathbf { y } ) _ { \mathrm { i } }$ ．其次，根据各恒星方位角的虚拟值，计算第i和i-1颗恒星对真实天顶所形成的张角 $\theta _ { \mathrm { ~ i ~ } } ^ { \prime }$ ．然后，比较N 枚样本恒星张角数列的虚拟值和实测值的综合差异：

图7绘制了某次计算中网格内 $\delta ( \mathbf { x } , \mathbf { y } )$ 的坑状分布,X 和 $\mathrm { \Delta Y }$ 轴的坐标单位为0.02 像素，纵轴的单位为度. $\delta ( \mathbf { x } , \mathbf { y } )$ 的二阶曲率为正，这说明天顶确实在Z中．该坑的最低点具有最小的 $\delta ( \mathbf { x } , \mathbf { y } )$ 值，它就是图像的天顶位置.

考虑到，在对 $\delta ( \mathbf { x } , \mathbf { y } )$ 的数值计算中，各恒星的排序会影响计算的结果．这一方面是因为张角对中心点位置的敏感度与张角的大小成正比，另一方面是因为对恒星像点的测量有角分级（像素尺度）的误差．为了减小某特定排序中的随机误差，将多次计算结果的重心作为天顶．在图8所示的计算结果中，共进行了1024次计算，每次使用随机函数对样本 S2-9中的恒星进行随机排序，共得到1024个天顶候选位置，它们分布在一个 $4 { \times } 4$ 像素的矩形区域内，候选天顶的平均 $\delta ( \mathbf { x } , \mathbf { y } )$ 为 $0 . 3 9 ^ { \circ }$ ．该图的中央方片符号为散点的重心，格点间距为0.02像素，坐标单位为像素．去除1.5倍标准差以外的离群值并取平均值后，得到天顶位置：(1294.87,853.50)像素．使用不同的网格密度、离群值剔除标准no、计算次数，对样本 S2-9进行了多次计算，所得天顶坐标只有亚像素级的差异，如表4所列．在图5上，小十字标记从天顶候选区域Z(灰色方块)中遴选出来的天顶；三角号标记全天相机圆形像场的中心；背景是图像 $\scriptstyle \mathbf { D } 2 \cdot \mathbf { n }$ 的相应区域；坐标单位为像素.

# 4.4 使用较大容量样本的计算结果

在D2-n 星图上另选取了一个含有204枚恒星的样本 S2-204，并重新计算了天顶坐标，结果列于表4.在使用不同参数的多次计算中，散点均形成了聚合的团簇，综合所得天顶坐标仍然只有亚像素级的差异，但是天顶在X、Y方向与S2-9的计算结果均有约3像素的位移．此差异是由样本造成的，对恒星像点位置测量的随机误差在高纬度天区得到了放大并进而影响到天顶的定位，与计算参数的设置基本无关．因为这两个恒星样本的容量有数量级的差异，我们认为S2-204 的结果更可靠．在表4第10行所列的计算中，选用了较小的格点间距和no，遂采用为天顶坐标：( $( 1 2 9 8 . 0 3 \pm 0 . 3 4 , 8 5 6 . 6 0 \pm 0 . 3 8 )$ ．以图像Y方向的长度为单位，归一化天顶坐标为 $( 0 . 7 5 1 1 8 { \scriptstyle \pm 0 . 0 0 0 2 0 } .$ （20$0 . 4 9 5 7 2 { \scriptstyle \pm 0 . 0 0 0 2 2 ) }$ =

![](images/f50e7f662cf47886064795b0fdf926a1d51675825690cd02a756634448ebcc32.jpg)  
图7天顶区域Z网格内 $\delta ( \mathbf { x } , \mathbf { y } )$ 的坑状分布 Fig.7Pit-shaped distribution of $\delta ( \mathbf { x } , \mathbf { y } )$ in the Zenith region Z grid.   
图8使用样本S2-9计算所得的候选天顶点 Fig. 8 Distribution of computed candidate zenith,with its centroid marked with a spade.

856 11111111 + + + + + + 855 地 + + # 办 +# 能 多 + 中 854 + xid/ L 福 绿 出 ≠+ 853 清 中 + 1 + ++ T + + 1 + + + + + 852 ++ + + ＋ + + + + + + 1 + + 851 L 上 1292 1293 1294 1295 1296 1297 1298 X/pixel

# 4.4相机的竖直姿态偏差

测量相机的光轴与天顶的偏差，是本研究所要解决的重要实际问题．首先，使用Z区域的HIP109056 和HIP107975作为参考点，依据二者星点的角距离和像点的距离，求得相机在天顶区域的平均空间分辨率为 $0 . 1 1 4 5 ^ { \circ }$ 像素-1．由此可得，图像的天顶位置(1298.03,856.60)与像场中心(1311.48,872.22)的角距离为 $2 . 3 6 ^ { \circ }$

针对 2017年05月底相机姿态被调整的情况，我们使用D3-n星图另采集了一个含有40枚恒星的样本 S3-40,代表性结果列于表4第11行．天顶位置与像场中心的角距离达 $7 . 6 4 ^ { \circ }$ ，该次维护作业明显加大了竖直姿态偏差.

# 5测量旋转角

全天相机的旋转角 $\psi$ ，即图像纵轴与测者子午线正北方向的夹角，可以根据恒星样本方位角的虚拟值和实测值的差值求得.

$$
\Psi = \mathrm { m e a n } ( \{ \Phi _ { \mathrm { i } } - \Phi _ { \mathrm { i } } ^ { \prime } \} ) , \qquad 0 \leq \mathrm { i } \leq \mathrm { N } .
$$

上式中， $\Phi _ { \mathrm { i } }$ 和 $\phi _ { \mathrm { i } } ^ { \prime }$ 分别是在实测星场和虚拟星场中恒星i的方位角.S2-9 和 S2-204 的旋转角分别为 $1 5 2 . 7 4 { \scriptstyle \pm 2 . 5 5 ^ { \circ } }$ 和 $1 5 2 . 7 1 { \scriptstyle \pm 1 . 5 8 ^ { \circ } }$ ．图9绘制了S2-204的 $\{ \Phi _ { \mathrm { { i } } } - \Phi _ { \mathrm { { i } } } ^ { \prime } \}$ ．图5和6中的实线箭头分别标记了实测与虚拟星图的正北方向，箭头与Y轴的夹角是图像的旋转角．将原始图像旋转 $\psi$ 后，二者重合．图4(左)和(右)分别是旋转前后的样本D2-n.小十字标记天顶，坐标单位为像素．在图4(右)中，图像纵轴为正北方向．这样就制成了符合行业规范的图片和动画.

在对S3-40样本的计算结果中(表4)，其旋转角为 $1 8 5 . 7 8 ^ { \circ }$ ，与 $\mathbf { D } 2 \mathbf { - n }$ 的测量结果有较大差异．在近年的使用中，每次开箱维护都会改变旋转角.因此，在每次维护之后都应当重新测量旋转角并反馈给数据处理程序。

![](images/0ad0601be033645e0eedc9bd3d4c2de311c23debc22af0dea14bf74ad26b8671.jpg)  
图9用样本S2-204计算图像D2-n 的旋转角Fig.9 Calculation of night image D2-n's rotation angle with star samples S2-204.

# 6结论与讨论

# 6.1结论

我们使用无名山全天相机于2016年10月和2017年06月获得的4组全天图像，采集了容量分别为9、40、204 的恒星样本，从虚拟天文馆获得了恒星的地平坐标，通过像场对姿态参数进行了精确的测量．主要结果为：(1）开发了一种基于虚拟天文馆计算恒星坐标功能的测量方法，使姿态测量建立在容量较大的参考恒星上，为全天相机图像的深入处理分析奠定了基础。特别是，采用网格法对天顶的定位达到了亚像素的精度，有望满足陨星和航空器等高定位精度监测的需求．该方法对相机的视场、像差、可见天空角面积等参数没有依赖性，具有较强的可移植性。

(2）提高相机姿态精度的首要任务是减小光轴的天顶角，而对相机的维护作业可能会造成光轴与天顶有不可忽略的偏差．按 2016-10-20 日全天相机的姿态，像场的天顶坐标为:(0.75118±0.00020,0.49572±0.00022)，与像场中心的夹角为 $2 . 3 6 ^ { \circ }$ ；而在2017-06-05 的数据中，二者的夹角达到 $7 . 6 ^ { \circ }$

(3）常规维护作业对像场几何参数的改变甚微 $( \leq 0 . 2 8 \% )$ ，在一般图像分析中可以忽略．无名山全天相机的像场呈正圆形．以图像Y方向的长度为单位，其半径和中心坐标分别为0.4289 和(0.7590、0.5048).

(4）测量了图像的旋转角并在可视化产品中按制图惯例进行了旋转．每次维护相机都可能改变旋转角，并需要重新测量.

# 6.2讨论

本测量的主要误差来源是：(1）单帧图像中恒星像点的定位误差。夜间长时间曝光(\~30s)和视宁度的时空不均匀性等均可造成偶然误差.(2）光学系统的桶形像差。由于光轴倾斜，光学投影的径向非线性被传导到切向，在测量结果中形成了系统误差．在进一步的工作中，可以采用升级硬件以缩短曝光时间、综合多帧测量结果、改进测星方法等手段抑制偶然误差；通过测量镜头径向畸变参数，在预处理中将图像矫正为等角投影，以抑制系统误差.

影响全天相机像场的首要姿态偏差是其光轴与天顶的夹角．如果光轴不竖直，不仅对视场和投影的轴对称性都会造成系统性的影响，而且每次在维护后都需要重新测量姿态．如果能在设计和施工中大幅度提高竖直方向的姿态精度和稳定性,在野外使用中光轴的天顶角一直符合监测任务的精度要求，那么，只需要测量新的旋转角就可以了.

在天文观测中，一个潜在的误差来源是观测设备的时钟误差．由于天球旋转的速度是 $3 6 0 ^ { \circ } \mathrm { d } ^ { - 1 }$ 即 $1 5 ^ { \prime \prime } s ^ { - 1 }$ 时钟误差0.1s就会造成角秒级的定位误差．但是，对于无名山全天相机而言，按照天顶区域 $0 . 0 5 7 2 ^ { \circ }$ 的像元分辨率 $\langle 5 1 8 4 \times 3 4 5 6 \rangle$ ），时钟误差达到13.7s方能造成像素级的定位误差．无名山全天相机使用互联网时钟对工控机内置时钟进行校准，其精度完全可以满足恒星定位的需要，

天文导航技术的发展，为本研究的进一步深入提供了很多可借鉴的方法．本研究与天文导航的研究具有一定的异同．一方面，天文导航的测量目的是定位，要求准实时性；而本研究的测量目标是地基设备的姿态，对时效性要求不高，但期望在类似设备中具有较强的可移植性．另一方面，二者都主要解决实测星场的获得、矫正和比较计算．全天相机充足的恒星样本容量，提高了结果的可靠性，并为深入分析提供了可能．如果在后续研究中需要采集大容量的恒星样本，可以从天文导航的研究中借鉴成熟的从星图中批量获取和比较恒星坐标的方法[27.28]，并开发4从虚拟天文馆中自动输出坐标矩阵的接口软件，我们将在后续研究中有针对性的改进数据压缩方法，开展对全天相机光学系统的分析和矫正，并提高对数据格式、图像瑕疵和气象条件的适应能力，以期把本研究移植到类似设备.

致谢 无名山观测站在次仁汪堆、洛绒次称、宋其武等同志的辛苦劳作下得以稳定运行，在此深表谢忱.

表1本研究使用的全天相机监测数据Table 1Data of all-sky camera used in this study  

<html><body><table><tr><td>日期</td><td>时间a</td><td>分辨率</td><td>间隔时长b</td><td>帧数</td><td>天气</td><td>测量对象</td><td>编号</td></tr><tr><td>2016年10月05日</td><td>06:29:11-19:52:38</td><td>2592×1728</td><td>5.05 min</td><td>7</td><td>多云间晴</td><td>视场边界</td><td>D1-d</td></tr><tr><td>2016年10月20日</td><td>21:21:00</td><td>2592×1728</td><td>5.05 min</td><td>1</td><td>晴</td><td>相机姿态</td><td>D2-n</td></tr><tr><td>2017年06月05日</td><td>02：20:55-22:39:22</td><td>5184×3456</td><td>4.09 min</td><td>4</td><td>晴转多云</td><td>视场边界</td><td>D3-d</td></tr><tr><td>2017年06月05日</td><td>03:54:58</td><td>5184×3456</td><td>4.09 min</td><td>1</td><td>晴</td><td>相机姿态</td><td>D3-n</td></tr></table></body></html>

(a）对含有多帧图像的数据组，此处列出起止帧的时刻，下同.(b）全天相机在该日采集时间序列的时间间隔.

表2全天相机像场的实测几何参数  

<html><body><table><tr><td>数据编号</td><td>分辨率</td><td>长半轴a</td><td>短半轴</td><td>圆半径</td><td>中心横坐标</td><td>中心纵坐标</td></tr><tr><td>D1-d</td><td>2592×1728</td><td>741.25</td><td>741.02</td><td>741.14</td><td>1311.48</td><td>872.22</td></tr><tr><td>D3-d</td><td>5184×3456</td><td>1485.63</td><td>1483.18</td><td>1484.40</td><td>2630.20</td><td>1743.16</td></tr></table></body></html>

(a）长度单位均为像素.

Table 2Geometric parameters of all-sky camera's image field   
表3恒星样本S2-9的实测和虚拟参数  
Table 3Measured and virtual parameters of star sample S2-9   

<html><body><table><tr><td>序列号</td><td>X坐标a</td><td>Y坐标</td><td>HIP 编号</td><td>地平经度b</td><td>地平纬度</td></tr><tr><td>0</td><td>1641</td><td>1236</td><td>113368</td><td>165°07'45.6"</td><td>29°40'22.6"</td></tr><tr><td>1</td><td>1797</td><td>1012</td><td>3419</td><td>134°26'36.5"</td><td>28°21'44.1"</td></tr><tr><td>2</td><td>1264</td><td>1285</td><td>100345</td><td>211°27'04.7"</td><td>40°16'36.3"</td></tr><tr><td>3</td><td>1293</td><td>519</td><td>746</td><td>27°02'28.4"</td><td>52°32'56.7"</td></tr><tr><td>4</td><td>1679</td><td>569</td><td>9884</td><td>80°07'24.3"</td><td>34°34'05.2"</td></tr><tr><td>5</td><td>1588</td><td>797</td><td>1067</td><td>106°37'54.3"</td><td>56°00'25.4"</td></tr><tr><td>6</td><td>1110</td><td>1114</td><td>97649</td><td>242°25'22.5"</td><td>53°55'30.6"</td></tr><tr><td>7</td><td>1111</td><td>766</td><td>102098</td><td>322°08'55.6"</td><td>67°45'51.9"</td></tr><tr><td>8</td><td>919</td><td>855</td><td>91262</td><td>296°59'40.3"</td><td>47°37'09.5"</td></tr><tr><td></td><td>1281</td><td>856</td><td>107975</td><td>260°11'39.3"</td><td>88°41'05.5"</td></tr><tr><td>二</td><td>1303</td><td>844</td><td>109056</td><td>91°43'00.0"</td><td>88°25'55.4"</td></tr></table></body></html>

(a)X、Y是图像D2-n上恒星像点的正交坐标，单位为像素.(b）样本恒星在图像D2-n拍摄时刻的地平经纬度，由虚拟天文馆计算所得.(c)HIP107975和HIP109056仅用于圈定天顶的位置范围，在计算天顶时并不作为参考恒星.

表4天顶和旋转角的计算结果 Table 4 Results of the computation of zenith and rotation angle   

<html><body><table><tr><td colspan="3">恒星样本</td><td colspan="3">计算参数</td><td colspan="3">计算结果</td></tr><tr><td>编号</td><td>星图</td><td>容量</td><td>格点间距a</td><td>nb</td><td>计算次数</td><td>天顶横坐标</td><td>天顶纵坐标</td><td>旋转角</td></tr><tr><td rowspan="5">S2-9</td><td rowspan="5">D2-n</td><td rowspan="5">9</td><td>0.50</td><td>2.0</td><td>512</td><td>1294.91</td><td>853.43</td><td>152.75</td></tr><tr><td>0.20</td><td>2.0</td><td>512</td><td>1294.84</td><td>853.50</td><td>152.74</td></tr><tr><td>0.10</td><td>2.0</td><td>512</td><td>1294.82</td><td>853.41</td><td>152.74</td></tr><tr><td>0.02</td><td>1.5</td><td>1024</td><td>1294.87</td><td>853.50</td><td>152.74</td></tr><tr><td>0.01</td><td>2.0</td><td>32</td><td>1294.99</td><td>853.61</td><td>152.74</td></tr><tr><td rowspan="5">S2-204</td><td rowspan="5">D2-n</td><td rowspan="5">204</td><td>0.50</td><td>1.5</td><td>1024</td><td>1298.04</td><td>856.64</td><td>152.71</td></tr><tr><td>0.10</td><td>1.5</td><td>256</td><td>1297.93</td><td>856.47</td><td>152.71</td></tr><tr><td>0.05</td><td>1.5</td><td>512</td><td>1298.02</td><td>856.53</td><td>152.71</td></tr><tr><td>0.02</td><td>5.0</td><td>1024</td><td>1297.65</td><td>855.66</td><td>152.71</td></tr><tr><td>0.02</td><td>1.5</td><td>1024</td><td>1298.03</td><td>856.60</td><td>152.71</td></tr><tr><td>S3-40d</td><td>D3-n</td><td>40</td><td>0.05</td><td>3.5</td><td>256</td><td>2561.85</td><td>1627.99</td><td>185.78</td></tr></table></body></html>

(a）格点间距和天顶坐标的单位均为像素，旋转角的单位为度.(b)n是剔除离群值的标准.距离散点重心大于no的点被视为离群点，o是标准差.(c）每次计算中，对样本恒星进行随机排序，结果是剔除离群点之后的均值.(d）仅列出一代表性结果.

# References

[1] 高太长，刘磊，赵世军，等．全天空测云技术现状及进展 [J].应用气象学报,2010,21(1):101-109.   
[2] KAZANTZDSA,ZOUMANKAP,LANCP,etal.5-Short-terforecastingbasedonal-scameras [C]/RenewableEergy Forecasting. 2017.   
[3]CHAUVIR,NOUJ,THLS,etal.Clouddetectiomethodoogbasedoaskyimagingsystem[C/IterationalConereceon Concentrating Solar Power and Chemical Energy Systems, SolarPACES 2014.2015.   
[4]SHIELDSJEJOHNORW,KARRME,etal.Daylghtisible/Nole-skymagersfoudanddiancemoitoringinuprtfUV research programs [C]// Ultraviolet Ground-and Space-based Measurements,Models,and EffectsII. 2003.   
[5]YAMASHTAM,YOSHMURAM,NAKAHZUKAT.Cloudcoverestimationusingultitemporalhmispereimageries[C]//XXthSPR Congress. 2004.   
[6] 霍娟，吕达仁．全天空数字相机观测云量的初步研究[J]．南京气象学院学报,2002,25(2):242-246.   
[7]YABUKIM,OBAM,NAKAK,etaDeveloptfoddetectioetodfrohoskyoloriages[J].aiece 2014,8(4):315-326.   
[8]TUOMINENP,TUONONENM.Clouddetectionand movementestimationbasedonskycameraimages usingneuralnetworksndthe Lucas-Kanade method [C]// SolarPACES 2016.2017.   
[9]LIUS,ZHeutoticdtifggetatioede Sensing Letters,IEEE,2015,12(2):354-358.   
[10]DURISCOEDM,LUGNBUHLCB,MOORECA.Measuringnight-skyrightesswithawidefieldCCDcamera[J].Publicatiosofthe Astronomical Society of the Pacific,2007,119(852):192213.   
[1]SItlsodttt [C] //Revista Mexicana de Astronomia y Astrofisica Conference Series.2011.   
[12] 彭焕文，辛玉新，和寿圣，等．丽江天文观测站全天相机介绍 [J].天文研究与技术,2015,12(1):89-95.   
[13] 田健峰，邓李才，闫正洲，等.中国 SONG项目节点全天云量监测方案[J].天文学报,2016,57(3):366-375.   
[14] 尹佳，姚永强，王红帅，等．天文选址的夜间云量处理方法 [J].天文学报,2012,53(3):230-239.   
[15]李小波，刘煜，宋腾飞，等．川西无名山天文址点定点监测平台的运行介绍 [J].云南大学学报(自然科学版),2017,39(S2):180-186.   
[16]PETRSON,C.TheColoradoal-skycameranetwork[C]//Proceedingsofthe InterationalMeteorConference210.2011.   
[17] 李崇辉.基于鱼眼相机的舰船天文导航技术研究[D].郑州:解放军信息工程大学,2013.   
[18] 孙剑明.基于星图识别的舰船天文导航关键技术研究 [D]．哈尔滨:哈尔滨工程大学,2013.   
[19] SZALAY A,GRAYJ.The world-wide telescope [J]. Science,2001,293:2037.   
[20]DJORGOKSG,WAR.Virtualbseatory:fromcocepttoimplementationC/FoClarkLaketotheLngWavelegtha Bill Erickson's Radio Science.2005.   
[21]崔辰州，于策，肖健，等．大数据时代的天文学研究[J].科学通报,2015,60:445-449.   
[22] 吴宁，刘煜，赵红梅．川西无名山天文址点GIS 分析研究 [J].天文学报,2016,57(6):729-745.   
[23]SONGTF,W,Y,eal.utoaticsoeingsetiosatMtWuganiestei[J]aris,, 293(2):37-51.   
[24]LUY,IXtetoalgstCt Processes,and Systems VII.2018.   
[25]BERGLUK,EAAN,RUsingfr,peouceStellusoftwarefr9CScieceEucatioOutrachFog Path to the Future.2011.   
[26]PERRYMANMAC,IDEGRENL,KOVLEVSKYJ,etal.TheHPPACOScatalogue[J].Astroo&Astropysics,99,:49.   
[27]张广军．星图识别[M].北京:国防工业出版社,2011.   
[28] 张喆，翟京生，张亮.基于圆形视场分割的鱼眼相机星图识别方法 [J]．应用光学,2018,39(04):505-510.