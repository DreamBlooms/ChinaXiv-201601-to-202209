# 基于NDVI的新疆荒漠地区植被覆盖度遥感估算经验模型研究

岳健,²，穆桂金²，唐自华³，杨雪峰4，林永崇，徐立帅

1中国科学院新疆生态与地理研究所荒漠与绿洲生态国家重点实验室,新疆乌鲁木齐830011;2新疆策勒荒漠草地生态系统国家野外科学观测研究站,新疆策勒848300;

3中国科学院地质与地球物理研究所,北京10029；4新疆师范大学地理科学与旅游学院,新疆乌鲁木齐830054;5闽南师范大学历史地理学院,福建 漳州 363000；6山西农业大学资源与环境学院,山西 太古030801)

摘要：新疆荒漠地区植被覆盖度遥感估算模型十分缺乏，给荒漠化监测等相关工作带来很大不便,开展植被覆盖度遥感估算经验模型研究，对于促进和完善相关地区的生态监测及研究工作具有积极的现实意义。通过对阜康市北部沙漠南缘和克拉玛依市中部平原荒漠进行无人机航拍，利用无人机遥感提取(光合)植被信息，并将无人机航拍影像的植被覆盖度统计单元与高分辨率卫星影像像元在空间上直接相对应，获取在高分辨率卫星影像像元尺度上的植被盖度，然后通过植被覆盖度和空间上与其相对应的源自高分辨率卫星影像的NDVI数据的拟合关系，建立基于源自高分二号影像的NDVI的阜康北部沙漠植被覆盖度遥感估算线性模型以及基于源自ZY1-02C影像的 ND-VI的克拉玛依平原荒漠植被覆盖度遥感估算二次多项式模型。研究中所采用的无人机遥感与卫星遥感相结合、植被覆盖度统计单元与卫星像元在空间上直接对应的方法，可避免以往相关工作中常以点位测量数据代表卫星像元数据所带来的不确定性。由于所用卫星影像的NDVI数据稳定性相对不足等原因,所建立的遥感估算模型的估算精度尚相对偏低，有待于今后进一步的工作加以改进。

关键词：NDVI；荒漠；植被覆盖度；遥感估算；经验模型

植被覆盖度是观测区域内植被垂直投影面积占地表面积的百分比，是刻画陆地表面植被数量的一个重要参数，也是指示生态系统变化的重要指标。在土地利用/土地覆盖变化以及生态环境变化监测研究中，植被覆盖度的应用十分普遍。

传统的植被覆盖度数据可以通过地面实测获得，但是其获取过程费时、费力，在现代生态环境监测与研究中，尤其在监测或研究大面积区域时，单纯依靠地面实测已难以满足需求。因此，利用遥感手段间接获取植被覆盖度数据的方法应运而生，人们也探索出了基于植被指数的估算方法（如经验模型法）、基于数据挖掘技术的估算方法（如决策树分类法)等多种估算方法[1]。由于植被指数与植被覆盖度具有很强的线性或非线性相关性[2-3],因此,多年来植被指数在植被覆盖度遥感估算中的应用十分普遍，其中，又以归一化植被指数(NDVI)应用最为广泛[4-16] 。

受多种因素限制，现有利用遥感手段估算植被覆盖度的方法一般均各有优缺点。以目前国内应用较为流行的像元分解模型为例，由于模型中需要有全植被覆盖的像元，这就限制了该模型对低分辨率遥感数据的使用5，也限制了模型在一些植被覆盖度总体偏低地区例如西北干旱荒漠地区的应用。相对而言，经验模型法(或称回归模型法)虽然也有局限性，一般只适用于特定的区域与特定的植被类型[5],但该模型原理相对简单、容易实现、精度较高，应用上也较多数其它估算方法简便。国内目前关于干旱区的相关经验模型还不多[6,17],新疆地区虽有学者对植被覆盖度的遥感估算方法开展过一些工作[18-22],但经验模型则尚仅见于有学者在石河子地区所做的非专门针对荒漠地区的工作[18]。开展新疆荒漠地区植被覆盖度遥感估算经验模型的研究，对于促进和完善相关地区的生态监测及研究具有积极的现实意义。

已有的研究在调查或估算植被覆盖度时多是单独应用地面实测、无人机遥感[17,23-30]或是卫星遥感。也有部分研究是将地面实测与卫星遥感相结合，但在将地面实测与卫星遥感结合时，一般是以点位测量数据（单个样方值或多个样方平均值)代表大尺度卫星影像像元数据[18],植被覆盖度与卫星影像像元的空间对应关系并不直接，存在着一定的不确定性。本文拟通过将无人机遥感与卫星遥感相结合，先采用超低空无人机遥感提取植被信息，再将无人机航拍影像所提取的植被覆盖度与卫星影像像元在空间上直接相对应起来，在此基础上，探索建立基于NDVI的新疆荒漠地区(光合)植被覆盖度[31卫星遥感估算经验模型

# 数据处理与研究方法

# 1.1 工作步骤

研究工作分为5个步骤：（1）选择天气晴好的日期对研究区进行无人机超低空航拍。（2）根据航拍影像，提取所摄区域的植被信息。（3）购买于航拍当日过境的米级或亚米级高分辨率卫星影像，计算其 $N D V I _ { \circ }$ （4）将航拍影像与卫星影像配准后，以源自卫星影像的NDVI的格元为统计单元，计算航拍影像植被覆盖度。（5）根据航拍影像植被覆盖度和空间上与其一一对应的NDVI的数据拟合情形，建立二者的经验关系模型。

# 1.2 数据采集

选择阜康市北部的古尔班通古特沙漠南缘和克拉玛依市中部平原荒漠作为航拍区，分别位于地理坐标 $8 7 ^ { \circ } 5 7 ^ { \prime } 3 9 . 6 ^ { \prime \prime } \mathrm { E } . 4 4 ^ { \circ } 2 2 ^ { \prime } 1 9 . 2 ^ { \prime \prime } \mathrm { N }$ 和 $8 5 ^ { \circ } 5 ^ { \prime } 5 . 7 ^ { \prime \prime } \mathrm { E }$ 、$4 5 ^ { \circ } 3 3 ^ { \prime } 0 ^ { \prime \prime } \mathrm { N }$ 附近（图1）。航拍采用大疆悟1pro 四轴飞行器进行，单块电池飞行时间约 $1 5 \mathrm { m i n }$ ,相机镜头分辨率为 $1 ~ 6 0 0 \times 1 0 ^ { 4 }$ 像素。航拍分别于2017年6月20日和2016年9月3日进行，拍摄之前两日及拍摄当日天气晴或多云，静风至微风，地表干燥。拍摄时镜头垂直向下，航向和旁向重叠度均保持在$70 \%$ 以上，航高约 $6 \sim 7 ~ \mathrm { ~ m ~ }$ ，照片地面分辨率约$0 . 0 0 2 \sim 0 . 0 0 3 \mathrm { ~ m ~ }$ 。阜康航拍区由相距约 $4 0 \mathrm { ~ m ~ }$ 的两块区域组成,共拍摄照片1976幅,涉及面积约$0 . 5 1 8 { \ \mathrm { h m } } ^ { 2 }$ ;克拉玛依航拍区共拍摄照片1553幅，涉及面积约 $0 . 6 8 \ \mathrm { h m } ^ { 2 }$ 。

航拍结束数月后经查询购买到2017年6月20日航拍当日过境阜康航拍区的高分二号卫星影像(GF2_PMS2_E88.0_N44.5_ 20170620L1A0002431214），以及2016年9月2日即航拍前一日过境克拉玛依航拍区的ZY1-02C卫星影像$( \mathrm { \ Z Y 0 2 C _ { \mathrm { ~ - } } ~ H R C _ { \mathrm { ~ - } } ~ E 8 5 . ~ \ 2 _ { \mathrm { ~ - } } ~ N 4 5 . ~ \ 7 ~ \ } _ { \mathrm { ~ - } } \ 2 0 1 6 0 9 0 2 _ { \mathrm { ~ - } }$ L1C0003517850、ZY02C_PMS_E85．2_N45.7_20160902_L1C0003517696），航拍区晴空无云。高分二号的全色波段影像分辨率为 $1 \mathrm { ~ m ~ }$ ，多光谱影像分辨率为 $4 \ \mathrm { m } , \mathrm { Z Y 1 - 0 2 C }$ 的PMS相机全色波段影像分辨率为 $5 \mathrm { ~ m ~ }$ ，多光谱影像分辨率为 $1 0 \mathrm { ~ m ~ }$ ,HR相机影像分辨率为 $2 . 3 6 \mathrm { ~ m ~ }$ ○

![](images/bda4e4b83228700002fec8d67d6da775616cdabfb2d02c68dda97457ffddd02f.jpg)  
图1航拍区位置示意图Fig.1Aerial shooting area

# 1.3 数据处理

1.3.1影像拼接与校正航拍影像采用AgisoftPhotoscan软件进行拼接处理，经对齐照片、建立密集点云、生成网格、生成纹理等步骤后，最终生成正射RGB影像。高分二号影像和ZY1-02C影像采用ENVI软件进行辐射定标、大气校正和正射校正（正射校正输出结果的采样方式为立方卷积），投影方式为WGS_1984_UTM_Zone_45N。

分别根据高分二号的全色波段影像和ZY1-02C的HR影像对阜康航拍区和克拉玛依航拍区航拍正射影像进行配准。图像配准、切割及投影转换等工作在ArcGIS软件下进行。图像输出结果的采样方式均为最近邻，配准精度控制在0.5个像元之内。1.3.2植被信息提取数码相机照相法是植被覆盖度地面测量法中最客观且精度最高的测量方法[32],本研究中采用的无人机超低空航拍其相对航高不足 $8 \mathrm { ~ m ~ }$ ,本质上仍可看作是数码相机照相法的一种实施方式。已有研究表明，利用无人机替代人工开展荒漠地区植被覆盖度调查是相对客观、高效和值得推广的一种调查方式[17]。根据前人研究成果，可见光波段差异植被指数VDVI（visible-banddifferencevegetationindex）在植被和非植被分离度较高，其数值几乎没有交叉，比较适合无人机拍摄影像植被的提取[17],因此本文采用VDVI指数用于无人机RGB影像的植被信息提取。

VDVI的计算公式为：

$$
V D V I = \frac { 2 \times \rho _ { g r e e n } - \rho _ { r e d } - \rho _ { b l u e } } { 2 \times \rho _ { g r e e n } + \rho _ { r e d } + \rho _ { b l u e } }
$$

式中 $: \rho _ { \mathit { r e d } } \setminus \rho _ { \mathit { g r e e n } } \setminus \rho _ { \mathit { b l u e } }$ 分别为红、绿、蓝3个波段对应的反射率。

由于无人机影像噪音的存在， $W D W$ 提取的植被信息一般会略多于实有的（光合）植被信息，但通过合理设置提取阈值，可以将这一误差控制在适当的范围内。结合目视解译以及航拍当日实地调查情形，经过反复比较尝试，选择0.034作为本研究中航拍影像的光合植被VDVI提取阈值（图2）。对照实地调查结果可发现，在对应卫星影像的裸地或几无光合植被的像元（植被覆盖度视为0），VDVI据此阈值提取的无人机影像植被覆盖度均不超过 $0 . 0 8 \%$ ，这个误差对于荒漠区植被动态监测来说是完全可以接受的。

1.3.3NDVI生成、植被覆盖度计算及数据拟合分别用红和近红外两个波段数据计算高分二号影像和ZY1-02C影像的 $N D V I _ { \circ }$ 使用ArcGIS软件中的ZonalStatistics工具，将由航拍影像提取的（光合）植被信息与NDVI图进行叠加，统计生成NDVI图像各对应格元内的植被覆盖度（图3）。根据分别源自高分二号影像的NDVI（以下简称GF2-NDVI)和源自ZY1-02C 影像的 NDVI(以下简称 ZY1-02C NDVI)与对应的无人机航拍影像提取的植被覆盖度信息的拟合情况，建立NDVI与植被覆盖度的经验关系模型，并根据优选出的关系模型，分别进行植被覆盖度计算，生成植被覆盖度图。数据系列关系拟合借助

![](images/e93779d937b2cbb746a19d26e6bc82e14ab50cfeda6144dcc8c69595db3f83ee.jpg)  
图2VDVI提取植被信息效果  
Fig.2Effect of extracting vegetation information from VDVI

![](images/7bcaab32b307374f2df59d01e40c1b27e5480c3ab0e7965b0c1c5b6345f9f5b1.jpg)  
图3以NDVI格元为统计单元计算植被覆盖度 Fig.3Computing vegetation coverage with NDVI cells as statistical units

Origin软件完成。

# 2 结果与分析

# 2.1基于GF2-NDVI的阜康北部沙漠植被覆盖度遥感估算模型

将由航拍影像提取的（光合）植被信息与GF2-NDVI图进行叠加，统计GF2-NDVI图像各对应格元内的植被覆盖度，去除边缘不完全重叠格元，共提取107对GF2-NDVI值及与该GF2-NDVI图像格元相对应的植被覆盖度数据，在Origin中进行拟合，结果表明，多项式拟合效果最好，线性次之（图4、表1）。多项式虽然随着次数增加，决定系数 $R ^ { 2 }$ 的值也继续增大,但由于多项式高次项的系数为负值，随着 $x$ 值(NDVI)增大， $y$ 值(植被覆盖度)在30附近或稍大于20处即出现向下的拐点，显然与常识不符，因此，选取线性方程 $y = 1 4 9 . 8 6 x - 1 3 . 4 4 9$ （ $R ^ { 2 } = 0 . 7 3 5 \ 3$ ）

![](images/b425aa58a2027cc30b7ebe2bb6491876f95a73d004093aa900dc901181dd814b.jpg)

# 表1GF2-NDVI与植被覆盖度的拟合方程

Tab.1 Fitting equations of GF2-NDVI and vegetation coverage   

<html><body><table><tr><td>趋势线类型</td><td>方程</td><td>决定系数R²</td></tr><tr><td>指数</td><td>y =0. 203e22.291x</td><td>0. 444 2</td></tr><tr><td>线性</td><td>y =149.86x -13.449</td><td>0. 7353</td></tr><tr><td>对数</td><td>y=22.929ln(x） +53.236</td><td>0. 734 0</td></tr><tr><td>多项式</td><td>y= -311.85x² +251.03x-21.138</td><td>0. 742 4</td></tr><tr><td>幂</td><td>y =512 0x3.520 6</td><td>0.472 6</td></tr></table></body></html>

作为基于GF2-NDVI的阜康北部沙漠植被覆盖度遥感估算模型。据此模型计算的覆盖度如图5所示，与这一区域多中高盖度梭梭、总体以固定半固定沙漠为主的野外实况相符。

# 2.2基于ZY1-02CNDVI的克拉玛依平原荒漠植被覆盖度遥感估算模型

与2.1节类似，将由航拍影像提取的（光合）植被信息与ZY1-02CNDVI图进行叠加，统计ZY1-02C

![](images/58f76c71589910c46c0e7676fa72fdb28ecfedd04d375bce681a85fb86d11c12.jpg)  
图4GF2-NDVI与植被覆盖度的拟合关系 Fig.4Fitting relation between GF2-NDVI and vegetation coverage   
图5GF2-NDVI及其对应的植被覆盖度  
Fig. 5 GF2-NDVI and its corresponding vegetation coverage

![](images/79a0fc622e6506d936a18d662c4eb08ecdc6a80ba02ad1626cc119fe21118cc5.jpg)  
图6ZY1-02C NDVI与植被覆盖度的拟合关系 Fig.6Fitting relation between ZY1-O2C NDVI and vegetation coverage

# 表2ZY1-02CNDVI与植被覆盖度的拟合方程

Tab.2 Fittng equations of ZY1-02C NDVI and vegetation coverage   

<html><body><table><tr><td>趋势线类型</td><td>方程</td><td>决定系数R²</td></tr><tr><td>指数</td><td>y = 1.766 5e9.793 5x</td><td>0. 778 4</td></tr><tr><td>线性</td><td>y=118.9x-8.499 8</td><td>0.815 5</td></tr><tr><td>对数</td><td>y=20.468ln(x）+49.22</td><td>0.770 2</td></tr><tr><td>多项式</td><td>y=97.397x² +80.837x-5.210 9</td><td>0.818 0</td></tr><tr><td>幂</td><td>y = 236. 74x1.763 9</td><td>0.8048</td></tr></table></body></html>

NDVI图像各对应格元内的植被覆盖度，去除边缘不完全重叠格元，共提取47对ZY1-02CNDVI值及与该ZY1-02CNDVI图像格元相对应的植被覆盖度数据，在Origin中进行拟合，结果表明，多项式拟合效果最好（图6、表2）。因此，选取多项式方程 $y =$ $9 7 . 3 9 7 x ^ { 2 } + 8 0 . 8 3 7 x - 5 . 2 1 0 ~ 9$ ！ $R ^ { 2 } = 0 . 8 1 8 ^ { \circ } ,$ 作为基于ZY1-02CNDVI的植被覆盖度遥感估算模型。据此模型计算的覆盖度如图7所示，与野外调查时图内中部偏右南北向道路的西侧区域以中高盖度梭梭、怪柳及花花柴等植被为主、东侧以低盖度稀疏梭梭为主的实况相符。

# 2.3模型估算精度

根据公式(2）、（3）[30],以由航拍影像提取的植被覆盖度作为基准，可以分别计算得到GF2-NDVI、ZY1-02CNDVI与植被覆盖度关系模型的均方根误差和估算精度。

$$
R M S E \ = \ { \sqrt { \frac { \displaystyle \sum _ { i = 1 } ^ { n } \left( f c - f c ^ { \prime } \right) ^ { 2 } } { n } } }
$$

$$
A c = \left[ 1 - \frac { R M S E } { \bar { f } \bar { c } } \right] \times 1 0 0 \%
$$

式中：RMSE为均方根误差； $f { \boldsymbol { c } }$ 为作为基准的植被覆盖度样本值 $; f c ^ { \prime }$ 为植被覆盖度估算值; $n$ 为样本数;$A c$ 为估算精度; $\overline { { f c } }$ 为作为基准的植被覆盖度样本的均值。

由表3看到，上述两个估算模型的估算精度尚相对偏低，尤其是基于GF2-NDVI的植被覆盖度估算模型。这可能主要跟GF2-NDVI与植被信息对应

![](images/f12c61e903dfc3bec0710445f8f586a4be48c4aaef438046af66a64363843014.jpg)  
图7ZY1-02C NDVI及其对应的植被覆盖度  
Fig.7ZY1-O2C NDVI and its corresponding vegetation coverage

# 表3模型的估算精度

Tab.3Accuracy of estimation models   

<html><body><table><tr><td>模型</td><td>均方根误差(RMSE)／%</td><td>估算精度/%</td><td>模型</td><td>均方根误差(RMSE)／%</td><td>估算精度／%</td></tr><tr><td>GF2-NDVI线性估算模型</td><td>3.196 8</td><td>60.31</td><td>ZY1-02C-NDVI多项式估算模型</td><td>3.412 0</td><td>70.38</td></tr></table></body></html>

关系的稳定性相对不足有关。对照实地调查结果和GF2-NDVI数据可以发现，在航拍区及其附近区域内，在裸地或仅有非光合植被的像元，GF2-NDVI的值可在 $0 . 0 2 8 \sim 0 . 1 3 5$ 之间变动,变动幅度明显偏大。此外，影像配准误差和植被信息VDVI指数提取误差也会有一定影响。

# 3结语

本文对探索基于NDVI的新疆荒漠地区植被覆盖度遥感估算经验模型做了一些尝试，取得了一些初步结果：

（1）通过无人机遥感与卫星遥感相结合、植被覆盖度统计单元与卫星影像像元直接对应的方法，可以使在构建植被覆盖度遥感估算模型过程中植被覆盖度与卫星影像像元的空间对应关系相对更为直观和准确，避免了以往相关工作中常以点位测量数据代表大尺度卫星像元数据所带来的不确定性，并为今后开展类似工作提供了一种思路。

（2）获得了基于源自高分二号影像的NDVI的阜康北部沙漠植被覆盖度遥感估算线性模型以及基于源自ZY1-02C影像的NDVI的克拉玛依平原荒漠植被覆盖度遥感估算二次多项式模型。这些模型可在一定程度上为新疆地区相关的生态监测和研究工作提供服务和参考。

由于本文所用卫星影像的NDVI数据稳定性相对不足等原因，所获得的遥感估算模型的估算精度尚相对偏低，有待于今后进一步的工作加以改进。

# 参考文献(References)

[1］程红芳,章文波,陈锋.植被覆盖度遥感估算方法研究进展[J]. 国土资源遥感,2008,（1）:13-18.[CHENG Hongfang,ZHANG Wenbo,CHEN Feng.Advances in researches on application of remote sensing method to estimating vegetation coverage[J].Remote Sensing for Land and Resources,2008,（1):13-18.]   
[2]ASRAR G,MYNENIR B,CHOUDHURY B J. Spatial heterogeneity in vegetation canopies and remote sensing of absorbed photosynthetically active radiation:A modelling study[J].Remote Sensing ofEnvironment,1992,41(2-3):85-103.   
[3] CHOUDHURY B J.Relationships between vegetation indices,radiation absorption and net photosynthesis evaluated by a sensitivity analysis[J].Remote Sensing of Environment,1987,22（2）:209- 233.   
[4]张生军，王涛,王天明.新疆不同植被NDVI的变化及其与气候 因子的关系［J].草业科学2009，26（5）：26-31.［ZHANG Shengjun,WANG Tao,WANG Tianming.The variations in NDVIof

different vegetation types in Xinjiang and its relation to climate factors[J].Pratacultural Science,2009,26(5）:26 -31.]

[5]李苗苗.植被覆盖度的遥感估算方法研究［D].北京：中国科学院研究生院,2OO3.［LI Miaomiao.The methodofvegetationfraction estimation by remote sensing[D].Beijing: University ofthe Chinese Academy of Sciences,2003.]

[6］王晓慧,李增元,高志海,等.沙化土地信息提取研究[J].林业 科学,2005,41(3）:82-87.[WANG Xiaohui,LI Zengyuan,GAO Zhihai,et al.Information extraction of sandy land[J]. Scientia Silvae Sinicae,2005,41(3) :82 -87.]   
[7]张云霞,李晓兵,陈云浩.草地植被盖度的多尺度遥感与实地 测量方法综述［J].地球科学进展,2003,18（1)：85－93. [ZHANG Yunxia,LI Xiaobing,CHEN Yunhao. Overview of field and multi-scale remote sensing measurement approaches to grassland vegetation coverage[J].Advace in Earth Sciences,2003,18 (1) :85 -93.]   
[8］张本昀,喻铮铮,刘良云,等.北京山区植被覆盖动态变化遥感 监测研究［J].地域研究与开发,2008,27（1）：108－112. [ ZHANG Benyun,YU Zhengzheng,LIU Liangyun,et al. Studyon the vegetation coverage changes monitoring of Beijing City by remote sensing[J]. Areal Research and Development,2008,27(1): 108 -112. ]   
[9］叶贵祥,李维青,田源.基于NDVI的干旱区典型绿洲植被覆盖 动态变化分析——以策勒绿洲为例[J].干旱区资源与环境， 2009,23(9）:128-133.[YE Guixiang,LI Weiqing,TIAN Yuan. Dynamic changes of vegetation cover in typical oasis of arid areas based on NDVI[J]. Journal of Arid Land Resources and Environment,2009,23(9):128-133.]   
[10］游浩妍,骆成凤,刘正军,等.基于 MODIS 植被指数估算青海 湖流域植被覆盖度研究[J].遥感信息,2012,27（5）:55-60. [YOU Haoyan,LUO Chengfeng,LIU Zhengjun,et al. Estimation vegetation coverage based on vegetation index of MODIS data in Qinghai Lake watershed[J].Remote Sensing Information,2012,27 (5) :55 -60.]   
[11］何雅枫,花立民,邸利.不同植被指数反映地表植被覆盖度的 比较分析—以甘肃河西走廊地区为例[J].中国农学通报, 2014,30（19）:45-50.[HE Yafeng,HUA Limin,DI Li.Comparative analysis on the reflection eect of the vegetation on the Earth' S surface by diferent vegetation indices:A case study in Hexi Corridor[J]. Chinese Agricultural Science Bulltin,2014,30（19）: 45 -50.]   
[12］王计平,郭仲军,黄继红,等.北疆不同生态功能区近30 年来 植被盖度时空变化[J].林业资源管理,2015,（6):64－70. [WANG Jiping,GUO Zhongjun,HUANG Jihong,et al. Characteristics of spatio-temporal variation of NDVI in diferent ecological function zones in north Xinjiang in recent 3O years[J].Forest Resources Managemet,2015,（6）:64-70.]   
[13］蔡朝朝,安沙舟,蒲智,等.基于TM NDVI的库尔勒市域植被覆 盖动态变化[J].草业科学,2015,32（7）:1069－1078.[CAI Chaochao,AN Shazhou,PU Zhi,et al.A studyon vegetationcoverage change in Korla City based on the TM NDVI[J].Pratacultural Science,2015,32（7) :1069 -1078.]   
[14］陈明华,柴鹏,陈文祥,等.不同植被指数估算植被覆盖度的比 较研究[J].亚热带水土保持,2016,28（1）:1-4.［CHEN Minghua,CHAI Peng,CHEN Wenxiang,et al. Comparative study on

the estimation of the vegetation coverage by different vegetation indexes[J].Subtropical Soil and Water Conservation,2016,28（1）： 1-4.]

[15］王丽春,焦黎,来风兵.基于NDVI的新疆玛纳斯湖湿地植被覆 盖度变化研究[J].冰川冻土,2018,40（1）：176－185.[WANG Lichun,JIAO Li,LAI Fengbing. Thevegetation coverage change based on NDVI of the wetland by Manas Lake,Xinjiang[J]. Journal of Glaciology and Geocryology,2018,40（1）:176 -185.]   
[16］段峥嵘,祖拜代·木依布拉,夏建新.基于 NDVI的干旱区绿洲 植被覆盖度动态变化分析——以新疆阿克苏地区为例[J].中 央民族大学学报（自然科学版）,2018,27（2）:5-14.[DUAN Zhengrong,MUYIBULA Zubaidai,XIA Jianxin.Analysis of vegetation coverage dynamic change in typical oasis of arid areas based on NDVI:A case studyof Aksu region in Xinjiang[J]. Journalof MUC（Natural Sciences Edition）,2018,27(2）:5 -14.]   
[17］高永平,康茂东,何明珠,等.基于无人机可见光波段对荒漠植 被覆盖度提取的研究——以沙坡头地区为例[J].兰州大学学 报（自然科学版）,2018,54（6）:770－775.[GA0 Yongping, KANG Maodong,HE Mingzhu,et al.Extraction of desert vegetation coverage based on visible light band information of unmanned aerial vehicle:A case study of Shapotou region[J]. Journal of Lanzhou University(Natural Science Edition）,2018,54(6):770-775.]   
[18］江淼,张显峰,孙权,等.不同分辨率影像反演植被覆盖度的参 数确定与尺度效应分析[J].武汉大学学报,2011,36（3）： 311-315.[JIANG Miao,ZHANG Xianfeng,SUN Quan,et al. Vegetation coverage retrieval scale effect analysis using multi-sensor data[J].Geomatics and Information Science of Wuhan University,2011,36(3) :311 -315.]   
[19］古丽·加帕尔,陈曦,包安明.干旱区荒漠稀疏植被覆盖度提 取及尺度扩展效应[J].应用生态学报,2009,20（12）;2925- 2934.[JIAPAER Guli,CHEN Xi,BAO Anming. Coverage extraction and up-scaling of sparse desert vegetation in arid area[J]. Chinese Journal of Applied Ecology,2009,20（12）:2925- 2934.]   
[20］古丽·加帕尔,陈曦,马忠国.干旱区稀疏芦苇盖度遥感信息 提取[J].干旱区地理,2010,33（6）:988-996.[JIAPAERGuli,CHEN Xi,MA Zhongguo.Extraction of vegetation fraction over the sparse reed in arid area[J].Arid Land Geography,2010,33 (6) :988 -996.]   
[21］于嵘,亢庆,张增祥,等.中国西北盐碱区植被盖度遥感方法分 析[J].干旱区资源与环境,2006,20（2）：154－158.［YU Rong,KANG Qing,ZHANG Zengxiang,et al. Analysis on the methods for assessing vegetation cover based on RS in alkali region,northwest China[J]. Journal of Arid Land Resources and Environment,2006,20(2）:154-158.]   
[22］牛宝茹,刘俊蓉,王政伟.干旱半干旱地区植被覆盖度遥感信 息提取研究［J].武汉大学学报.信息科学版,2005,30（1）： 27- 80.［NIU Baoru,LIU Junrong，WANG Zhengwei.Remote sensing information extraction based on vegetation fraction in drought and half-drought area[J].Geomatics and Information Science of Wuhan University,2005,30(1):27-80.]   
[23］谢涛,刘锐,胡秋红,等.基于无人机遥感技术的环境监测研究 进展[J].环境科技,2013,26(4）:55-60.[XIE Tao,LIU Rui, HU Qiuhong,et al.A critical review on unmammed aerial vehicle remote sensing technology in the fieldof environmental monitoring [J].Environmental Science and Technology,2013,26(4）:55- 60.]   
[24］汪小钦,王苗苗,王绍强,等.基于可见光波段无人机遥感的植 被信息提取[J].农业工程学报,2015,31（5）：152－159. [WANG Xiaoqin,WANG Miaomiao,WANG Shaoqiang,et al. Extraction of vegetation information from visible unmanned aerial vehicleimagesJ].Transactions of the Chinese Societyof Agricultural Engineering,2015,31(5）:152-159.]   
[25］田明璐,班松涛,常庆瑞,等．基于低空无人机成像光谱仪影像 估算棉花叶面积指数[J].农业工程学报,2016,32（21)：102- 108.[Tian Minglu,Ban Songtao,Chang Qingrui,et al. Use of hyperspectral images from UAV-based imaging spectroradiometer to estimate cotton leaf area index[J].Transactions of the Chinese Society of Agricultural Engineering,2016,32（21）:102-108.]   
[26］宋清洁,崔霞,张瑶瑶,等.基于小型无人机与 MODIS 数据的 草地植被覆盖度研究——以甘南州为例[J].草业科学,2017, 34(1):40 -50.[SONG Qingjie,CUI Xia,ZHANG Yaoyao,et al. Grassand fractional vegetation cover analysis using small UAVs and MODIS:A case study in Gannan Prefecture[J].Pratacultural Science,2017,34(1) :40-50.]   
[27］冯海英,冯仲科,冯海霞.一种基于无人机高光谱数据的植被 盖度估算新方法[J].光谱学与光谱分析,2017,37（11）：3573 - 3577.[FENG Haiying,FENG Zhongke,FENG Haixia.A new method for estimating the fractional vegetation cover based on UAV hyperspectrum[J]. Spectroscopy and Spectral Analysis,2017,37 (11) :3573 -3577. ]   
[28］孙世泽,汪传建,尹小君，等.无人机多光谱影像的天然草地生 物量估算[J].遥感学报,2018,22（5）：848-856.[SUN Shize, WANG Chuanjian,YIN Xiaojun,et al.Estimating aboveground biomass of natural grassand based on multispectral images of unmanned aerial vehicles[J]. Journal of Remote Sensing,2018,22 (5) :848 -856.]   
[29］万炜,肖生春,陈小红,等.无人机遥感在野外植被盖度调查中 的应用——以阿拉善荒漠区灌木为例[J].干旱区资源与环 境,2018,32（9）:150-156.[WAN Wei,XIAO Shengchun, CHEN Xiaohong,et al.Application of unmanned aerial vehicles to field vegetation coverage survey[J]. Journal of Arid Land Resources and Environment,2018,32(9）:150 -156.]   
[30］刘艳慧,蔡宗磊,包妮沙,等.基于无人机大样方草地植被覆盖 度及生物量估算方法研究[J].生态环境学报,2018,27（11）： 2023-2032.[LIU Yanhui,CAI Zonglei,BAO Nisha,et al.Research of grassand vegetation coverage and biomass estimation method based on major quadrat from UAV photogrammetry[J].Ecology and Environmental Sciences,2018,27(11):2023-2032.]   
[31］柴国奇,王静璞,邹学勇,等.基于 Sentinel-2 数据的典型草原 光合/非光合植被覆盖度估算[J].草业科学,2018,35（12）： 2836 -2844.[CHAI Guoqi,WANG Jingpu,ZOU Xueyong,et al. Estimating fractional cover of photosynthetic/non-photosynthetic vegetation in a typical steppe region based on Sentinel-2 data[J]. Pratacultural Science,2018,35（12）:2836-2844.]   
[32］顾祝军.植被覆盖度的照相法测算及其与植被指数关系研究 [D].南京：南京师范大学,2005.［GU Zhujun.Study on the measurement of photography method for vegetation coverage and its relationship with vegetation index[D].Nanjing:Nanjing Normal University,2005.]

# Remote sensing estimation models for vegetation coverage in desert regions of Xinjiang based on NDVI

YUE Jian1²，MU Gui-jin $\mathbf { \Psi } _ { . } ^ { 1 , 2 }$ ，TANG Zi-hua³， YANG Xue-feng4， LIN Yong-chong§， XU Li-shuai6 (1State KeyLaboratoryof DesertandOasis EcologyXinjiang IstituteofEcologyand Geography,ChineseAcademyofSciences， Urumqi830o11,Xinjiang,China；2Cele National StationofObservationand ResearchforDesert-GrasslandEcosystems, Cele 848300,Xinjiang,China；3Instituteof GeologyandGeophysics,ChineseAcademyofSiences,Beijing1o29,hina;   
4College of Geography Science and Tourism,Xinjiang Normal University,Urumqi 830o54,Xinjiang,China;   
5School of History and Geography,Minnan Normal University,Zhangzhou 363Ooo,Fujian,China;   
6College of Resources and Environment,Shanxi Agricultural University,Taigu O3o8O1,Shanxi,China)

Abstract:The lack of remote sensing estimation models invegetation coverage fordesert regions of Xinjiang,China has brought great inconvenience to desertification monitoringand otherrelated work.It is of positive and practical significance to study the empirical models for remote sensing estimation of vegetation coverage for promoting and improving ecological monitoring abilities in relevant areas.In this study,unmanned aerial vehicle（UAV）photography was firstlycarredout in typical desert regions in Xinjiang,vegetation information（photosynthesis）was extracted by UAV images.Secondly,vegetationcoverage was obtained at the pixel scale of high resolution satelite image by makingthestatisticalunits of vegetation coverage directly correspond to thepixelsof high resolution satelite image in space.Lastly,based on the fiting relationship between vegetation coverage and the corresponding NDVI data derived from high resolution satelite images,the empirical models were established for estimating vegetation coverage of typical desertregions in Xinjiang.The deserts inthe southern margin of the northern partof Fukang Cityand in the central plain of Karamay City were chosen asaerial shooting areas respectively.The relative flight height was set to $6 - 7 \mathrm { ~ m ~ }$ and the ground resolution was $0 . 0 0 2 \mathrm { ~ - 0 . 0 0 3 ~ m }$ .Satellite images which were shot on the same day and the daybefore UAV photographing,were selected and purchased for generating NDVI data.Agisoft Photoscan software was used for UAV image processing,ENVI and ArcGIS software packages were used for satelite remote sensing image procesing and spatial analysis,Origin software was usedfor fiting analysis of data series and the vegetation information of UAV images was extracted by $W D W$ index.As a result,a linear model ( $\quad ( y = 1 4 9 . \ 8 6 x - 1 3 . 4 4 9 \mathrm { , } R ^ { 2 } =$ 0.735 3）was established for remote sensing estimation of vegetation coverage in northern sandy desert in Fukang based on NDVI derived from GF2 satellite image and a quadratic polynomial model $\ \cdot \ y = 9 7 . \ 3 9 7 x ^ { 2 } + 8 0 . \ 8 3 7 x \ -$ 5.210 9, $R ^ { 2 } = 0 . 8 1 8$ ） was established for remote sensing estimation of vegetation coverage in plain desert in Karamay based on NDVI derived from ZY1-O2C satelite image.These models might provide necessary foundation and basis for monitoring and research of landuse and landcover change,ecological environment change,desertification (orsandydesertification）,vegetation mapping and other related work in Xinjiang.The combination of UAV images and sateliteremotelysenseddataandthe spatial direct corrspondence between vegetation coverage statisticalunit and satelite pixel,could avoid theuncertaintycaused bythe process ofrepresenting vegetation coverageof satelite pixel with manual measurement data at diferent points in the previous related work.The proposed method made the spatial matching between vegetation coverage and satelite image pixels relatively more intuitive and accurate in the process of constructing remote sensing estimation model of vegetationcoverage and it also provided an idea for similar work.

Key words:NDVI; desert； vegetation coverage；remote sensing estimation；empirical model