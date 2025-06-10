# 双目立体显示技术在月表形貌三维可视化中的应用

高兴烨1,2,3，刘建军1,3，任鑫1,3，牟伶俐1,3，李春来1,3（1.中国科学院国家天文台，北京100012；2.中国科学院大学，北京100049;3.中国科学院月球与深空探测重点实验室，北京100012)

摘要：基于嫦娥二号探测器获得的地形及影像数据，将双目立体显示技术应用于月表形貌三维可视化中，构建了月球三维立体可视化系统。介绍了双目立体显示原理，并对月球三维立体可视化系统的具体实现进行了详细的介绍。首先论述了系统的设计方案及硬件环境;接着论述了月球海量地形数据的组织方式和实时渲染方法；最后采用离轴模型的双目立体显示方法，实现了舒适的立体效果。月球科普及科研应用表明，系统具有良好的实用价值。

关键词：嫦娥二号探测器；双目立体显示；月球三维可视化中图分类号：TP391.9 文献标识码：A 文章编号：1672-7673(2016)03-0358-08

自2007年我国成功发射第一颗绕月探测器嫦娥一号以来，我国已经成功开展了三次月球探测活动，获取了大量珍贵的月球影像数据。嫦娥一号探测器在一年多的绕月探测任务中利用搭载的三线阵CCD相机，获取了 $1 2 0 \mathrm { m }$ 分辨率的全月球影像，经嫦娥工程地面应用系统工作人员的精心处理，获得了空间分辨率 $5 0 0 \mathrm { ~ m ~ }$ 的全月球数字高程模型（Digital Elevation Model，DEM）。嫦娥二号探测器在半年多的绕月探测中，利用搭载的两线阵CCD相机获得了 $7 \mathrm { m }$ 分辨率的全月球影像数据以及32轨米级分辨率的虹湾地区影像数据，经地面应用系统工作人员的精心处理，获得了空间分辨率达 $2 0 ~ \mathrm { m }$ 的全月球数字高程模型数据。2013年12月14日，嫦娥三号探测器将我国首个着陆器和月兔号巡视器送抵月球表面，开始开展月表就位探测和巡视探测活动。至今，利用月兔号巡视器搭载的全景相机已获取了大量着陆点周围的月球数据。三次成功的月球探测活动，在我国拥有自主月球探测数据的同时，弥补了国外获取的月球影像数据不清晰、不全面的不足，为人们真实全面地了解月球形貌提供了良好的数据基础。基于清晰全面的嫦娥探测器影像数据和高分辨率数字高程模型数据，进行月球形貌三维可视化研究，以直观便捷的方式帮助人们认识月球、了解月球，有助于人们对月球开展更深入的定量定性研究；对于我国更好地开展月球探测活动，也具有重要意义。基于嫦娥探测器数据，国内学者开展了大量的月球形貌可视化研究工作。文[1]基于嫦娥一号地形数据制作了三维月球形貌图；文［2]基于嫦娥一号CCD 相机数据和激光高度计数据制作了月球三维可视化系统；文[3］基于嫦娥一号地形数据及影像数据构建了嫦娥二号在轨运行视景仿真系统；文[4]对WebGIS技术应用于月球可视化的关键技术进行了论述。在基于嫦娥探测器数据对月表形貌进行可视化的研究中，几乎所有可视化研究方法是采用二维平面进行显示，具有一定的局限性。

现实的世界是三维的世界，随着计算机技术的发展，基于双目立体显示的三维立体可视化技术取得了飞速的发展。与传统的二维显示技术相比，采用双目立体显示技术能够使人眼在二维显示平面获得立体视觉；双目立体显示技术能够以更符合人眼习惯的形式再现客观景物，使视者获得身临其境的临场感；双目立体显示技术显示的信息量更大，感染力更强，更逼真，更富于实感性和参与性[5]。双目立体显示技术是虚拟现实及可视化中的关键技术，在航天、医疗、教育、游戏、电影电视等方面具有广泛的应用[6-12]。

本文在介绍双目立体显示原理的基础上，将双目立体显示技术应用于月球形貌的三维立体可视化表达中，基于嫦娥二号地形及影像数据，结合四通道立体投影系统，实现了沉浸式的月球三维立体可视化系统，并选择离轴模型的双目立体显示方法，提供了更好的沉浸感，有效地辅助人们以更直观的方式了解月球的形貌特征。

# 1双目立体显示原理

在观察真实的三维世界时，双眼由于存在一定的瞳距，所看到的是现实世界投影于视网膜上具有一定视差的图像对，大脑通过调整眼球的运动，综合视差图像对信息，从而获得对物体距离的感知。双目立体视觉的原理即是根据人眼的立体视觉成像原理，仿真人眼的立体成像过程，根据人眼所处的相对屏幕的位置，利用计算机模拟仿真生成该处左右眼所看到的视差图像，并显示在屏幕上，再通过专门的双目立体显示硬件使人的左眼只看到仿真生成的左图像，右眼只看到仿真生成的右图像，以在大脑中形成立体视觉。下面分别对形成双目立体视觉的决定性因素——视差以及构建立体视觉的基础—双目立体显示硬件进行介绍。

# 1. 1 视差

视差是指屏幕上显示的左右视差图像的两个对应点的水平距离。视差决定了立体图像在大脑中的立体感受。通过对左右视差图像的视差大小调节，可以形成不同的立体视觉。根据视差在大脑中形成的不同立体感受，可将视差分为正视差、零视差、负视差和发散视差4类。

正视差：当视差图像上两个对应点的距离小于瞳距，而且两眼的视线不在屏幕前交叉时，就会产生正视差(图1(a)）。大脑通过融合这两个对应点，产生三维立体的点，看上去就像位于屏幕平面的后方空间。

零视差：在二维显示器上显示零视差的两个对应点重叠在一起，双眼观看时，这点显示在二维屏幕平面上(图1(b)）。

负视差：当左右视差图像上两个对应点的距离小于瞳距，而且两眼的视线在屏幕前交叉时，就会产生负视差(图1(c)）。大脑通过融合这两个对应点，产生三维立体的点，这样的立体点看上去就像漂浮在屏幕和人眼之间。

发散视差：当两个对应点的距离大于或等于瞳距，大脑无法对这两个对应点对焦，产生具有重影的立体像(图1(d)）。在这种情况下，人脑会本能地不断对图像对焦，即使很短一段时间，都会产生疲劳和不舒服的感觉。

![](images/24f36eb25d6697fee2edb66221aa818693592620d66e73d9dd57564c7d0b897a.jpg)  
图1屏幕视差  
Fig.1Screen parallax

# 1.2双目立体显示硬件

双目立体显示硬件是指利用光学等技术手段，保证左右双眼只能看到屏幕上对应的左右视差图像的辅助设备。根据双目立体硬件的实现原理，将立体硬件采用的技术分为以下几类：分色技术、分时技术、分光技术、空间划分技术，如图2。

# 2 月球三维立体可视化系统的设计及实现

本文基于双目立体显示的原理，结合计算机图形学知识，设计及构建了月球三维立体可视化系统。

# 2.1月球三维立体漫游系统的构建流程

本文采用嫦娥二号 $7 \mathrm { m }$ 分辨率的正射影像数据及 $2 0 \mathrm { ~ m ~ }$ 分辨率的数字高程数据构建了可实时交互漫游的月球形貌三维立体可视化系统。整个系统的构建流程如图3。

首先将月表 $2 0 \mathrm { ~ m ~ }$ 分辨率的数字高程数据及月球数据进行预处理，生成全月球的地形模型数据库；再将地形模型数据加入月球三维立体可视化系统，根据视点位置动态加载地形数据块，并

![](images/70907c0fb5b11de2e6a53149e9e78debbbf3f81e1a231a83bb4747f2352d634a.jpg)  
图2双目立体显示硬件  
Fig.2Hardware for binocular stereo display

基于双目视点的离轴模型完成立体渲染；最后将渲染的左右视差图像信号输出到四通道立体投影系统进行立体投影显示。

![](images/b6a5c09a98b06cd82a25ccd3af16f12c6b894079346e0f0262a87a1c7d44cbff.jpg)  
图3月球三维立体可视化系统的构建流程  
Fig.3Framework of the stereo display system of virtual Moon

# 2.2月球三维立体漫游系统立体硬件环境介绍

月球立体漫游系统以沉浸式四通道立体投影系统为展示平台（图4)。该系统的硬件配置如下：

4 台支持主动立体显示的无缝融合的巴可投影机，亮度26000 流明，刷新率为 $1 2 0 \ \mathrm { H z }$ ；投影巨幕弧长 $3 1 \mathrm { ~ m ~ }$ ，高 $5 . 5 \mathrm { ~ m ~ }$ ，弧度 $1 2 0 ^ { \circ }$ ；信号同步矩阵1台；惠普 Z820 图形工作站1台，外接Quadro Plex显卡；立体信号发射器1台及快门式立体眼镜若干。

该硬件系统采用支持 Nvidia的3DVision 分时技术的Quadro Plex 显卡，实时渲染交替输出4路左右立体视频信号，经同步矩阵将4路视频的立体信号同步后，分别输出到4台无缝拼接的立体投影仪，以 $1 2 0 \ \mathrm { H z }$ 的刷新率进行立体投影显示，同时立体信号发射器发射立体同步信号，立体眼镜进行同步响应，保证观看者的左眼只能看到左像，右眼只能看到右像，形成立体视觉。

# 2.3地形数据的组织及渲染

嫦娥二号数字高程数据及数字正射影像图（Digital Orthophoto Map，DOM)达到TB级，不可能将其一次性载入计算机内存，必须对数据进行有效的组织和动态调度，才能实现全月球的实时交互漫游和渲染显示。

本文通过对数字高程数据及数字正射影像数据进行预处理构成地形模型块，并以四叉树的组织方式对地形块进行组织，具体的数据组织方式如图5。先将全球数据分为东西两个半球，然后沿着经纬线将东西两个半球递归四等分，以四叉树的结构进行组织管理。每个四叉树的结点悬挂一个地形单元，此地形单元由256像素 $\times 2 5 6$ 像素的影像块和地理位置与影像块对应的地形块融合构成。

![](images/dccf74d0beea0102d67ec05d939e36c08eb2b2166a022843e6629ac0db491fca.jpg)  
Fig.4Structure diagrams of 4-pipe-projection stereo system

![](images/3d63e018a0e85773171f4ee04d977fd6982ef7fa27bcc6f53c2ff75cb44c13d3.jpg)  
图44通道立体投影系统结构图  
图5全月球地形数据四叉树组织结构图  
Fig.5Quadtree organization mode for terrain data of the Moon

本文采用层次细节模型(Levelof Detail Model，LOD)渲染算法动态调度地形单元完成渲染。层次细节模型渲染算法是指在场景中进行模型绘制时距离视点越远的地方分辨率越低，距离视点越近的地方分辨率越高，而且随着视点的变化，场景的变化具有连续性，这样即能保证显示大规模数据的流畅性，又不影响显示的效果[13]。

2.4双目视点模型的选择和立体显示的实现

在虚拟月球模型建模完成后，需要选择合适的双目视点模型完成立体场景的渲染，才能达到良好的月球立体漫游效果。

# 2.4.1双目视点模型的选择

在虚拟场景中，根据双眼视差原理，设置具有水平距离并内聚的左右视点，再将视点所见的虚拟场景投影变换在二维屏幕上立体显示，利用这种方法构建的双目视点模型，称为内束模型（图6（a)）。内束模型不能形成良好的立体效果，它的重要缺陷是引入垂直视差并造成了水平深度面的变形[14]。离轴模型是内束模型的改进（图6(b)）。离轴模型在保持左右视点视线平行的同时，将两个视点投影后的图像向相反的水平方向移动，形成立体视差图像。移轴模型在保证双眼视线平行的同时，通过设置两个非对称的视见体实现。图6(b)中阴影部分代表非对称的视见体。采用离轴模型投影后形成的左右视差图像不但没有引进垂直视差，还解决了深度面的变形问题。

![](images/7a02106cbadac1eedf386194093da92bb7b947f4517dcebd9c46e431429dc457.jpg)  
图6内束模型和离轴模型 Fig.6Toe-in model and off-axis model

# 2.4.2 三维立体可视化的实现

计算机中虚拟世界的三维效果利用将虚拟场景的三维坐标经视点变换后再经透视投影到二维平面实现。三维立体可视化的实现，首先需要根据离轴模型原理构建水平偏移原视点的左右两个视点，同时利用错切矩阵乘以原透视投影矩阵，对原透视投影矩阵进行错切变换；然后再将虚拟世界的三维坐标分别乘以经平移变换后的左右视点矩阵的逆矩阵，再乘以经错切变换后的左右视点投影矩阵，将虚拟三维世界投影成为具有左右视差的立体图像；最后分别将得到的左右视差图像交替显示输出。视点变换矩阵及投影变换矩阵的平移及错切变换过程如下：

LeftViewMatrix $\mathbf { \Sigma } = \mathbf { \Sigma }$ LeftTranslationMatrix $\times$ ViewMatrix ; LeftProjectionMatrix $\mathbf { \tau } = \mathbf { \tau }$ LeftShearMatrix $\times$ ProjectionMatrix ; RightViewMatrix $\mathbf { \tau } = \mathbf { \tau }$ RightTranslationMatrix $\times$ ViewMatrix ; RightProjectionMatrix $\mathbf { \tau } = \mathbf { \tau }$ RightShearMatrix $\times$ ProjectionMatrix ; 其中，LeftViewMatrix 和RightViewMatrix为变换后左右视点的变换矩阵；ViewMatrix为原视点变换矩 阵；LeftTranslationMatrix和RightTranslationMatrix分别为将视点向左右平移的平移矩阵；LeftProjection 和RightProjection为变换后左右视点的投影矩阵；ProjectionMatrix为原透视投影矩阵；ShearLeftMatrix 和ShearRightMatrix为将原透视投影进行错切变换的左右视点对应的错切变换矩阵。

其中，LeftTranslateMatrix和RightTranslateMatrix两个平移矩阵分别为

$$
\begin{array}{c} { \left\{ \begin{array} { l l l l l l } { 1 . 0 } & { 0 . 0 } & { 0 . 0 } & { 0 . 0 } \\ { 0 . 0 } & { 1 . 0 } & { 0 . 0 } & { 0 . 0 } \\ { 0 . 0 } & { 0 . 0 } & { 1 . 0 } & { 0 . 0 } \\ { { \Biggl [ } { \frac { I P D } { 2 } } } & { 0 . 0 } & { 0 . 0 } & { 1 . 0 } \end{array} \right] }  \end{array} \{array { \left\{ \begin{array} { l l l l l l } { 1 . 0 } & { 0 . 0 } & { 0 . 0 } & { 0 . 0 } & { 0 . 0 } \\ { 0 . 0 } & { 1 . 0 } & { 0 . 0 } & { 0 . 0 } \\ { 0 . 0 } & { 0 . 0 } & { 1 . 0 } & { 0 . 0 } \\ { { \Biggl [ } { \frac { I P D } { 2 } } } & { 0 . 0 } & { 0 . 0 } & { 1 . 0 } \end{array} \right] }
$$

LeftShearMatrix和RightShearMatrix两个错切矩阵分别为

$$
\left\{ \begin{array} { l l l l l l } { 1 . 0 } & { 0 . 0 } & { 0 . 0 } & { 0 . 0 } \\ { 0 . 0 } & { 1 . 0 } & { 0 . 0 } & { 0 . 0 } \\ { \displaystyle \frac { I P D } { 2 } } & { 0 . 0 } & { 1 . 0 } & { 0 . 0 } \\ { 0 . 0 } & { 0 . 0 } & { 0 . 0 } & { 1 . 0 } \end{array} \right\} \# \mathbb { F } \mathbb { H } \left\{ \begin{array} { l l l l l } { 1 . 0 } & { 0 . 0 } & { 0 . 0 } & { 0 . 0 } \\ { 0 . 0 } & { 1 . 0 } & { 0 . 0 } & { 0 . 0 } \\ { 0 . 0 } & { 0 . 0 } & { 1 . 0 } & { 0 . 0 } \\ { - \displaystyle \frac { I P D } { 2 } } & { 0 . 0 } & { 1 . 0 } & { 0 . 0 } \\ { 0 . 0 } & { 0 . 0 } & { 0 . 0 } & { 1 . 0 } \end{array} \right\}
$$

以上矩阵中 $I P D$ (Inter-Pupillary Distance）为双眼视差。合适的双眼视差受视点的视场角、虚拟场景尺寸、显示屏幕大小和显示屏幕距离等因素共同影响[15]。

月球三维立体可视化系统渲染时采用QuadBuffer四缓冲渲染技术。渲染左视点视图到左后缓冲区，渲染右视点视图到右后缓冲区，交替渲染左右视点图像。同时为避免闪烁，交换左后缓冲区到左前缓冲区，交换右后缓冲区到右前缓冲区，完成左右渲染图像交替显示。基于离轴模型渲染的立体月球效果如图7（此时双眼视差设定值为 $0 . 0 0 6 \mathrm { ~ m ~ }$ ）。

![](images/68b65e2b2644fb5bb059e5d97097f79f451bc59d64aeebab2e93db8785127076.jpg)  
图7月球三维立体可视化系统红绿立体效果图  
Fig.7Anaglyph images of stereo display system of virtual Moon

# 3系统成果

本文将双目立体显示技术应用于全月球形貌可视化研究中，结合4通道立体投影系统，基于嫦娥二号数字高程数据及数字正射影像数据，采用OpenGL 图形库，设计实现了具有良好立体效果的月球三维立体可视化系统。该系统配合 $1 : 1$ 的巡视器模型及投影地幕系统(图8)仿真构建的沉浸式月表虚拟探测场景，多次接待中小学生、学者、外国友人、媒体等，为科学普及月球知识，宣传嫦娥工程的科学成果发挥了重要作用。随着我国深空探测的深入及进一步发展，双目立体显示技术必将在深空探测数据的三维立体可视化中得到更广泛的应用。

![](images/13948190e0421fe25649827d905fcadb1b434d6c2b99691bb6ec9ee407f8b75f.jpg)  
图8月球三维立体可视化系统结合投影地幕及月球车模型构建的月表虚拟探测场景 Fig.8Virtual scene of lunar surface probe composed by stereo display system of virtual Moon，lunar rover model and ground screen

# 参考文献：

[1] 邹小端，刘建军，李春来.基于嫦娥一号观测数据的月球形貌可视化技术［J].空间科学学报，2011，31(1)：100-105.Zou Xiaoduan，Liu Jianjun，Li Chunlai.Applications of the visualization of lunar surface basedon Chang'E-1 observations [J]. Chinese Journal of Space Science，2011，31(1）:100-105.  
[2] 左维，刘阳，任鑫，等.基于嫦娥一号CCD相机和激光测距数据的月球三维可视化系统[J]．计算机辅助设计与图形学学报，2012，24（1)：37-42.Zuo Wei，Liu Yang，Ren Xin，et al.Design and implementation of three-dimensionalvisualization of the Moon based on Chang'E-1 data of CCD camera and laser altimeter [J].Journal of Computer-Aided Design & Computer Graphics，2012，24(1） : 37-42.  
[3] 高兴烨，刘建军，任鑫，等.嫦娥二号探测器在轨运行视景仿真系统的研究与实现［J]．天文研究与技术——国家天文台台刊，2012，9(2)：114-120.Gao Xingye，Liu Jianjun，Ren Xin，et al.Research and implementation of visual simulationsystem of Chang'E-2 motion in orbit ［J].Astronomical Research & Technology———Publicationsof National Astronomical Observatories of China，2012，9(2）：114-120.  
[4] 邢丽平，左维，李春来.建立WebGIS的月球三维可视化关键技术［J]．天文研究与技术-国家天文台台刊，2014，11(3)：299-304.Xing Liping，Zuo Wei,Li Chunlai. Key technologies of a WebGIS-based 3D visualization systemfor the Moon [J].Astronomical Research & Technology———Publications of National AstronomicalObservatories of China，2014，11(3）:299-304.  
[5] 丁剑飞，刘永进.三维立体显示技术综述［J]．系统仿真学报，2008，20：132-135.Ding Jianfei，Liu Yongjin.A survey on three-dimension display technologies ［J]. Journal ofSystem Simulation，2008，20：132-135.  
[6] 孙超．几种立体显示技术的研究［J].计算机仿真，2008，25(4)：213-217.Sun Chao.A probe into several stereoscopic display technologies [J]. Computer Simulation,2008，25(4): 213-217.  
[7] 王琼华，王爱红.三维立体显示综述［J].计算机应用，2010，30(3)：579-588.Wang Qionghua，Wang Aihong. Survey on stereoscopic three-dimensional display [J]. Journal ofComputer Applications，2010，30(3）:579-588.  
[8] Wright J，Hartman F，Cooper B.Immersive environment technologies for planetary exploration[C]//Proceedings of the Virtual Reality 2001 Conference.2001：183-190.  
[9] McAllister DF. Display technology: stereo &3D display technologies [EB/OL].[2015-04-07].http://fp.optics. arizona.edu/opti588/reading/DavidMcAllister_DisplayTech _stereo% 20and%$20 3 \mathrm { D \% }$ 20Display_review.pdf.  
[10] 林征，宋恩民.立体显示技术在医学领域的应用［J].生命科学仪器，2013，11(2)：63-73.Lin Zheng，Song Enmin. Application of stereoscopic displays technology in medical ［J].LifeScience Instruments，2013，11(2):63-73.  
[11］潘家辉，吕成宾，彭丰平，等.立体显示技术在力反馈仿真手术的应用［J].软件，2014,35(10) : 32-36.Pan Jiahui，Lv Chengbin，Peng Fengping，et al. The application of stereoscopic on forcefeedback surgery simulation [J].Software，2014，35(10）:32-36.  
[12] 谭珂，潘新华，蔡守旺，等.三维立体显示技术在肝脏手术仿真训练系统中的应用［J]．中国医学教育技术，2011，25(5)：522-525.Tan Ke，Pan Xinhua，Cai Shouwang，et al. Application of 3D stereoscopic display technology insimulation training system for liver surgery [J]. China Medical Education Technology，2011,25(5): 522-525.  
[13] 万定生，龚汇丰.一种基于四叉树的大规模地形实时生成算法［J].计算机工程与应用，2005，33：186-188.Wan Dingsheng，Gong Huifeng.A quadtree-based and real-time generation algorithm for largescale terrain [J]. Computer Engineering and Applications，2005，33:186-188.  
[14] 赵猛，金一丞，尹勇.立体显示中双目视差模型和深度感知研究［J].计算机工程，2011,37(17) : 271-273.Zhao Meng，Jin Yicheng，Yin Yong. Research on binocular parallax model and depth perceptionin stereo display [J]. Computer Engineering，2011，37(17）:271-273.  
［15］赵猛．大屏幕多人沉浸式立体显示系统［D]．大连：大连海事大学，2010.

# Application of Binocular Stereo Display Technology in Three-Dimensional Visualization of the Moon

Gao Xingye $^ { 1 , 2 , 3 }$ , Liu Jianjun $^ { 1 , 3 }$ ，Ren Xin $^ { 1 , 3 }$ ，Mu Lingli $^ { 1 , 3 }$ ,Li Chunlai $^ { 1 , 3 }$ （204号 (1.NationalAstrocalOeatorsdefic，eia；.Uestfiede， Beijing 1Oo049,China；3.KeyLaboratoryof Lunarand Deep Space Exploration,National Astronomical Observatories， Chinese Academy of Sciences，Beijing 1Ooo12，China，Email：gaoxy $@$ nao.cas.cn )

Abstract:Based on the lunar terrain data and image data derived from Chang'E-2 probe，we develop a stereo display system of a virtual moon by using the binocular stereo display technology.This paper first introduces the principle of binocular stereo vision，and then discusses the design and implementation methods of the system in detail.Firstly，a framework and the hardware composition of the system are introduced；then organization mode of terrain data and dynamic scheduling for terrain real-time rendering are discussed；to achieve satisfying stereoscopic effct，off-axis model is used for stereoscopic rendering at last.This system plays an important role in science popularization about the Moon and research of lunar surface.

Key words:Chang'E-2；Binocular stereo display；Three-dimensional visualization of the Moon